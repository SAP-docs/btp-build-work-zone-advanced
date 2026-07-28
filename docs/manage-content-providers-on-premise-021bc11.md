<!-- loio021bc1192cbd455d898542dcf584440e -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Manage Content Providers \(On Premise\)

The administrator uses the Channel Manager to define, edit, and get updates from remote content providers running on premise.



<a name="loio021bc1192cbd455d898542dcf584440e__section_ind_3xs_ylb"/>

## Overview

The Channel Manager is used to manage remote content providers. Once the administrator defines a content provider, it's also added to the Content Explorer. The Content Explorer displays the roles or apps in each remote provider. Clicking a role displays the list of apps assigned to it.

The following table provides an overview of the steps required to define a remote content provider:


<table>
<tr>
<th valign="top">

Step

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

Enter a title

</td>
<td valign="top">

Mandatory

</td>
</tr>
<tr>
<td valign="top">

Enter a description

</td>
<td valign="top">

Optional

</td>
</tr>
<tr>
<td valign="top">

Specify a unique ID

</td>
<td valign="top">

The provider title is copied by default to the ID field. The ID must be unique within a subaccount.

> ### Note:  
> When transporting content between landscapes \(dev, test, prod\) the ID of the content provider in the target landscape must be identical to the ID in the source landscape.



</td>
</tr>
<tr>
<td valign="top">

Select a design-time destination

</td>
<td valign="top">

The design-time destination defines the location from which to fetch the content that was exposed by the content provider.

</td>
</tr>
<tr>
<td valign="top">

Select a runtime destination

</td>
<td valign="top">

The default runtime destination defines the location from which to obtain the resources needed to run the federated apps in runtime.

</td>
</tr>
<tr>
<td valign="top">

Select a runtime destination for dynamic data

</td>
<td valign="top">

The runtime destination for retrieving dynamic data to display on dynamic tiles. By default, the default runtime destination is used.

</td>
</tr>
<tr>
<td valign="top">

Select the content scope

</td>
<td valign="top">

The scope of the content items that will be federated:


<table>
<tr>
<th valign="top">

Option

</th>
<th valign="top">

Scope

</th>
<th valign="top">

Admin Capabilities

</th>
</tr>
<tr>
<td valign="top">

*Roles and related content*

</td>
<td valign="top">

This is the **full content scope**, which includes the apps assigned to the roles, as well as the catalogs, groups, pages \(and spaces\) to which the apps are assigned.

This scope defines the content and the layout \(groups, pages, spaces\) of how the apps will be used in runtime.

</td>
<td valign="top">

The content provider has full control of the usage of the federated content.

The federated content cannot be modified by the admin

</td>
</tr>
<tr>
<td valign="top">

*Apps only*

</td>
<td valign="top">

This scope includes **apps only**, without any roles or other content.

</td>
<td valign="top">

The admin has full control of the usage of the federated apps. The admin needs to configure local content, such as roles, pages, and spaces, and then assign the apps to this content. For example, it is possible to assign apps from different content providers to the same page.

</td>
</tr>
</table>



</td>
</tr>
<tr>
<td valign="top">

Select the content addition mode using the *Automatically add all content items to subaccount* toggle

</td>
<td valign="top">

When this option is **enabled** \(default\), as a result of creating the content provider, all the content items are automatically selected in the *Content Explorer* and added to the *Content Manager*. When updating a provider, all the new content items are also automatically added.

When this option is **disabled**, after creating or updating the content provider, you need to manually select the desired content items in the *Content Explorer* and add them to the *Content Manager*.

