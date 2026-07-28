<!-- copy1410900702044af3bef46687bf7e148b -->

# Assign Content to a Role

When creating a role, you need to assign it to content to enable role-based access to the content and to the site.



<a name="copy1410900702044af3bef46687bf7e148b__section_ec5_lmr_mgc"/>

## Introduction

An *Everyone* role is provided out-of-the-box for each subaccount. Items assigned to this role are visible to all users in all the sites in the subaccount. The *Everyone* role does not have a corresponding role collection and is assigned to all users implicitly. You can also create a role.

When you create a role, a corresponding role collection is created in the SAP BTP cockpit, using the following values:

-   Platform role name - `<role ID>`

-   Platform role description - `<role title>-<role description`, if exists\>




## Create a Role

Create a local role as follows:

1.  In the Content Manager, click *Create* \> *Role* to open the Role editor.

2.  Enter a *Title*.

    The *ID* field is automatically filled with the same string. This occurs only the first time you enter the role title. After saving the role, you can no longer change its ID.

3.  Specify an ID that complies with the following requirements:

    -   ID is unique in the subaccount

    -   ID is unique in the platform

    -   ID cannot start with the ~ character

    -   ID can contain alphanumeric characters, spaces, and \_ - : @ + . \# & \( \) = , ' < \> ? /


4.  Click *Save* to create the role.

> ### Note:  
> -   When opening a local role in the role editor, if the role does not exist in SAP BTP you will see a warning, and you can recreate the role in the platform by editing and saving the role in the editor.
> 
> -   When deleting a local role in the role editor, the corresponding role collection and all user and group assignments to it are deleted from SAP BTP as well.



<a name="copy1410900702044af3bef46687bf7e148b__section_tm5_txw_mgc"/>

## Assigning Roles

Once you've created the role, you need to do the following in the Content Manager:

In the *Apps* tab, use the toggle in the *Assignment Status* column on the right to assign or unassign apps to or from your role and then click *Save*.

Now complete the following assignments:

-   Assign the role to the relevant site.

    For more information, see [Assign Roles to Your Site](assign-roles-to-your-site-7afe670.md).

-   Assign users to the role collection in the SAP BTP cockpit.

    For more information, see [Assign Users to a Role](assign-users-to-a-role-77f09c0.md).


> ### Note:  
> If the application is running data from another back-end system, the users must also have authorization for that data.

