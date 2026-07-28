<!-- loioa12a0028857f4586b43164a81152fbf4 -->

# Content Providers - On-Premise Solutions

An overview of the end-to-end process for integrating content from on-premise solutions.



<a name="loioa12a0028857f4586b43164a81152fbf4__section_pfdb_wml_xnc_cnb"/>

## Overview

The following solutions provide a tool for exposing their content to the SAP Build Work Zone, advanced edition:

-   SAP S/4HANA

-   SAP Business Suite

-   SAP Enterprise Portal




### Additional Info

-   The integration of SAP S/4HANA content includes support for SAP Smart Business tiles. For information about the behavior of these tiles at runtime, see [Tile Analysis](https://help.sap.com/viewer/6b356c79dea443c4bbeeaf0865e04207/2020.001/en-US/f7b5426c0b134be5aec97bf71883afaa.html).

-   In runtime, when launching an SAP Enterprise Portal tile, it opens the application in a new tab.




## End-To-End Process

The end-to-end process includes the following steps:


<table>
<tr>
<th valign="top">

Step

</th>
<th valign="top">

Description

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

0. Prerequisite

</td>
<td valign="top">

To run apps in an iFrame, you need to configure an allowlist - define secure applications by adding trusted hosts to the protection allowlist.

</td>
<td valign="top">

For more information, see [S/4HANA: Protecting Against Clickjacking](http://help.sap.com/docs/CIAS%20FES%202020/ecb81b5bfce440ca8e7e7c9ad58fcf3a/981311d8f8b34c00b28c0670a4194de3.html)

> ### Note:  
> In case custom themes are used, it may be required that a CSS allowlist is configured additionally. For more information on CSS allowlist configuration, see [Configuring HTTP Context Types](https://help.sap.com/docs/SAP_NETWEAVER_AS_ABAP_751_IP/1ca554ffe75a4d44a7bb882b5454236f/ad6340c911164f639877e2dfb51d4b49.html?version=7.51.8).



</td>
</tr>
<tr>
<td valign="top">

1. Expose the Roles from the Content Provider

</td>
<td valign="top">

In the content exposure tool of the content provider, select and expose the roles that you want to integrate in the SAP Build Work Zone, advanced edition.

> ### Note:  
> Composite and derived PFCG roles are supported at runtime and can be exposed too. However, they are not visible in the Content Manager.

> ### Note:  
> A single role, group, or catalog may not be assigned more than 3000 apps. Otherwise, you will not be able to create the content provider in the Channel Manager, as described below in step 3.



</td>
<td valign="top">

For more information about SAP S/4HANA and SAP Business Suite, see [Exposing Launchpad Content to SAP BTP](https://help.sap.com/docs/ABAP_PLATFORM_NEW/a7b390faab1140c087b8926571e942b7/8216497368a9417f8008db8eb63fab72.html?version=Latest).

For information about SAP Enterprise Portal, see [Enterprise Portal as a Content Provider to SAP BTP](https://help.sap.com/viewer/40fb2965584a448a996f1e1aa3e3c08d/7.5.19/en-US/3199ba8b24244b32bce08cbe7fff7dd3.html).

</td>
</tr>
<tr>
<td valign="top">

2. Configure Destinations

</td>
<td valign="top">

In the SAP BTP cockpit, configure a design-time destination and one or more runtime destinations.

</td>
<td valign="top">

[Configure Destinations \(On Premise\)](configure-destinations-on-premise-f337b80.md) 

</td>
</tr>
<tr>
<td valign="top">

3. Define a Content Provider and Add Roles to Your Subaccount

</td>
<td valign="top">

In the Channel Manager, define the content provider.

When enabled, the *Automatically add all content items to subaccount* option automatically selects and adds all the roles to the *Content Manager* when the provider is created or updated.

When this option is disabled, after the provider is created or updated, you need to manually select specific roles in the *Content Explorer* and add them to the *Content Manager*.

> ### Note:  
> When the option *Use the Identity Provisioning service to provision user authorizations* is not selected, the roles are managed in the SAP BTP cockpit. In this case, for every role that is added to the *Content Manager*, a corresponding role collection is automatically created in the cockpit, with the following name: `<provider ID>_<provider role name>`



</td>
<td valign="top">

[Manage Content Providers \(On Premise\)](manage-content-providers-on-premise-021bc11.md)

[Add Specific Roles to Your Subaccount Manually](add-specific-roles-to-your-subaccount-manually-b645e74.md)

</td>
</tr>
<tr>
<td valign="top">

4. Assign Role Collections to Users

</td>
<td valign="top">

If the option *Use the Identity Provisioning service to provision user authorizations* is not selected, assign the role collections in the cockpit, under *Security* \> *Role Collections*, to the relevant end users, including the administrator. This enables them to view and access the related apps in the runtime site.

</td>
<td valign="top">

[Directly Assign Role Collections to Users](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/a55a3feb7dca464dbb333dc66d2416ad.html?q=trust%20configuration) 

</td>
</tr>
<tr>
<td valign="top">

5. Assign Roles to Sites

</td>
<td valign="top">

In the Role Assignments editor, assign one or more roles/content channels to the site, to enable the users who are assigned to these roles, to access the site in the runtime.

</td>
<td valign="top">

[Assign Roles to Your Site](assign-roles-to-your-site-7afe670.md) 

</td>
</tr>
</table>

**Related Information**  


[Federation of Remote Content Providers](federation-of-remote-content-providers-fa46cc3.md "Learn how to integrate content from remote content providers.")

