<!-- loiob645e742dc01473f95e0e9411c1c1db2 -->

# Add Specific Roles to Your Subaccount Manually

The administrator can use the *Content Explorer* to select specific roles from remote content providers and add them to the list in the *Content Manager*.



<a name="loiob645e742dc01473f95e0e9411c1c1db2__section_lvr_w5p_xmb"/>

## Overview

> ### Note:  
> If the content provider was created with the *Automatically add all content items to subaccount* option enabled, all the roles were already selected and added when the content provider was created, and you can skip this procedure.
> 
> For more information, see [Manage Content Providers \(On Premise\)](manage-content-providers-on-premise-021bc11.md).

When you define a remote content provider in the Channel Manager with the *Automatically add all content items to subaccount* option disabled, you need to select the roles that you want to add to the list in the *Content Manager*.

When the option *Use the Identity Provisioning service to provision user authorizations* is not selected, for every role that you add, a corresponding role collection is automatically created in the SAP BTP cockpit, using the following values:

-   Platform role name - <role ID\>

-   Platform role description - <role title\>-<role description, if exists\>




<a name="loiob645e742dc01473f95e0e9411c1c1db2__section_dpn_pr5_3lb"/>

## Procedure

1.  In the *Content Explorer*, select the content provider you defined. The roles that it contains are displayed in a table.

    > ### Note:  
    > Click a role to open the Role editor in view mode, to see in the *Assignments* panel the list of apps that are assigned to this role.

2.  Select the roles you want and click *Add*.


The roles are integrated in the list in the *Content Manager*. Click a role to view the list of apps assigned to it.

The groups and catalogs are not visible in the *Content Manager* at all, but they will be visible in the runtime site.

