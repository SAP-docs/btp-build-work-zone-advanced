<!-- loio1fd9ea4f7051499db52b2dc086b86b54 -->

# Solution Architecture and Authentication Details

Information about hostname patterns, trust setup, and authentication flows.



This guide is equally applicable to SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone. For convenience, we will use the product name SAP Build Work Zone, advanced edition.

> ### Note:  
> SAP SuccessFactors Work Zone connected to HXM Core \(BizX\) is no longer supported, and since February 2022 all customers need to follow SAP note [0003111415](https://launchpad.support.sap.com/#/notes/0003111415) - How to decouple SAP Jam or SAP SuccessFactors Work Zone from BizX, guidelines and to switch to the new setup.



<a name="loio1fd9ea4f7051499db52b2dc086b86b54__section_j3y_vsk_4tb"/>

## Hostname Pattern

There are two components that create the SAP Build Work Zone, advanced edition experience with dedicated domain patterns:

1.  A subscription available via the SAP BTP cockpit.

    **URL pattern:** https://<SAP BTP subaccount domain\>.<type\>.cfapps.<SAP BTP subaccount region\>.hana.ondemand.com

    For more information about SAP BTP subaccount domain, see [Create a Subaccount](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/05280a123d3044ae97457a25b3013918.html)

    For more information about the type \(**workzone** for SAP Build Work Zone, advanced edition or **workzonehr** for SAP SuccessFactors Work Zone \), see [Regions and API Endpoints Available for the Cloud Foundry Environment](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/f344a57233d34199b2123b9620d0bb41.html) 

2.  The Digital Workplace Service seamlessly integrated into the subscription as an iframe \(transparent to the end-user\).

    **URL pattern:** https://<unique subdomain\>.<DWS region\>.workzone.ondemand.com

    Unique subdomain - this will either be automatically generated when creating a fresh SAP Build Work Zone, advanced edition environment, or handled by SAP Support when running the SAP Jam domain migration. For more information, see SAP note [0002920494](https://launchpad.support.sap.com/#/notes/0002920494) - How to raise domain migration request for transition from SAP Jam to SAP Build Work Zone, advanced edition?

    Digital Workplace Service region - this will automatically follow the pattern of coreXX, with XX = data region. For example, DC12 will be core12.




<a name="loio1fd9ea4f7051499db52b2dc086b86b54__section_c2m_cvk_4tb"/>

## Trust Setup

SAP Build Work Zone, advanced edition is running as a service on SAP BTP and hence relies on the trust configuration on the subaccount level. You must configure SAP Cloud Identity Services - Identity Authentication as the primary IdP, whether you connect to it directly or you use it as a proxy, using OpenID Connect \(recommended\) or SAML2.

For more information about configuring a trust between SAP BTP and Identity Authentication, see:

[Setting Up Trust Between Identity Authentication and SAP BTP](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/9dba751c208f4435a711c26b20945980.html), [Configuring Single Sign-On Using Identity Authentication](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/5a31ca1032334a52bc084816567f16ec.html)

For more information about using Identity Authentication as the primary IdP or as a proxy, see [Corporate Identity Providers](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/19f3eca47db643b6aad448b5dc1075ad.html).

-   Subaccount \> Security \> Users list \(if the *Create Shadow Users During Logon* option is enabled\)
-   Subaccount \> Connectivity \> Destinations \(for example, the `userIdSource` property\)
-   Attributes for Principal Propagation to on-premise backend systems
-   Attributes shown in the user avatar in SAP Build Work Zone, advanced edition shell header

> ### Note:  
> The standard setup guidelines assume that the SAP BTP subaccount is connected to the Identity Authentication, based on SAML2 with the documented assertion attributes as described in the respective onboarding guide: The information configured for this trust setup is impacting the user attributes available in: [Onboarding to SAP Build Work Zone, advanced edition](onboarding-to-sap-build-work-zone-advanced-edition-f8c6eab.md), [Onboarding to SAP SuccessFactors Work Zone](onboarding-to-sap-successfactors-work-zone-edc62f9.md)

In addition to the SAP BTP subaccount level trust, an additional trust configuration is required, for the Digital Workplace Service component running as an iframe in SAP Build Work Zone, advanced edition. This trust is SAML2-based trust and configured as a fallback mechanism. More details can be found in the next section 'Authentication Flow' of this guide.



<a name="loio1fd9ea4f7051499db52b2dc086b86b54__section_qpt_dwk_4tb"/>

## Authentication Flows

When a user accesses any link for SAP Build Work Zone, advanced edition, the trust between the subaccount and the Identity Authentication \(and optionally connected IdP\) is leveraged. In contrast, the authentication for the Digital Workplace Service iframe is done via a single\_use\_token generated via an API call using the “JAM” destination with OAuth2SAMLBearerAssertion as an authentication mechanism.



### SAP BTP

The information configured for this trust setup is impacting the user attributesIn the “JAM” destination, the following two properties need to be looked at specifically. By default, they are created as follows:

-   nameIdFormat = urn:oasis:names:tc:SAML:1.1:nameid-format:unspecified
-   userIdSource = user\_uuid



### Identity Authentication

The userIdSource property in the “JAM” destination is referring to the assertion attributes configured in Identity Authentication and/or the connected IdP. The same mechanism is used for other destinations such as the HR content package of SAP SuccessFactors Work Zone. For more information, see [Creating Destinations to SAP SuccessFactors](https://help.sap.com/docs/SAP_SUCCESSFACTORS_WORK_ZONE/04877e17a5da4908a6fea94949e160b5/c12996ba62d34dfba5ae042fb925add2.html)



### Digital Workplace Service

For the single\_use\_token API call to be successful, the “JAM” destination properties need to match the configured *SAML Trusted IdP* that is configured automatically during the SAP Build Work Zone, advanced edition onboarding wizard. By default, it is referring to the`SCIM.userName` attribute in the user record, but it can alternatively also connect to either `SCIM.externalId` or the `SCIM.emails.value` to find a unique user. In case emails.value is leveraged, the `nameIdFormat` property in the “JAM” destination as well as the trusted IdP need to be adjusted accordingly.

> ### Sample Code:  
> ```
> 
> "userName": "<value>", 
> "externalId": "<value>", 
> "emails": [ 
> 	{ 
> 		"value": "<value>", 
> 		"primary": true 
> 	} 
> ], 
> 
> ```

> ### Note:  
> In case the API call to create this single\_use\_token fails for some reason, the Digital Workplace Service < \> Identity Authentication trust based on SAML2 is leveraged. In this case, the *Subject Name Identifier* configured in Identity Authentication for the Digital Workplace Service \(i.e., NOT the one for the SAP BTP subaccount!\) needs to match the `SCIM.userName` in the user record.