> ### Note:  
> When not using the Identity Provisioning service \(see the following row in this table\), for every role that you add \(automatically or manualy\) to the Content Manager, a corresponding role collection is automatically created in the SAP BTP cockpit, using the following values:
> 
> -   Role collection name - <ID of role in Content Manager\>
> 
>     The <ID of role in Content Manager\> is composed as follows: `~<provider ID>_<role ID>`
> 
>     For example: `~provider1_EMPLOYEE`
> 
> -   Role collection description - <role title\>-<role description, if exists\>
> 
> 
> For restrictions related to the number of role collections allowed, see [General Restrictions](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/restrictions-general#general-restrictions).



</td>
</tr>
<tr>
<td valign="top">

Select the authorization synchronization option using the *Use the Identity Provisioning service to provision user authorizations* toggle.

</td>
<td valign="top">

-   Enable this feature to use the Identity Provisioning service to synchronize identities and their authorizations from the provider's IdP to . Enabling this option will prevent the creation of role collections in SAP BTP as they are not required when provisioning the authorizations from the IdP.

    To use this option, you need to configure the SAP Build Work Zone, standard edition connector in your Identity Provisioning tenant \(in addition to the SAP Build Work Zone, advanced edition connector\). For more information, see [Connect your subaccount to Identity Provisioning \(optional step\)](https://help.sap.com/docs/build-work-zone-advanced-edition/sap-build-work-zone-advanced-edition/post-booster-configuration#connect-your-subaccount-to-identity-provisioning).

-   Disable this feature if you want to manage the provider authorizations locally on SAP BTP.


> ### Note:  
> Enabling this option on existing providers is not supported. To use this capability, you must define a new provider. See instructions in the "Edit Content Provider" section below.



</td>
</tr>
<tr>
<td valign="top">

Use *Include group and catalog assignments to role* toggle switch depending on how the provider is modeled.

</td>
<td valign="top">

-   Disable this feature to include all groups and catalogs in this site, without considering their assignment to roles.

-   Enable this feature to include only groups and catalogs in this site, that have been directly assigned to roles.


For more information, see [Defining Optional Relations Between Roles and Groups/Catalogs](defining-optional-relations-between-roles-and-groups-catalogs-215517e.md)

</td>
</tr>
<tr>
<td valign="top">

Map aliases to runtime destinations \(SAP S/4HANA and SAP Business Suite only\)

</td>
<td valign="top">

This step is relevant only when the SAP Fiori front-end server is deployed in a hub deployment, with separate back-end systems, each with its own alias. You map aliases after the content provider has been created.

</td>
</tr>
</table>



<a name="loio021bc1192cbd455d898542dcf584440e__section_a4b_5q5_3lb"/>

## Define a Content Provider

**Prerequisites**

You've configured in the cockpit:

-   The design-time destination.
-   One or more default runtime destinations.
-   A runtime destination for retrieving dynamic data. \(Optional\)

**Procedure**

1.  In the Channel Manager, click *New*.

2.  In the *New Content Provider* dialog box, specify a title for the provider.

    > ### Note:  
    > The provider ID is identical to the provider title by default, but the administrator can change it. The ID can contain up to 20 alphanumeric characters, dots, or underscores.
    > 
    > The provider ID is used as a prefix \(preceded by the ~ sign\) for the ID of the roles you add to the Content Manager.
    > 
    > When transporting sites and content between landscapes, the ID **must be identical in all landscapes**.

3.  Select the design-time destination and \(default\) runtime destination that were configured in the cockpit.

4.  If the runtime destination for retrieving dynamic data is different than the default runtime destination, select it from the *Runtime Destination for Dynamic Data* list.

5.  Select the *Content Scope* to determine the content that will be federated - roles and related content or apps only.

6.  Disable the *Automatically add all content items to subaccount* if you want to manually select the desired content items in the *Content Explorer* and add them to the *Content Manager*.

7.  *Save*.

    A new row is added to the *Content Channels* table, with the status “Creating…”.

    When the content provider is ready, the status changes to “Created”.

    Click the *Report* link to see the number of roles, apps, groups, catalogs, spaces, pages, and URL templates that are included in the content provider.


The content provider is now visible also in the *Content Explorer*.

> ### Note:  
> -   All content that is exposed on the provider's side is created on SAP BTP at the time the content provider is created.
> -   For every content provider, a unique set of content is created, even if different content providers are pointing to the same remote system.



<a name="loio021bc1192cbd455d898542dcf584440e__section_kx3_rcj_ylb"/>

## Map Aliases for the Runtime Destinations \(SAP S/4HANA and SAP Business Suite only\)

> ### Note:  
> This step is relevant only in a Hub deployment of the SAP Fiori front-end server.

The following deployment options are available to set up the SAP Fiori front-end server:

-   Embedded deployment \(recommended\) - the SAP Fiori front-end server is deployed into the AS ABAP of a back-end system.

    > ### Note:  
    > In an embedded deployment, before exposing the content, the ABAP system administrator needs to set the value of the customizing parameter `EXPOSURE_SYSTEM_ALIASES_MODE` to `CLEAR`. For more information, see [Launchpad Configuration Parameters](https://help.sap.com/viewer/a7b390faab1140c087b8926571e942b7/latest/en-US/6107ee41f89a43c9af0aa279fe039cca.html).

-   Hub deployment for separate back-end systems - a dedicated AS ABAP front-end server with an SAP Fiori front-end server is deployed in a standalone system in front of the back-end systems, either behind or in front of the firewall.


For more information, see [Deployment Options](https://help.sap.com/viewer/22bbe89ef68b4d0e98d05f0d56a7f6c8/latest/en-US/4cca4152fc94b610e10000000a44176d.html).

In a hub deployment, each back-end system may have several aliases. You need to create a runtime destination for each back-end system. Then, using the *Alias Mapping* dialog, which lists all the available aliases that were derived from the content exposed by the provider, map the relevant aliases to the corresponding runtime destinations.

**Procedure**

1.  Click *Map aliases* in the *Status* column.

2.  From the list of *Available Aliases*, select the aliases that belong to a specific runtime destination.

3.  Select the corresponding runtime destination from the dropdown list, and click :heavy_plus_sign:.

    A row of the aliases mapped to the selected runtime destination is added to the *Mapped Aliases* list.

4.  If a specific alias doesn't appear in the list of *Available Aliases*, use the *Enter a New Alias* link to add it manually and map it to the corresponding runtime destination.

5.  When you've mapped all the aliases, *Save*. This action populates the mapping details to the runtime sites.




<a name="loio021bc1192cbd455d898542dcf584440e__section_utc_g11_zlb"/>

## Edit a Content Provider

You use the :pencil2: option if you want to:

-   Change the title or the description of a provider.

-   Change the state of the *Automatically add all content items to subaccount* option:

    -   From disabled to enabled – All the content items that weren't added yet, are automatically selected in the *Content Explorer* and added to the *Content Manager*.

    -   From enabled to disabled – There's no change in the content. In future updates, new content won't be added automatically.


-   Editing the setting of *Use the Identity Provisioning service to provision user authorizations* is not supported. If you want to use the Identity Provisioning service to sync authorizations, do as follows:

    1.  Create a new provider with a new provider ID, and enable the option *Use the Identity Provisioning service to provision user authorizations*.
    2.  Sync users and authorizations from source to target using the Identity Provisioning service.
    3.  In the*Content Explorer*, add the roles from the new content provider to the *Content Manager*.
    4.  Assign the roles from the new content provider to the site.
    5.  Delete the old content provider. This action will delete all the role collections that were previously created in the SAP BTP cockpit.




<a name="loio021bc1192cbd455d898542dcf584440e__section_aps_5ys_ylb"/>

## Update the Content of a Provider

The Channel Manager enables the administrator to manually update a content provider following changes that were made to the content exposed by the provider.

> ### Note:  
> When federating content from SAP Enterprise Portal or from ABAP-based backends, it is possible to set up automatic updates. For more information, see [Set Up Automatic Updates for an SAP Enterprise Portal Content Provider](set-up-automatic-updates-for-an-sap-enterprise-portal-content-provider-232b6da.md) and [Set Up Automatic Updates for Content Providers](set-up-automatic-updates-for-content-providers-b5f4f4e.md).

Use the :arrows_clockwise: action to fetch the updated content that was exposed.

Following an update:

-   The report reflects the changes done as a result of the update.

-   When the *Automatically add all content items to subaccount* option is enabled, all new content items are automatically selected in the *Content Explorer* and added to the list in the *Content Manager*.


> ### Note:  
> When a role is removed from the content exposed by a content provider, as a result of updating the content provider in the *Channel Manager*, the role is also removed from the *Content Explorer*, the *Content Manager*, and from any sites to which it was assigned. However, this information is maintained. This means that if the role is added once again to the exposed content on the content provider side, it reappears in the *Content Explorer*, the *Content Manager*, and it will be assigned again to the same sites.

**Related Information**  


[Additional Settings - Cloud and On-Premise Solutions](additional-settings-cloud-and-on-premise-solutions-63867df.md "Additional settings and configurations that are relevant for cloud and on-premise content providers.")

