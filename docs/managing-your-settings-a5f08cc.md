<!-- loioa5f08ccb81794894806f6812b0c56a27 -->

# Managing Your Settings

You can change the visual appearance of your site such as the theme, search settings, user default values, user activities, and many other features.



<a name="loioa5f08ccb81794894806f6812b0c56a27__section_fbz_s2p_byb"/>

## Where do I manage my settings?

In the User Actions menu, choose *Settings*. A settings dialog opens for each of the relevant settings that you want to view or edit.



<a name="loioa5f08ccb81794894806f6812b0c56a27__section_gbz_s2p_byb"/>

## What settings can I view or change?

> ### Note:  
> Some settings are read-only and can't be changed directly in the *Settings* screen. You may also not see all the settings; they may either be disabled by your administrator or not supported on your platform.


<table>
<tr>
<th valign="top">

Setting

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

User Account

</td>
<td valign="top">

View your account settings, such as name, e-mail, and server address.

</td>
</tr>
<tr>
<td valign="top">

Appearance

</td>
<td valign="top">

Change your theme and display settings.

**Themes**

The *SAP Morning Horizon* theme is the default theme.

The themes are listed according to the following categories:

-   *SAP Quartz Set* - includes the light, dark, high contrast black, and high contrast white SAP Quartz themes.
-   *SAP Horizon Set* - includes the morning, evening, high contrast black, and high contrast white SAP Horizon themes.
-   *Individual Themes* - lists additional themes that are not part of a set.
-   *Custom Theme Sets*

    For more information about how to create a custom theme or custom theme sets, see [Create and Assign a Custom Theme or Custom Theme Set](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/create-and-assign-custom-theme).


In addition to the list of themes, each set also includes an option for **automatic detection** of the theme used in the operating system settings. When selected, the theme of your runtime site is set automatically according to your operating system settings.

For example, when your operating system is set to Dark Mode and High Contrast, if the automatic theme detection option is selected for the SAP Quartz set, your runtime site will be displayed using the SAP **High Contrast Black \(Quartz\)** theme.

The automatic theme detection option is available for all theme sets \(such as the SAP Quartz and the SAP Horizon sets\) where there is more than one theme available in the set.

> ### Note:  
> Some themes may be restricted by your administrator, so they will not be available. However, if the option for automatic theme detection is selected, the operating system settings will take effect.
> 
> For example, if the admin disabled SAP Evening Horizon, the automatic theme detection option is selected for the SAP Horizon set, and the operating system is set to Dark Mode, then the SAP Evening Horizon theme will be used in the runtime site even though it was disabled by the admin.

> ### Note:  
> The automatic theme detection option might not be supported by all browsers and operating systems.

**Display Settings**

Under this tab you have the option to use the following settings:

-   *Show Source System Name on Tiles*

    Show from which system the app comes, directly on the tile. We recommend activating this setting if the apps you use are available in multiple systems.

-   *Optimized for Touch Input*

    When using a hybrid device that combines touch and mouse events, you can turn on the feature which increases the size and spacing of the controls on your screen so they are easier to use with your fingertip. You can choose if the tiles should be displayed in a small or a large size.




</td>
</tr>
<tr>
<td valign="top">

Language and Region

</td>
<td valign="top">

Choose the preferred language for the business content in your site. Depending on the language you select, the date, time format, decimal format, and work week will be updated accordingly. These values can't be modified.

> ### Note:  
> When configuring a locale for a site:
> 
> -   The language settings are taken from SAP Build Work Zone for all application types.
> -   The date and number format settings are taken from:
>     -   SAP Build Work Zone locale settings for SAPUI5 applications.
>     -   SAP S/4HANA user profile settings for legacy applications.



</td>
</tr>
<tr>
<td valign="top">

Home Page

</td>
<td valign="top">

> ### Note:  
> This setting only applies if you're working in *Groups* view mode.

Choose whether to show the content of all your groups all at once on the Home page or to show only one group at a time. The group selection bar at the top of the home page appears identical for both options; however, they behave differently:

-   Show all content: Behaves like an anchor bar; choosing a group at the top of the home page scrolls to the content assigned to the group.

-   Show one group at a time: Behaves like a tab bar; choosing a group displays the content assigned to the group.


For large amounts of apps, showing one group at a time may be better.

</td>
</tr>
<tr>
<td valign="top">

