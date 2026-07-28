<!-- loio1fd9ea4f7051499db52b2dc086b86b54 -->

# Solution Architecture

Information about SAP Build Work Zone, advanced edition architecture, as well as hostname patterns, trust setup, and authentication flows.



## Overview

SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone are SAP BTP offerings available on a multi-cloud environment. Since the decoupling of SAP SuccessFactors Work Zone from SAP SuccessFactors HXM Core \(BizX\) in February 2022 \(see note [3111415](https://me.sap.com/notes/3111415)\), and the use of SAP Cloud Identity Services for user authentication and provisioning, there are no technical or architectural differences between them.

Since the beginning of 2023, the HR content packages that were previously available only in SAP SuccessFactors Work Zone are also available in SAP Build Work Zone, advanced edition. Therefore, the only difference between the two services is that SAP SuccessFactors Work Zone comes as a solution bundle with additional SAP BTP services included, whereas SAP Build Work Zone, advanced edition is a standalone service that can be integrated with others through the platform.



<a name="loio1fd9ea4f7051499db52b2dc086b86b54__section_ihc_g1c_n1c"/>

## Components

SAP Build Work Zone, advanced edition consists or the following components:


<table>
<tr>
<th valign="top">

Type

</th>
<th valign="top">

Name

</th>
<th valign="top">

Related Capabilities

</th>
</tr>
<tr>
<td valign="top" rowspan="4">

Default Components

</td>
<td valign="top">

Digital Workplace Service \(DWS\)

</td>
<td valign="top">

DWS covers all the features that are available in the Administration Console, such as company and area administration, workspaces and workpages, user management, external integrations, and many more.

DWS provides an OData API to work with its content: workspaces, workpages, feeds, forums, knowledge articles, etc.

</td>
</tr>
<tr>
<td valign="top">

SAP Build Work Zone, advanced edition subscription \(SaaS\)

</td>
<td valign="top">

Covers the tenant-level settings such as content management, channel management, and subaccount settings, as well as the site settings. Required for the federation of SAP and third-party business applications from SAP BTP and remote content providers. The tenant and site-level settings are managed from the Site Manager editors.

> ### Note:  
> To be able to access SAP and third-party business applications, both the Connectivity service and the Destination service are being used. These services, which are part of the SAP BTP platform, are used to pass requests to other systems as well as handle the authentication between the remote application and DWS \(through the predefined "JAM" destination\).



</td>
</tr>
<tr>
<td valign="top">

SAP Mobile Services

</td>
<td valign="top">

Provides a native mobile application to access SAP Build Work Zone, advanced edition.

</td>
</tr>
<tr>
<td valign="top">

UI Theme Designer

</td>
<td valign="top">

Enables you to create custom themes and customize the site branding.

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Mandatory components

</td>
<td valign="top">

SAP Cloud Identity Services - Identity Authentication

</td>
<td valign="top">

The Identity Authentication service can be used as the primary IdP or as a proxy between an SAP or third-party corporate IdP and SAP Build Work Zone, advanced edition.

</td>
</tr>
<tr>
<td valign="top">

SAP Cloud Identity Services - Identity Provisioning

</td>
<td valign="top">

Identity Provisioning is used to extract users’ information from a source system, such as SAP SuccessFactors or Microsoft Azure Active Directory, transform it, and then create or update users’ profiles in DWS. DWS exposes a REST API based on the System for Cross-domain Identity Management \(SCIM 2.0\) specification for this purpose.

> ### Note:  
> While the Identity Provisioning is a mandatory setup for provisioning users and their authorizations from a source system, it is optional to use it to provision roles when federating content from remote content providers.



</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Optional components

</td>
<td valign="top">

SAP Business Application Studio

</td>
<td valign="top">

A dedicated plugin, "Development Tools for SAP Build Work Zone", is available in SAP Business Application Studio. The plugin can be used to develop UI integration cards and content packages.

</td>
</tr>
<tr>
<td valign="top">

SAP Build Apps

</td>
<td valign="top">

A low-code development platform to create apps for the Web and native mobile use.

</td>
</tr>
<tr>
<td valign="top">

SAP Build Process Automation

</td>
<td valign="top">

This component replaces the SAP Workflow service and is used for creating workflows and guided processes. You can choose to include this service when running the onboarding booster or add it later.

</td>
</tr>
<tr>
<td valign="top">

SAP Notification service

</td>
<td valign="top">

Displays notifications from different providers on SAP BTP in one viewer. You can choose to use the SAP Notification service or keep the default notification mechanism that shows only SAP Build Work Zone, advanced edition notifications.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

SAP Task Center

</td>
<td valign="top">

The integration with SAP Task Center allows you to see any tasks that were created in a workspace in the SAP Task Center UI.

</td>
</tr>
</table>



<a name="loio1fd9ea4f7051499db52b2dc086b86b54__section_asx_qnc_n1c"/>

## Service plan configuration

The onboarding process to SAP Build Work Zone, advanced edition/SAP SuccessFactors Work Zone, creates the necessary assignments to service plans.

For more information about the available service plans, see [Service Plans and Metering](service-plans-and-metering-0b00752.md).

> ### Note:  
> In the China region, the subscription commercial model, which is applicable to SAP Build Work Zone, advanced edition, is not available. Therefore, only the SAP SuccessFactors Work Zone service plans should be used.

In addition to SAP Build Work Zone, advanced edition/SAP SuccessFactors Work Zone service plans, the following assignments are also configured:


<table>
<tr>
<th valign="top">

Service

</th>
<th valign="top">

Plan

</th>
<th valign="top">

Type

</th>
</tr>
<tr>
<td valign="top">

\[Optional\] SAP Business Application Studio

</td>
<td valign="top">

`standard_edition (Application)`

</td>
<td valign="top">

Subscription

Contains a dedicated extension "Development tools for SAP Build Work Zone", which allows development of content packages and UI Integration Cards.

</td>
</tr>
<tr>
<td valign="top">

\[Optional\] SAP Build Process Automation

</td>
<td valign="top">

`standard`, `advanced-user`

</td>
<td valign="top">

Subscription

Allows you to adapt, improve, and innovate business processes with no-code workflow management and robotic process automation capabilities.

</td>
</tr>
</table>

> ### Note:  
> Unlike other SAP BTP services, it's not enough to manually subscribe to the service in order to access it. To complete the onboarding process successfully, all onboarding steps must be followed meticulously. For more information, see [Initial Setup](initial-setup-c8e3eb2.md).



<a name="loio1fd9ea4f7051499db52b2dc086b86b54__section_j3y_vsk_4tb"/>

## Hostname Pattern

The following components have a dedicated hostname pattern:

1.  The SAP BTP subscription has the following URL pattern:

    https://<SAP BTP subaccount domain\>.<type\>.cfapps.<SAP BTP subaccount region\>.hana.ondemand.com

    **<type\>**: `workzone` for SAP Build Work Zone, advanced edition or `workzonehr` for SAP SuccessFactors Work Zone.

2.  The DWS component is seamlessly integrated into the subscription as an iframe \(transparent to the end-user\), and has the following URL pattern:

    https://<unique subdomain\>.<DWS region\>.workzone.ondemand.com

    **<Unique subdomain\>**: this will either be automatically generated when creating a new tenant or handled by SAP Support when migrating an existing SAP Jam tenant.

    **<DWS region\>**: this will follow the pattern of coreXX, when XX = data center region. For example, DC12 will be core12.


> ### Note:  
> You can easily locate the subscription and DWS URLs as follows:
> 
> -   The subscription URL is what you use to access the service.
> -   The DWS URL is available in the Admin Console *Overview* screen. It's the value of the *Custom Domain* field.



<a name="loio1fd9ea4f7051499db52b2dc086b86b54__section_zzn_5nz_lyb"/>

## URL Patterns



### DWS iframe URL pattern:

`https://[subaccount domain].workzone.ondemand.com/groups/[placeholder 1]/documents/[placeholder 2]`



### The previous URL will automatically redirect to the connected Work Zone shell / URL:

`https://[subaccount domain].workzone*.cfapps.[data center].hana.ondemand.com/[navigation intent]/groups/[placeholder 1]/documents/[placeholder2]`

\* **workzone** for SAP Build Work Zone, advanced edition or **workzonehr** for SAP SuccessFactors Work Zone.



### SAP Jam Migration

If the tenant has been migrated from SAP Jam to DWS, the URL will change as follows:

**Original SAP Jam URL\*\*:** `https://[SAP Jam DC].sapjam.com/groups/[placeholder 1]/documents/[placeholder 2]`

\*\* The first part of the URL up until 'groups' can be a custom subdomain or a full custom domain, depending on the customer setup.

**URL after migration:** `https://[subaccount domain].workzone.ondemand.com/groups/[placeholder 1]/documents/[placeholder 2]`

**Additional Info:**

-   **Placeholder 1** - workspace ID \(22-digit\) unique and stable for this workspace, remains the same after renaming, moving location, etc.
-   **Placeholder 2** - document ID \(22-digit\) unique and stable for this document, remains the same after renaming, uploading of new version, etc.
-   When navigating within the site, the URL also contains the relative path to the content, such as a specific workpage, forum, profile, etc., but it always follows the 22-digit pattern for the IDs.
-   When navigating within the site, the URL uses a navigation intent such as workzone-home or workzone-admin. A navigation intent is a unique combination of a semantic object and an action that is used to define navigation to an application. At runtime, the application navigation targets are resolved into actual URLs.

> ### Note:  
> These IDs are also required for the OData APIs: `https://jam2.sapjam.com/work_zone/ODataDocs/ui` 



<a name="loio1fd9ea4f7051499db52b2dc086b86b54__section_c2m_cvk_4tb"/>

## Trust Setup and Authentication Flows

You must configure SAP Cloud Identity Services - Identity Authentication as the primary IdP, whether you connect to it directly, or whether you use it as a proxy between a corporate IdP andSAP Build Work Zone, advanced edition.

You need to configure two levels of trust:

-   A trust in the subaccount level between SAP BTP and Identity Authentication, using Open ID Connect \(OIDC\) protocol. This is done during the onboarding process, see [Prerequisites](prerequisites-9e78b62.md).
-   A trust between Identity Authentication and DWS that runs as in iframe inside SAP Build Work Zone, advanced edition. This trust is using SAML2-based assertion attributes.

    The DWS trust is a fallback mechanism. When a user accesses any link pointing to SAP Build Work Zone, advanced edition, the OIDC trust between the subaccount and the Identity Authentication \(and optionally connected IdP\) is leveraged. In contrast, the authentication for DWS is done via a `single_use_token` , generated via an API call through the “JAM” destination with an `OAuth2SAMLBearerAssertion` as an authentication mechanism.




### Authentication on the SAP BTP side

The information configured for this trust setup impacts the user attributes. The following two properties should be reviewed in the “JAM” destination. By default, they are created as follows:

```
nameIdFormat = urn:oasis:names:tc:SAML:1.1:nameid-format:unspecified
userIdSource = user_uuid
```



### Authentication on the Identity Authentication side

The `userIdSource` property in the “JAM” destination refers to the assertion attributes configured in Identity Authentication and/or the connected IdP. The same mechanism is used for other destinations such as the HR content package of SAP SuccessFactors Work Zone. For more information, see [Creating Destinations to SAP SuccessFactors](https://help.sap.com/docs/SAP_SUCCESSFACTORS_WORK_ZONE/04877e17a5da4908a6fea94949e160b5/c12996ba62d34dfba5ae042fb925add2.html)



### Authentication on the DWS side

The `single_use_token` generated via an API call can be successful only when the “JAM” destination properties match the configured *SAML Trusted IdP*, which is configured automatically by the onboarding configurator. By default, it refers to the `SCIM.userName` attribute in the user record, but it can alternatively also connect to either the `SCIM.externalId` attribute or the `SCIM.emails.value` attribute to find a unique user. When the `SCIM.emails.value` is used, the `nameIdFormat` property in the “JAM” destination as well as the trusted IdP need to be adjusted accordingly.

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
> If the API call to create the `single_use_token` fails for some reason, the DWS - Identity Authentication trust based on SAML2 is leveraged. In this case, the *Subject Name Identifier* configured in Identity Authentication for the DWS \(and not the one for the SAP BTP subaccount!\) needs to match the `SCIM.userName` in the user record.

