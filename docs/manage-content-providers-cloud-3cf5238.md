<!-- loio3cf52387374d4f91892e48c5fc3c4a01 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Manage Content Providers \(Cloud\)

The administrator uses the Channel Manager to define, edit, and get updates from remote content providers running on cloud.



<a name="loio3cf52387374d4f91892e48c5fc3c4a01__section_ind_3xs_ylb"/>

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

When this option is **enabled** \(default\), as a result of creating the content provider, all the content items are auomatically selected in the *Content Explorer* and added to the *Content Manager*. When updating a provider, all the new content items are also automatically added.

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

-   Enable this option to use the Identity Provisioning service to synchronize identities and their authorizations from the provider's IdP to SAP Build Work Zone, advanced edition. Enabling this option will prevent the creation of role collections in SAP BTP as they are not required when provisioning the authorizations from the IdP.

    To use this option, you need to configure the SAP Build Work Zone, standard edition connector in your Identity Provisioning tenant \(in addition to the SAP Build Work Zone, advanced edition connector\). For more information, see [Connect your subaccount to Identity Provisioning \(optional step\)](https://help.sap.com/docs/build-work-zone-advanced-edition/sap-build-work-zone-advanced-edition/post-booster-configuration#connect-your-subaccount-to-identity-provisioning).

-   Disable this option if you want to manage the provider authorizations locally on SAP BTP.


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
</table>



<a name="loio3cf52387374d4f91892e48c5fc3c4a01__section_a4b_5q5_3lb"/>

## Define a Content Provider

**Prerequisites**

You've configured in the cockpit:

-   The design-time destination

-   The default runtime destination

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

4.  If the runtime destination for dynamic data is different than the default runtime destination, select it from the *Runtime Destination for Dynamic Data* list.

5.  Select the *Content Scope* to determine the content that will be federated - roles and related content or apps only.

6.  Disable the *Automatically add all content items to subaccount* if you want to manually select the desired content items in the *Content Explorer* and add them to the *Content Manager*.

7.  Select the optional settings for synchronizing authorization and including catalog and group assignments based on your scenario.

8.  *Save*.

    A new row is added to the *Content Channels* table, with the status “Creating…”.

    When the content provider is ready, the status changes to “Created”.

    Click the *Report* link to see the number of roles, apps, groups, catalogs, spaces, pages, and URL templates that are included in the content provider.


The content provider is now visible also in the *Content Explorer*.

> ### Note:  
> -   All content that is exposed on the provider's side is created on the SAP Business Technology Platform at the time the content provider is created.
> -   For every content provider, a unique set of content is created, even if different content providers are pointing to the same remote system.



<a name="loio3cf52387374d4f91892e48c5fc3c4a01__section_utc_g11_zlb"/>

## Edit a Content Provider

You use the :pencil2: option if you want to:

-   Change the title or the description of a provider.

-   Change the state of the *Automatically add all content items to subaccount* option:

    -   From disabled to enabled – All the content items that weren't added yet, are automatically selected in the *Content Explorer* and added to the *Content Manager*.

    -   From enabled to disabled – There's no change in the content. In future updates, new content won't be added automatically.


-   Editing the setting of *Use the Identity Provisioning service to provision user authorizations* is not supported. If you want to use the Identity Provisioning service to sync authorizations, do as follows:

    1.  Create a new provider with a new provider ID, and enable the option *Use the Identity Provisioning service to provision user authorizations*.
    2.  Sync users and authorizations from source to target using the Identity Provisioning service.
    3.  In the *Content Explorer*, add the roles from the new content provider to the *Content Manager*.
    4.  Assign the roles from the new content provider to the site.
    5.  Delete the old content provider. This action will delete all the role collections that were previously created in the SAP BTP cockpit.




<a name="loio3cf52387374d4f91892e48c5fc3c4a01__section_aps_5ys_ylb"/>

## Update the Content of a Provider

If the content was changed in the source system, use the :arrows_clockwise: option to fetch the updated content that was exposed.

Following an update:

-   The report reflects the changes done as a result of the update.

-   When the *Automatically add all content items to subaccount* option is enabled, all new content items are automatically selected in the *Content Explorer* and added to the list in the *Content Manager*.


> ### Note:  
> When a role is removed from the content exposed by a content provider, as a result of updating the content provider in the *Channel Manager*, the role is also removed from the *Content Explorer*, the *Content Manager*, and from any sites to which it was assigned. However, this information is maintained. This means that if the role is added once again to the exposed content on the content provider side, it reappears in the *Content Explorer*, the *Content Manager*, and it will be assigned again to the same sites.

**Related Information**  


[Additional Settings - Cloud and On-Premise Solutions](additional-settings-cloud-and-on-premise-solutions-63867df.md "Additional settings and configurations that are relevant for cloud and on-premise content providers.")

