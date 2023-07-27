<!-- loio476b62b69bf740049c04ca8004de5f45 -->

# Managing Dynamic User Lists

A dynamic user list is based on rules that consist of various profile attributes.



## Introduction

You can use dynamic user lists to create a rules-based list that updates whenever there are changes for those users who fit the selected rules. Creating a dynamic user list that includes the users of several departments, can change over time as people join and leave those departments.

Dynamic user lists are created and managed from the *User Lists* screen that you access from the Administration Console under the *Users* menu item. From the *Dynamics User Lists* tab, you can create and manage your lists as follows:


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

Create, edit, or delete a user list.



</td>
<td valign="top">

Use the dedicated button to create a new dynamic user list. To edit or delete an existing user list, open the dropdown options from the *Actions* column next to the user list.

For more information, see the section below - **How to create and manage a dynamic user list**.



</td>
</tr>
<tr>
<td valign="top">

View the usage details of a list.



</td>
<td valign="top">

From the *Actions* menu, choose *View Usage*. The usage report screen opens of the selected list. If you haven't enabled content administration yet, you can enable it now on the *Content Management* screen in order to see where the user list is used.



</td>
</tr>
<tr>
<td valign="top">

Use the lists to assign or invite users to workspaces.



</td>
<td valign="top">

Assign multiple users who fit specific rules to a workspace all at one time.

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
    > When you change an administrative area, the overview screen of the area is in focus.

2.  Click *User Lists* under *Users* in the side navigation panel.

3.  From the *Actions* column next to a specific user list, add the list to the selected area.


Everyone in this user list is added to the selected area. Changes to a user list are automatically reflected in the area's list of users.



</td>
</tr>
</table>



<a name="loio476b62b69bf740049c04ca8004de5f45__section_kjc_fm1_ntb"/>

## How to create and manage a dynamic user list

To create a new list:

1.  Click *New Dynamic User List*.

2.  Fill in the *Name* field and optionally, the description.

3.  Select *Admins Only* if the list should only be accessed by administrators. If not selected, it remains a user list that's available for anyone in the company to use.

4.  Click inside the *Rules* box. The *Dynamic User List Rules* dialog box displays.

5.  Select a criteria for the rule from the dropdown list. For example, `Country/Region`.

6.  Keep clicking *Select an option* to select additional criteria for your rule.

7.  Click *Done*.

8.  Click *Publish* once it's ready for use.

The dynamic user lists display a status of either:

-   *Complete* - users have been synced according to the rule criteria.

-   *Pending* - no rule criteria has been set for users.

**Related Information**  


[Dynamic User Lists Attributes](dynamic-user-lists-attributes-aa0cb53.md "You can configure dynamic user lists based on specific attributes.")

