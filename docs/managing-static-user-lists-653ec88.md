<!-- loio653ec88e317447b19c5bf26f81355043 -->

# Managing Static User Lists

Static user lists are created and managed manually by an administrator. They're used mainly to invite large groups of users in the company to become members of a specific workspace.



## Introduction

Static user lists are created and managed from the *User Lists* screen that you access from the Administration Console under the *Users* menu item. From the *Static User Lists* tab, you can create and manage your lists as follows:


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

Use the dedicated button to create a new static user list. To edit or delete an existing user list, open the dropdown options from the *Actions* column next to the user list.

For more information, see the section below - **How to create and manage a static user list**.



</td>
</tr>
<tr>
<td valign="top">

Add users to a user list.



</td>
<td valign="top">

You can add users to a static user list in one of the following ways:

-   Add them individually.

-   Add already existing user lists.

-   Import a CSV file of email addresses.




</td>
</tr>
<tr>
<td valign="top">

View the usage details of a list.



</td>
<td valign="top">

From the *Actions* menu, choose *View Usage* next to a user list. The usage report screen opens of the list. If you haven't enabled content administration yet, you can enable it now in the *Content Administration* screen in order to see where the user list is used.



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
    > When you change an administrtive area, the overview screen of the company or area is in focus.

2.  Click *User Lists* under *Users* in the side navigation panel.

3.  From the *Actions* column next to a specific user list, add the user list to the selected area.


Everyone in this user list is added to the selected area. Changes to a user list are automatically reflected in the area's list of users.



</td>
</tr>
</table>



<a name="loio653ec88e317447b19c5bf26f81355043__section_olq_hv5_mtb"/>

## How to create and manage a static user list

To create a new user list:

1.  Click *New Static User List*.

2.  In the *New Static User List* popup, enter a meaningful name for the user list and then click *OK* to open the *Edit Static User List* screen.

3.  In the *Add Users* text box, add users as follows:

    -   Enter the person's name or email address. When you see the name in the dropdown auto-completion list, click their information to add them. You can also add the name of another user list – this will add all the users from that list. Make sure that each user name or user list name is separated by a comma. The status of the user or the user list is *To be added*.

    -   Click *Import CSV* to import a comma-separated list of email addresses of users. Use your browser's upload feature to find and select the file on your hard drive. When the file is uploaded and processed, the listed users are added.


    > ### Note:  
    > If you add an unknown email address, it displays in the *Errors* tab. You can save a user list that has errors, but you can't publish it until you've edited and corrected the unrecognized email addresses.

4.  To edit or remove users from your user list, hover over a row of a user and click *Undo* \(if the status is *To be added*\) or *Remove* \(if status is *Published*\).

5.  Select *Admins Only* if the list should only be accessed by administrators who want to invite users to be members of a workspace. If not selected, it remains a user list that is available for anyone in the company to use.

6.  If you are satisfied with the collection of users in the list and there are no errors, click *Publish* to make the user list available for use. If you click *Discard Changes*, all pending users from the list are removed.

    Once you've published, the status of the list changes to *Published* and the static user list is now ready to be used.


