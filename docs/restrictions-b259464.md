<!-- loiob259464c1d8144da82e726109ad83a69 -->

# Restrictions

This topic describes the current restrictions that you should be aware of when working with SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone.



<a name="loiob259464c1d8144da82e726109ad83a69__section_v4h_d4w_tfc"/>

## China Region Restrictions


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

UI Theme Designer

</td>
<td valign="top">

Only out-of-the-box themes are supported.

Custom themes are not supported because the UI theme designer is not available.

</td>
</tr>
<tr>
<td valign="top">

Custom Domain

</td>
<td valign="top">

Custom domains are not suppoted. functionality is limited due to the use of SAP Authentication and Trust Management \(XSUAA\) service as the authentication method. Integrating applications from SAP BTP content providers as well as remote content providers is not supported when using a custom domain, except for local content from the HTML5 repo.

</td>
</tr>
<tr>
<td valign="top">

Task Center

</td>
<td valign="top">

The integration with Task Center isn't supported.

</td>
</tr>
<tr>
<td valign="top">

Onboarding boosters

</td>
<td valign="top">

Using the onboarding boosters is not supported. Instead, run the onboarding steps manually.

</td>
</tr>
<tr>
<td valign="top">

Content Delivery Network

</td>
<td valign="top">

The feature *Enable document download via CDN* is not supported.

</td>
</tr>
</table>



## Feature Restrictions


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

My Inbox

</td>
<td valign="top">

The **My Inbox** app shows tasks coming from the SAP Workflow service or SAP Build Process Automation \(depending whether the onboarding occurred before the integration with SAP Build Process Automation in July 2023\).

Following the integration with SAP Task Center, cross-system approvals are possible in the SAP Task Center app.

</td>
</tr>
<tr>
<td valign="top">

Shell headers

</td>
<td valign="top">

The only shell header supported is the SAP Fiori shell header.

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

Themes

</td>
<td valign="top">

No option to enable different default themes for different personas. In SAP Build Work Zone, advanced edition, the default theme is applied to all users. Themes that are enabled for selection, are also available to all users.

</td>
</tr>
<tr>
<td valign="top">

Users and roles

</td>
<td valign="top">

The company administrator role is managed via the SCIM API. The other roles \(such as support admin, page content admin\) are not.

For more information, see [Assigning Company Administrators](assigning-company-administrators-ff793e6.md).

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
<tr>
<td valign="top">

Exporting workspaces - size limitation

</td>
<td valign="top">

When exporting workspaces, the following size restrictions apply on the exported ZIP file:

-   Max number of items: 2000
-   Max ZIP file size: 2GB
-   Max uncompressed ZIP file size: 4GB
-   Max name length of file: 255 chars
-   Max path depth of zip file: 10



</td>
</tr>
<tr>
<td valign="top">

Exporting apps with card visualizations - size limit

</td>
<td valign="top">

When exporting apps with card visualizations, the total size of the card content is limited to 45 MB.

</td>
</tr>
<tr>
<td valign="top">

Audit log messages for user profile actions

</td>
<td valign="top">

Audit log messages for user profile actions are not supported on the following data centers: DC10, DC44, DC52, DC19, DC60, DC57, DC33, DC22, DC23, DC55, DC50, DC70, DC60, DC47, DC41.

For more information, see [Auditing and Logging Information](auditing-and-logging-information-b1c760e.md).

</td>
</tr>
<tr>
<td valign="top">

Downloading documents via the Content Delivery Network

</td>
<td valign="top">

This feature is not supported on the following data centers: cf-ch20, cf-eu11.

</td>
</tr>
</table>



<a name="loiob259464c1d8144da82e726109ad83a69__section_tp3_zbp_yzb"/>

## SAP Jam Migration Restrictions


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

Integration

</td>
<td valign="top">

In SAP Jam there are several CMS integration scenarios, such as on-premise SharePoint or OpenText. In SAP Build Work Zone, advanced edition/ SAP SuccessFactors Work Zone the only CMS integration supported is Microsoft SharePoint Online \(as part of Microsoft 365\) .

</td>
</tr>
<tr>
<td valign="top">

Restricted acess users

</td>
<td valign="top">

Restricted access users aren't supported in SAP Build Work Zone, advanced edition.

</td>
</tr>
</table>



<a name="loiob259464c1d8144da82e726109ad83a69__section_b2y_lhb_xpb"/>

## Legacy Mobile App Restrictions


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

WebView restrictions

</td>
<td valign="top">

For both iOS and Android, we use WebView to load web pages. However there are some restrictions. You can use *Open in browser* to continue the following operations.

-   **Supported Version:**

    WebView is supported from version 120 and above. Due to issues related to older WebView versions running on Android 14 and below, it is required to upgrade to Android 15 or above in order to use WebView with no issues.

    If you still need to use an older version of Android, please update Android System WebView to the latest version via Google Play, and ensure that the version is greater than 120. If you are unable to update WebView, please use Chrome browser to access the content.

-   **Files:**

    -   For IOS devices, you can upload files but you can't download them.

    -   For Android devices, you can't upload or download files.

    > ### Note:  
    > Even if the buttons are visible in WebView, they aren't supported.

-   **CORS:**

    Cross-domain access isn't available for mobile apps due to WebView limitations.




</td>
</tr>
<tr>
<td valign="top">

Authentication

</td>
<td valign="top">

A direct access is possible only to a mobile URL. All other URLs require a new login, including SAP Build Work Zone, advanced edition Web URL. For example:

-   Web URL - `https://workzone.sap.hana.ondemand.com`
-   Mobile app URL - `https://workzone.mobile.sap.hana.ondemand.com`

> ### Note:  
> In some cases, for example when accessing certain types of content via mobile, additional authentication is required and users will be prompt to login again. Alternatively, users can access this content from a browser on their device and avoid multiple logins.



</td>
</tr>
<tr>
<td valign="top">

View mode

</td>
<td valign="top">

Currently, the mobile client only supports Groups view mode. Applications that are modeled with spaces and pages will not be displayed on the mobile client. For more information, see [Site Settings](site-settings-ca74965.md).

</td>
</tr>
</table>



<a name="loiob259464c1d8144da82e726109ad83a69__section_qlf_nqp_v2c"/>

## Joule Work Mobile App Restrictions


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

Workflow Management

</td>
<td valign="top">

Applications and content from Workflow Management are not supported in the Joule Work mobile app \(it’s recommended to switch to SAP Build Process Automation\).

</td>
</tr>
<tr>
<td valign="top">

Joule Work mobile app strategy and guidance

</td>
<td valign="top">

See the following SAP Note: [Strategy & Guidance](https://me.sap.com/notes/3593046)

</td>
</tr>
<tr>
<td valign="top">

Changes to SAP Mobile Services Settings in a Subaccount

</td>
<td valign="top">

The Joule Work mobile app is enabled per site while the mobile settings are configured in the subaccount level.

Therefore, any change to the mobile settings \(for example, passcode policy\),will affect all sites that are connected to the Joule Work mobile app in this subaccount.

</td>
</tr>
</table>



<a name="loiob259464c1d8144da82e726109ad83a69__section_emh_hcp_yzb"/>

## Content Management and Federation Restrictions

For more information about restrictions related to business content and content federation, see [General Restrictions](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/restrictions-general#general-restrictions), [Federation Restrictions](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/restrictions-general#federation-restrictions).

