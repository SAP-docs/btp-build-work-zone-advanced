<!-- loiof04c185d689846908fb11d9a228392a2 -->

# User Authentication, Provisioning and Authorization

Additional information about user authentication, provisioning and authorization in SAP Build Work Zone, advanced edition.



The SAP Build Work Zone, advanced edition onboarding guide describes the “simplest” approach for user authentication and provisioning, using SAP Cloud Identity Services - Identity Authentication as the user management system, and SAP Cloud Identity Services - Identity Provisioning as the user provisioning system. However, other options are supported, based on your environment setup.



<a name="loiof04c185d689846908fb11d9a228392a2__section_kwg_mpg_5pb"/>

## User Authentication

The recommended setup is to connect directly to Identity Authentication and set up a trust between it and SAP Business Technology Platform using OpenID Connect. See [**Establish Trust and Federation Between UAA and Identity Authentication**](https://help.sap.com/docs/btp/sap-business-technology-platform/establish-trust-and-federation-between-uaa-and-identity-authentication). However, if your system is using a different IdP, you can use the Identity Authentication service as a proxy to another system rather than connect to the Identity Authentication service directly.

Customers that are using multiple IdPs can define which IdP will appear in the login screen.

To do that, the following environment variable of the approuter should be set to true: `DYNAMIC_IDENTITY_PROVIDER: true`. In this case, customers can set the identity provider \(IdP\) for the application’s login process by filling the request query parameter `sap_idp` with the IdP Origin Key.

For more information about this setup, see [Corporate Identity Providers](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/19f3eca47db643b6aad448b5dc1075ad.html)



<a name="loiof04c185d689846908fb11d9a228392a2__section_hyg_f4g_5pb"/>

## User Provisioning

SAP Build Work Zone, advanced edition requires users to be provisioned via the Identity Provisioning service. Depending on the your environment setup, you can provision your users from different source systems \(the Identity Authentication service or others\) to SAP Build Work Zone, advanced edition as a target system.

-   For more information about Identity Provisioning source systems, see [Source Systems](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/58033bec92124ef2a7905b37d0f50704.html) 
-   The Identity Provisioning target system must be SAP Build Work Zone, advanced edition. For more information about the parameter values that should be used, see [Onboarding to SAP Build Work Zone, advanced edition](onboarding-to-sap-build-work-zone-advanced-edition-f8c6eab.md)



<a name="loiof04c185d689846908fb11d9a228392a2__section_wh4_pqg_5pb"/>

## User Authorization

To be able to access SAP Build Work Zone, advanced edition, users must be assigned to one or more role collections on the subaccount level.

You can assign users to role collections in one of the following ways:

-   Manual assignment done in the SAP BTP cockpit. For more information, see [Assigning Role Collections](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/9e1bf57130ef466e8017eab298b40e5e.html)
-   Using assertion attribute mapping \(e.g. “Groups”\), as documented in the [Onboarding to SAP Build Work Zone, advanced edition](onboarding-to-sap-build-work-zone-advanced-edition-f8c6eab.md)
-   Using an API-based assignment of users \(e.g. via an Identity Provisioning target system\). For more information, see [Access Administration Using APIs of the SAP Authorization and Trust Management Service](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/dcb3bfd09c4b465e9d6f599485c5b6de.html)

> ### Note:  
> The default onboarding flow mentions specific user group names that are mapped to role collections in SAP BTP cockpit. Same mapping is done by the SAP Build Work Zone, advanced edition booster, which relies on those exact user groups names from Identity Authentication. If you wish to configure this differently, you can use different group names and map them to the role collections in SAP BTP cockpit. Those user groups can either be manually created in Identity Authentication or come from a corporate IdP \(Identity Authentication only acting as a proxy\).



<a name="loiof04c185d689846908fb11d9a228392a2__section_tgv_zrg_5pb"/>

## Exception! - External Users Self-Registration

If you plan to allow external users self-registration via external workspace invitations, you **must** use Identity Authentication.

In the self-registration scenario:

-   Users are created via self-registration in the Identity Authentication service.
-   The Identity Authentication service is used as the primary IdP.
-   Role collection is mapped based on an Identity Authentication attribute \(user type `public`\).
-   The Identity Provisioning service provisions user\(s\) directly from the Identity Authentication service as source system.

**Related Information**  


[Solution Architecture and Authentication Details](solution-architecture-and-authentication-details-1fd9ea4.md "Information about hostname patterns, trust setup, and authentication flows.")

[User and User List Provisioning Using SCIM API](user-and-user-list-provisioning-using-scim-api-6bd5237.md "This topic provides the information you need about SCIM API.")

[Manage Administrators Using SCIM API](manage-administrators-using-scim-api-ff793e6.md "In SAP Build Work Zone, advanced edition, you can manage the Company Administrator permissions using SCIM APIs.")

[Manage Custom Profile Attributes using SCIM API](manage-custom-profile-attributes-using-scim-api-796e3d9.md "Information about using custom attributes in the user profile.")