User Activities

</td>
<td valign="top">

> ### Note:  
> This setting is only visible if the administrator has enabled *Recent and Frequent Activities* in the Site Settings.

Specify whether to track user activity.

Check this option *Track my recent activity and frequently used apps* to track your recent activities. The entries *Recent Activities* and *Frequently Used* are then added to the User Actions menu. If this option is unchecked, you won't see these entries on the User Actions menu.

Click *Clear my history* to delete your user activities.

For more information, see [Working with Recent Activities and Frequently Used Apps](working-with-recent-activities-and-frequently-used-apps-fb44b72.md).

</td>
</tr>
<tr>
<td valign="top">

Default Values

</td>
<td valign="top">

> ### Note:  
> This option only appears if you have integration with an SAP S/4HANA system.

View and edit default user-specific parameter values used when launching your apps.

For more information, see [How to Use Default Values in App Fields](how-to-use-default-values-in-app-fields-fb9d1ca.md).

</td>
</tr>
<tr>
<td valign="top">

Joule Work Mobile App

</td>
<td valign="top">

Scan the QR Code to intall the Joule Work mobile app.

For more information, see [Setting Up the Joule Work Mobile App](setting-up-the-joule-work-mobile-app-3257133.md).

</td>
</tr>
<tr>
<td valign="top">

Mobile Application

</td>
<td valign="top">

Follow the instructions in the *Settings* screen to register and install the mobile application. For more information, see [Setting Up SAP Build Work Zone Advanced Mobile App](setting-up-sap-build-work-zone-advanced-mobile-app-1d157eb.md).

> ### Note:  
> This option is only visible if you've enabled the *Mobile Application* in the *Site Settings* screen.



</td>
</tr>
<tr>
<td valign="top">

Notifications

</td>
<td valign="top">

Personalize various settings that are related to the notifications.

For more information, see [How to Work With Central Notifications](how-to-work-with-central-notifications-52c4791.md).

</td>
</tr>
</table>



<a name="loioa5f08ccb81794894806f6812b0c56a27__section_vl3_5dk_rfc"/>

## Advanced Settings

From the advanced settings screen, you can configure the following features. When you choose a feature, you are forwarded to the relevant settings.


<table>
<tr>
<th valign="top">

Tab

</th>
<th valign="top">

What you can do

</th>
</tr>
<tr>
<td valign="top">

*Email*

</td>
<td valign="top">

Select options for daily email digests and the frequency of workspace notifications. Provide an email address to update your feed.

</td>
</tr>
<tr>
<td valign="top">

*Feed Settings*

</td>
<td valign="top">

Create a custom feed by selecting what type of status, content, and other activity updates you want to see.

</td>
</tr>
<tr>
<td valign="top">

*Integrations*

</td>
<td valign="top">

Set up integrations and sync with other sites \(for example, Personal Blog RSS\).

</td>
</tr>
<tr>
<td valign="top">

*Applications*

</td>
<td valign="top">

Lists any authorized applications that have access to your account.

</td>
</tr>
<tr>
<td valign="top">

*Profile Data Disclosure*

</td>
<td valign="top">

View a list of your personal data stored in the system. Disclosure details satisfy the compliance requirements for national and regional data privacy standards. Personal data from SuccessFactors Platform or SCIM \(for example, e-mail addresses, phone numbers, location addresses\) can also display on this page.

</td>
</tr>
<tr>
<td valign="top">

*Time & Calendar Settings*

</td>
<td valign="top">

This time zone setting affects workspace content.

Set your preferred time zone for features like the events displayed in the calendar\(s\), scheduled publishing, and display of timestamps in workspace content.

</td>
</tr>
<tr>
<td valign="top">

*Away Alerts*

</td>
<td valign="top">

Let other users know when you're away.

</td>
</tr>
<tr>
<td valign="top">

*Designate Blog Post Author*

</td>
<td valign="top">

Allow other people to publish and edit blogs on your behalf.

</td>
</tr>
<tr>
<td valign="top">

*Trash*

</td>
<td valign="top">

Contains items that you previously deleted. You can restore or permanently remove these deleted items.

</td>
</tr>
<tr>
<td valign="top">

*Terms of Service*

</td>
<td valign="top">

If the administrator has defined a Terms of Service agreement, you can review it and accept it the next time you log on to the system.

</td>
</tr>
</table>

