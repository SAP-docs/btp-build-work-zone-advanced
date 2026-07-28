<!-- loio3f619a13ca2a4a59a14bec8507c3fb69 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# About the Site Manager

The Site Manager is the design-time environment for managing sites and subaccount-level settings.



<a name="loio3f619a13ca2a4a59a14bec8507c3fb69__section_grj_23z_dgb"/>

## About the Site Manager Screens

The Site Manager consists of several screens, where you can manage sites, business content, content channels and different settings in your subaccount. You can access each screen from a side menu.


<table>
<tr>
<th valign="top">

Screen

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Site Directory

:globe_with_meridians:

</td>
<td valign="top">

The Site Directory contains your site tile, from which you can:

-   Manage your site alias

-   Open the runtime site

-   Access the *Site Studio* to:

    -   Configure the site settings.

    -   Assign single and content channel roles to your site.





</td>
</tr>
<tr>
<td valign="top">

Content Manager

:package:

</td>
<td valign="top">

In the Content Manager you manage the business content items for your site: apps, catalogs, groups, roles, and shell plugins.

Add business content items to the subaccount in one of the following ways:

-   Integrate content items from content providers.

-   Manually integrate content items by configuring them using content editors .




</td>
</tr>
<tr>
<td valign="top">

Channel Manager

<span class="SAP-icons-V5"></span>

</td>
<td valign="top">

In the Channel Manager you manage your content providers :

-   Remote content providers

-   SAP BTP content provider - HTML5 apps.


These content providers expose business content that you can integrate into your sites.

</td>
</tr>
<tr>
<td valign="top">

Import Monitor

:inbox_tray:

</td>
<td valign="top">

In the Import Monitor you track the status of your imports.

For more information, see [Tracking the Progress of Your Imports](tracking-the-progress-of-your-imports-0443a41.md).

</td>
</tr>
<tr>
<td valign="top">

Configurator

<span class="SAP-icons-V5"></span>

</td>
<td valign="top">

The Configurator is a wizard that assists you in completing the onboarding process to SAP Build Work Zone, advanced edition. For more information, see [Onboarding to SAP Build Work Zone, advanced edition](https://help.sap.com/docs/WZ/b03c84105ff74f809631e494bd612e83/f8c6eab5b9c8437f9367271863ac90eb.html).

</td>
</tr>
<tr>
<td valign="top">

Settings

:gear:

</td>
<td valign="top">

In the Settings screen you manage your subaccount settings. For more information, about the different subaccount settings, see [Site Settings](https://help.sap.com/docs/WZ/b03c84105ff74f809631e494bd612e83/e2bfc3d7e2694e189fb4cde61a347361.html).

</td>
</tr>
</table>



<a name="loio3f619a13ca2a4a59a14bec8507c3fb69__section_cbm_dwy_xxb"/>

## About the Content Manager

The Content Manager displays a list of all the content items in the subaccount – items that were integrated from content providers, as well as manually-integrated items.

Use the content editors to view provider-based content items, and to view, edit, or configure new manually-integrated content items.

> ### Note:  
> Content items from remote providers can't be edited in the Content Manager. Content items created locally are editable using the relevant editors.

From the Content Manager, you can access the Content Explorer, where you can see the content channels in the subaccount. When you select a channel, you can manage the content items in each channel, which includes adding or removing an item to or from the subaccount.



<a name="loio3f619a13ca2a4a59a14bec8507c3fb69__section_azq_m1f_b3b"/>

## About Business Content

Use the Content Manager to manage your content items: apps, catalogs, groups, roles, and shell plugins.

The following table describes these content items:


<table>
<tr>
<th valign="top">

Content Item

</th>
<th valign="top">

Administrator can:

</th>
</tr>
<tr>
<td valign="top">

Apps

</td>
<td valign="top">

An app can come from one of the following sources:

-   Provider-based content:

    In the *Content Explorer*, browse through the available content providers , select content items, and add them to the subaccount. You'll see that they are added to the list in the Content Manager.

-   Manually-configured content:

    In the Content Manager, use the App editor to manually configure an app based on a UI technology such as: URL, Dynamic URL, SAPUI5, SAPGUI for HTML, and Web Dynpro ABAP.




</td>
</tr>
<tr>
<td valign="top">

Catalogs

</td>
<td valign="top">

Assign apps to a catalog to display them together under a certain catalog in the App Finder. The App Finder is a tool that enables users to find all the apps available for their role.

For more information, see [App Finder](https://help.sap.com/viewer/3d99fdeadde04524bdd33d35f1e13777/Cloud/en-US/48a5dbb0308b47d8969485845d5966ae.html).

</td>
</tr>
<tr>
<td valign="top">

Groups

</td>
<td valign="top">

If the apps are modeled in groups, you assign them to groups to make them visible in the runtime site.

</td>
</tr>
<tr>
<td valign="top">

Roles

</td>
<td valign="top">

A role can come from one of the following sources:

-   Provider-based content:

    In the *Content Explorer*, browse through the available content channels, select roles, and add them to the subaccount. As a result, they are added to the list in the Content Manager. The role is already assigned to the relevant apps, according to the source content.

-   Manually-configured

    In the Content Manager, use the role editor to manually configure a role. Assign apps to the role to enable users with this role to view and access these apps from the runtime site.

-   An *Everyone* role is provided out-of-the-box. Apps assigned to this role are visible to all users.


You must assign a role to one or more sites, to determine user access to content in the site.

</td>
</tr>
<tr>
<td valign="top">

Spaces

</td>
<td valign="top">

Content can be modeled with spaces and pages instead of groups. A space contains one or more pages, and is assigned to a role. Spaces are displayed in the navigation bar of the site, where you can switch between spaces and between pages within a space.

</td>
</tr>
<tr>
<td valign="top">

Pages

</td>
<td valign="top">

A space contains one or more pages. Each page contains app tiles and cards, which are displayed in different sections.

</td>
</tr>
<tr>
<td valign="top">

Shell plugins

</td>
<td valign="top">

A shell plugin is a type of an HTML5 application that changes the functionality or UI of the page. Plugins are automatically loaded and initialized in runtime when the site is loaded.

Shell plugins can be integrated from SAP BTP and remote content providers.

</td>
</tr>
</table>

