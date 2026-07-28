<!-- loiod92cf2f5dfea4959beddc28b005da441 -->

# Content Providers - Cloud Solutions

An end-to-end process for integrating content from cloud solutions. This process is composed of a content exposure flow and a content consumption flow. Some steps might be slightly different between different content providers.



<a name="loiod92cf2f5dfea4959beddc28b005da441__section_vc3_lzf_3qb"/>

## Overview

The following solutions provide a tool for exposing their content to the SAP Build Work Zone, advanced edition:

-   SAP Integrated Business Planning for Supply Chain \(SAP IBP\)

-   SAP S/4HANA Cloud solution

-   SAP BTP ABAP environment


> ### Note:  
> For integrating content from cloud solutions, all systems must operate under the same domain.



## Content Exposure Flow

The content exposure flow involves setting up the communication between the content provider system and the SAP Build Work Zone, advanced edition, and exposing the roles that you want to integrate. You also need to configure a design-time destination from which the SAP Build Work Zone, advanced edition will fetch the exposed content.

The following table describes the steps that are required to set up the content exposure flow:


<table>
<tr>
<th valign="top">

System

</th>
<th valign="top">

Tool

</th>
<th valign="top">

Task

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

Content Provider System

</td>
<td valign="top">

*Communication Systems* app.

</td>
<td valign="top">

Communication systems are created to enable the communication among different systems.

</td>
<td valign="top">

