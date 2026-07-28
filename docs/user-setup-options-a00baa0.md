<!-- loioa00baa06e20e4b0d950a4b4bbc9ddfb6 -->

# User Setup Options

Choose how to manage admin assignments and automatic user creation.



## Administrator Assignment

Choose one of the following methods to manage administrator assignments in your site:


<table>
<tr>
<th valign="top">

Option

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

Administrators managed locally in SAP Build Work Zone, advanced edition.

</td>
<td valign="top">

First user to log in is an administrator, and after that a company administrator can promote any other member to be an administrator.

To manually assign a user to an administrator role:

1.  In the Admin Console open *Users* \> *Internal Users* and select the user from the list.
2.  In the *Action* dropdown, select *Edit* and open the user profile.
3.  In the *User Type* dropdown choose the type - Company/Support admin.

For more information, see [Assigning Administrators Manually](about-administrators-63a91fb.md#loio63a91fb1d4dd4fefaf46358be0f8bfa4__section_ahw_ywl_trb).

</td>
</tr>
<tr>
<td valign="top">

Administrators managed by SCIM provisioning source.

</td>
<td valign="top">

Only users with the SCIM role of 'Administrator' are company administrators in SAP Build Work Zone, advanced edition.

For more information, see [Assigning Company Administrators](assigning-company-administrators-ff793e6.md).

</td>
</tr>
<tr>
<td valign="top">

Administrators managed by SAP BTP role collections.

</td>
<td valign="top">

Users are granted access to admin permissions based on their role collection assignment\(s\) in the SAP BTP cockpit. When this option is enabled, updates to admin permissions may not be immediately reflected in the DWS APIs. This may cause temporary permission inconsistencies, which are resolved after the user’s next login.

</td>
</tr>
</table>



## Automatic User Creation

The following options are available for automatic user creation:

-   Allow automatic internal user creation - When this option is enabled, the system automatically creates a user upon their first login if the user does not already exist in the system. Subsequently, the user record will get updated with each login.

    > ### Note:  
    > Enabling this feature maps `SCIM.userName` to `SAP Global User ID` for both internal and external users. If external user creation is already enabled, activating this feature will change the current `SCIM.userName` mapping to use `SAP Global User ID` for all user types instead. If existing users are presented \(synced via SAP Cloud Identity\), ensure `SAP Global User ID` mapping is properly configured to prevent user duplication or access conflicts.

-   Allow automatic external user creation - When this option is enabled, the system automatically creates an external user based on a SAML assertion upon their first login. For more information, see [Allow SAML Assertion-Based Creation of External Users](allow-saml-assertion-based-creation-of-external-users-1c88797.md).

