<!-- loio098d8890a3fc45fe8e88444c1a7642e6 -->

# Managing Imported User Lists

Internal users as well as external users can be added to your site by importing user lists. These lists can be used to invite multiple users to internal or external workspaces.



## Introduction

SAP Build Work Zone, advanced edition customers who use SAP Cloud Identity Services - Identity Authentication and SAP Cloud Identity Services - Identity Provisioning can import groups of external or internal users from a source system using the SCIM protocol.

-   Groups of external users are imported into the site as external, imported user lists.

-   Internal users can be imported from any source system using the users own IDP that has been synced with the Identity Authentication service. These users can be added as an internal imported user list.


> ### Note:  
> Imported user lists can either be external or internal. If the user type doesn't match the list type, a warning is issued. Once you try to publish the user list, the users that don't match the list type are filtered out automatically.

For more about internal and external users, and how to create imported user lists, see:

-   [External Users - Overview](external-users-overview-4378212.md)
-   [Internal Users](internal-users-888ef2f.md)
-   [Creating Imported User Lists](creating-imported-user-lists-e7966a5.md)

There are various actions that you can perform on each list such as:


<table>
<tr>
<th valign="top">

Action



</th>
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

Edit the user list



</td>
<td valign="top">

Select *Admins Only* if the list should only be accessed by administrators. If not selected, it remains a user list that's available for anyone in the company to use.



</td>
</tr>
<tr>
<td valign="top">

Sort



</td>
<td valign="top">

Sort the user list according to:

-   Ascending or descending order

-   Name

-   Last modified




</td>
</tr>
<tr>
<td valign="top">

Filter



</td>
<td valign="top">

Filter the list by:

-   List Type

-   Status

-   Admins Only




</td>
</tr>
<tr>
<td valign="top">

View the usage details of a list.



</td>
<td valign="top">

From the *Actions* menu, choose *View Usage*. The usage report screen opens of the selected list. If you haven't enabled content administration yet, you can enable it now on the *Content Administration* screen in order to see where the user list is used.



</td>
</tr>
<tr>
<td valign="top">

Use the lists to assign or invite users to workspaces.



</td>
<td valign="top">

Assign multiple users to a workspace all at one time.

For more information, see [Assigning Required User Lists to Workspaces](assigning-required-user-lists-to-workspaces-290599f.md).



</td>
</tr>
<tr>
<td valign="top">

Add a user list to an administrative area.



</td>
<td valign="top">

1.  Choose an administrative area from the *Change Admin Area* menu.

    > ### Note:  
    > When you change an administrtive area, the overview screen of the area is in focus.

2.  Click *User Lists* under *Users* in the side navigation panel.

3.  From the *Actions* column next to a specific user list, add the list to the selected area.


Everyone in this user list is added to the selected area. Changes to a user list are automatically reflected in the area's list of users.



</td>
</tr>
</table>