-   SAP S/4HANA Cloud: [Manage Communication](https://help.sap.com/viewer/4fc8d03390c342da8a60f8ee387bca1a/latest/en-US/a01d59b0724c4fa499a7ff7299501801.html)
-   SAP IBP: [Manage Communication](https://help.sap.com/viewer/0292066056f642f1a0f6d9135e39abaf/2111/en-US/a01d59b0724c4fa499a7ff7299501801.html)
-   SAP BTP ABAP environment: [Manage Communication](https://help.sap.com/viewer/10fd1742ea914256abedb34bf15bd069/Cloud/en-US/a01d59b0724c4fa499a7ff7299501801.html)



</td>
</tr>
<tr>
<td valign="top">

Content Provider System

</td>
<td valign="top">

*Maintain Business Roles* app.

</td>
<td valign="top">

Select and expose the roles you want to integrate into SAP Build Work Zone, advanced edition.

> ### Note:  
> A single role, group, or catalog may not be assigned more than 3000 apps. Otherwise, you will not be able to create the content provider in the Channel Manager, as described below in the consumption flow.



</td>
<td valign="top">

-   SAP S/4HANA Cloud: [Select Roles for Exposure](https://help.sap.com/viewer/4fc8d03390c342da8a60f8ee387bca1a/latest/en-US/e0ba77cfec8b4b05ab8ccb163b914f67.html)
-   SAP IBP: [Select Roles for Exposure](https://help.sap.com/viewer/0292066056f642f1a0f6d9135e39abaf/2111/en-US/e0ba77cfec8b4b05ab8ccb163b914f67.html)
-   SAP BTP ABAP environment: [Select Roles for Exposure](https://help.sap.com/viewer/10fd1742ea914256abedb34bf15bd069/Cloud/en-US/e0ba77cfec8b4b05ab8ccb163b914f67.html)



</td>
</tr>
<tr>
<td valign="top">

SAP BTP

</td>
<td valign="top">

Cockpit

</td>
<td valign="top">

Create a design-time destination to define the location from which SAP Build Work Zone, standard edition should fetch the exposed content.

</td>
<td valign="top">

[Configure Destinations \(Cloud\)](configure-destinations-cloud-c381c6d.md)

</td>
</tr>
</table>



<a name="loiod92cf2f5dfea4959beddc28b005da441__section_myn_tty_qpb"/>

## Content Consumption Flow

After completing the content exposure flow, you need to go through the content consumption flow, at the end of which it will be possible to launch cloud applications from the SAP Build Work Zone, advanced edition.

The following table describes the steps that are required to set up the content consumption flow.


<table>
<tr>
<th valign="top">

System

</th>
<th valign="top">

Tool

</th>
<th valign="top">

Task

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

Prerequisite

</td>
<td valign="top">

Content Provider side

</td>
<td valign="top">

To run apps in an iFrame, you need to configure an allowlist - define secure applications by adding trusted hosts to the protection allowlist.

</td>
<td valign="top">

-   SAP S/4HANA Cloud: [Protect Against Clickjacking](https://help.sap.com/viewer/4fc8d03390c342da8a60f8ee387bca1a/latest/en-US/3d1ea8b1a0e145bb851d36d0da376e17.html)
-   SAP IBP: [Protect Against Clickjacking](https://help.sap.com/viewer/0292066056f642f1a0f6d9135e39abaf/latest/en-US/3d1ea8b1a0e145bb851d36d0da376e17.html)
-   SAP BTP ABAP environment: [Protect Against Clickjacking](https://help.sap.com/docs/BTP/10fd1742ea914256abedb34bf15bd069/3d1ea8b1a0e145bb851d36d0da376e17.html?version=Cloud)

> ### Note:  
> In case custom themes are used, it may be required that a CSS allowlist is configured additionally. For more information on CSS allowlist configuration, see [Configuring HTTP Context Types](https://help.sap.com/docs/SAP_NETWEAVER_AS_ABAP_751_IP/1ca554ffe75a4d44a7bb882b5454236f/ad6340c911164f639877e2dfb51d4b49.html?version=7.51.8).



</td>
</tr>
<tr>
<td valign="top">

Configure trust between the IdP and Identity Authentication, and between SAP BTP and Identity Authentication.

**Skip if the trust is already configured**

</td>
<td valign="top">

-   Identity Authentication
-   SAP BTP cockpit

tenant,

</td>
<td valign="top">

Configure trust between the Corporate IdP, Identity Authentication, and SAP BTP to be able to use single-sign-on when authenticating users from cloud providers.

</td>
<td valign="top">

[Establish Trust](establish-trust-8d41d7e.md)

</td>
</tr>
<tr>
<td valign="top">

Configure destinations

</td>
<td valign="top">

SAP BTP cockpit

</td>
<td valign="top">

Configure a design-time destination to define the location from which to fetch the exposed content. In addition, configure a runtime destinations for launching the resources that are required to run the app.

</td>
<td valign="top">

[Configure Destinations \(Cloud\)](configure-destinations-cloud-c381c6d.md) 

</td>
</tr>
<tr>
<td valign="top">

Content Provider System

</td>
<td valign="top">

Content Provider side

</td>
<td valign="top">

Create a communication system.

</td>
<td valign="top">

-   SAP S/4HANA Cloud: [Configure Communication for the Content Consumption](https://help.sap.com/docs/SAP_S4HANA_CLOUD/4fc8d03390c342da8a60f8ee387bca1a/386f16bba3884924a4c54507fd5347c2.html)
-   SAP IBP: [Configure Communication for the Content Consumption](https://help.sap.com/viewer/0292066056f642f1a0f6d9135e39abaf/latest/en-US/386f16bba3884924a4c54507fd5347c2.html)
-   SAP BTP ABAP environment: [Configure Communication for the Content Consumption](https://help.sap.com/docs/BTP/10fd1742ea914256abedb34bf15bd069/386f16bba3884924a4c54507fd5347c2.html?version=Cloud)



</td>
</tr>
<tr>
<td valign="top">

SAP Build Work Zone, advanced edition

</td>
<td valign="top">

Channel Manager

</td>
<td valign="top">

Consume the exposed content \(roles\) by configuring a content provider for the cloud system, using the design-time and runtime destinations, and adding the roles to the subaccount.

</td>
<td valign="top">

[Manage Content Providers \(Cloud\)](manage-content-providers-cloud-3cf5238.md)

</td>
</tr>
<tr>
<td valign="top">

SAP Build Work Zone, advanced edition

</td>
<td valign="top">

Site Directory

</td>
<td valign="top">

In the Role Assignments editor, assign one or more roles/content channels to the site, to enable the users who are assigned to these roles, to access the site in the runtime.

</td>
<td valign="top">

[Assign Roles to Your Site](assign-roles-to-your-site-7afe670.md)

</td>
</tr>
<tr>
<td valign="top">

SAP BTP

</td>
<td valign="top">

SAP BTP cockpit

</td>
<td valign="top">

> ### Note:  
> This step is required only when using SAP BTP role mechanism to manage authorization. If you're using the Identity Provisioning service to manage authorization, you can skip this step.

Assign the role collections created on the platform to the corresponding cloud system users, by using the following email format: `<user alias>@example.com`

</td>
<td valign="top">

[Mapping Role Collections in the Subaccount](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/9e1bf57130ef466e8017eab298b40e5e.html)

</td>
</tr>
</table>

**Related Information**  


[Federation of Remote Content Providers](federation-of-remote-content-providers-fa46cc3.md "Learn how to integrate content from remote content providers.")

