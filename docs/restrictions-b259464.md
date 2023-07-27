<!-- loiob259464c1d8144da82e726109ad83a69 -->

# Restrictions

This topic describes the current restrictions that you should be aware of when working with SAP Build Work Zone, advanced edition.



## Feature Restrictions

The *Applications* page is a single page that is filtered to only display the apps that the user can access.

For more information about the restrictions that you need to take into account when integrating apps into SAP Build Work Zone, advanced edition, see [Restrictions - General.](https://help.sap.com/viewer/8c8e1958338140699bd4811b37b82ece/Cloud/en-US/8cf196a5a8544c309086619df29595b1.html)


<table>
<tr>
<th valign="top">

Feature



</th>
<th valign="top">

Restriction



</th>
</tr>
<tr>
<td valign="top">

Notifications



</td>
<td valign="top">

-   The site only displays local notifications. For example, content updates, invitations, approvals. Integration of notifications coming from remote systems isn't supported.

-   The notification bell only opens the *Notifications* screen. When you click it, there's no hover or dropdown list showing the notifications.




</td>
</tr>
<tr>
<td valign="top">

Search



</td>
<td valign="top">

There are two types of search mechanisms - enterprise search and a site-specific search.

For more information about the two search mechanisms, see [Searching in the Site.](https://help.sap.com/docs/WZ/fec5ca6e3229418f84a932c745cbe985/a3a83b4013a74d3d9977afdd939e5486.html)

In the site-specific search, the search aggregates results from local objects such as workspaces and documents.

Restrictions in the search feature include:

-   Searches don't include objects in remote systems.

-   A search only supports a limited type-ahead experience. Your results won't show content type or an option to view all content items of a specific type. For example, when searching in a workspace forum, you can't get results if you search for a question or an idea forum.

-   You can't use keyboard shortcut commands to change the dropdown filter. For example, in the search text box you can't type in 'e' to restrict the results to 'events'.

-   You can't browse more than one search result type. For example, you can 'view all' in general but you can't 'view all tasks'.



</td>
</tr>
<tr>
<td valign="top">

Chatbots



</td>
<td valign="top">

No predefined chatbots are available.



</td>
</tr>
<tr>
<td valign="top">

Content Lifecycle Management



</td>
<td valign="top">

Content Lifecycle Management capabilities are limited to the scenarios described in this topic: [Transporting Content](transporting-content-c04d484.md).



</td>
</tr>
<tr>
<td valign="top">

My Inbox



</td>
<td valign="top">

The **My Inbox** app shows only tasks coming from the SAP Workflow service.



</td>
</tr>
<tr>
<td valign="top">

Integration



</td>
<td valign="top">

The only CMS integration that is available is Microsoft SharePoint Online \(as part of Microsoft 365\) .



</td>
</tr>
<tr>
<td valign="top">

Navigation



</td>
<td valign="top">

The option to enable a shared header across all SAP SuccessFactors modules is not available in SAP SuccessFactors Work Zone. Only the SAP Fiori shell header is available.



</td>
</tr>
<tr>
<td valign="top">

My Workspace template



</td>
<td valign="top">

*My Workspace* doesn't have a template or role-based layout. If this feature is enabled, the default layout of *My Workspace* is the same for all users. Only individual users can make changes to the page.



</td>
</tr>
<tr>
<td valign="top">

Online status indicator



</td>
<td valign="top">

The online status indicator can't be controlled by the user. If it was set to offline prior to the upgrade, it remains as offline.



</td>
</tr>
<tr>
<td valign="top">

Themes



</td>
<td valign="top">

No option to enable different default themes for different personas. In SAP Build Work Zone, advanced edition, the default theme is applied to all users. Themes that are enabled for selection, are also available to all users.



</td>
</tr>
<tr>
<td valign="top">

Integration with SAP SuccessFactors



</td>
<td valign="top">

Integration with SAP SuccessFactors Learning and Employee Central Service Center \(knowledge base\) are both only partly supported.

This is only relevant to SAP SuccessFactors Work Zone.



</td>
</tr>
<tr>
<td valign="top">

E-mails



</td>
<td valign="top">

E-mail domains and the e-mail server for email notifications can't be changed.



</td>
</tr>
<tr>
<td valign="top">

Identity Authentication



</td>
<td valign="top">

IDP-initiated login from Identity Authentication isn't supported when a corporate IDP is selected as the default.



</td>
</tr>
<tr>
<td valign="top">

Group navigation in SAP Jam



</td>
<td valign="top">

When an existing SAP Jam user onboards to SAP Build Work Zone, advanced edition, the group navigation is lost and needs to be re-added manually as pages. For example, forums and events.

Only header-navigation is available.



</td>
</tr>
<tr>
<td valign="top">

Users and roles



</td>
<td valign="top">

The SAP Build Work Zone, advanced edition user group on SAP Cloud Identity Services - Identity Authentication and the user roles \(company admin, area admin, user\) aren't synced.

For more information, see [Manage Administrators Using SCIM API](manage-administrators-using-scim-api-ff793e6.md).



</td>
</tr>
<tr>
<td valign="top">

Dynamic tiles



</td>
<td valign="top">

Dynamic tiles are only supported in the *Applications* page of SAP Build Work Zone, advanced edition.



</td>
</tr>
<tr>
<td valign="top">

Restricted acess users



</td>
<td valign="top">

Restricted access users aren't supported in SAP Build Work Zone, advanced edition



</td>
</tr>
<tr>
<td valign="top">

Embedded Mode



</td>
<td valign="top">

Embedding SAP Build Work Zone, advanced edition into another application, for example via an iframe, is not supported. The exception to this restriction is the dedicated Microsoft Teams integration that supports selected embedding, but only in the context of this specific integration. For more information, see [Integrating with Microsoft Teams](integrating-with-microsoft-teams-bfa596d.md).



</td>
</tr>
<tr>
<td valign="top">

Selecting workspaces in Microsoft Teams



</td>
<td valign="top">

You can select up to 100 workspaces in the workspace dropdown picker of the Microsoft Teams application.



</td>
</tr>
</table>



<a name="loiob259464c1d8144da82e726109ad83a69__section_b2y_lhb_xpb"/>

## Mobile Restrictions


<table>
<tr>
<th valign="top">

Feature



</th>
<th valign="top">

Restriction



</th>
</tr>
<tr>
<td valign="top">

Single Sign-On \(SSO\)



</td>
<td valign="top">

Accessing business data from the mobile client doesn't support Single Sign-On.



</td>
</tr>
<tr>
<td valign="top">

Customization



</td>
<td valign="top">

The mobile client can't be extended and customized.



</td>
</tr>
<tr>
<td valign="top">

Notifications



</td>
<td valign="top">

The mobile client doesn't support push notifications.



</td>
</tr>
<tr>
<td valign="top">

MDM restrictions



</td>
<td valign="top">

The mobile client doesn't support MDM restrictions on managed devices.



</td>
</tr>
<tr>
<td valign="top">

Restricting app activation



</td>
<td valign="top">

Option to activate the mobile client can't be restricted. This means that all users can activate the app.



</td>
</tr>
<tr>
<td valign="top">

Settings



</td>
<td valign="top">

Certain settings in Mobile Settings Exchange \(Mobile Service\) aren't active or used. For example, Feature Flag for Push or Print.



</td>
</tr>
<tr>
<td valign="top">

Supported devices



</td>
<td valign="top">

SAP Build Work Zone, advanced edition mobile app doesn't respect the *Supported Devices* setting that is relevant to the *Applications* page.

However if there are apps that you don't want displayed on your mobile device, please refer to the note in this topic: [Setting Up the SAP Work Zone Mobile App](https://help.sap.com/docs/WZ/fec5ca6e3229418f84a932c745cbe985/1d157ebf40fa48648dc8e40909c63076.html).



</td>
</tr>
<tr>
<td valign="top">

WebView restrictions



</td>
<td valign="top">

For both iOS and Android, we use WebView to load web pages. However there are some restrictions.. You can use *Open in browser* to continue the following operations.

-   **Files:**

    -   For IOS devices, you can upload files but you can't download them.

    -   For Android devices, you can't upload or download files.

    > ### Note:  
    > Even if thse buttons are visible in WebView, they aren't supported.

-   **CORS:**

    Cross-domain access isn't available for mobile apps due to WebView limitations.

-   **Authentication:**

    The mobile app is authentication-free via mobile services. Content can't be accessed when another IAS or third-party authentication is required.




</td>
</tr>
</table>

