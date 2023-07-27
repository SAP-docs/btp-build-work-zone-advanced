<!-- loio992318c8057a4ed2a2c69e8b1e8bffb4 -->

# Features

On the *Feature Enablement* \> *Features* screen, you can enable or disable many features and options centrally.

While you enable the features centrally on this screen, you configure many of them on other screens in the *Administration Console*.

For information about using these features, see the [User Guide](user-guide-a356523.md).





### Compliance


<table>
<tr>
<th valign="top">

Option



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

*Enable Compliance Monitor* 



</td>
<td valign="top">

Monitors the content posted in your site and flags items that contain terms that are listed in the compliance dictionary. This monitor scans the content only starting from the date on which it was enabled. It doesn’t scan documents that were uploaded earlier. If you disable this monitor, the documents that the users upload aren’t scanned for violations of the compliance dictionary. If content has already been scanned before disabling, flagged items remain listed in the *Compliance & Security* \> *Compliance* \> *Pending Flagged Items* table.

For more information, see [Compliance and Content Administration](compliance-and-content-administration-9174e97.md).



</td>
</tr>
<tr>
<td valign="top">

*Enable Profanity Monitor* 



</td>
<td valign="top">

Monitors the content posted in your site and marks items that contain terms that are listed in the profanity dictionary. Enabling the alert doesn’t scan content retroactively, only from the date the alert is enabled. Disabling the alert permits users to post profanities in the site without recording profanity dictionary violations. If content has already been scanned before disabling, flagged items remain listed in the *Compliance & Security* \> *Compliance* \> *Pending Flagged Items* table.

For more information, see [Compliance and Content Administration](compliance-and-content-administration-9174e97.md).



</td>
</tr>
<tr>
<td valign="top">

*Enable Unscannable Filter* 



</td>
<td valign="top">

Flags all items where content can’t be scanned \(for example: images, videos, ZIP files\). The attributes of these files such as file name, title, and description are scanned by compliance and profanity filters. This filter doesn’t scan content retroactively; it scans from the date that this filter is enabled.



</td>
</tr>
</table>



### User Management


<table>
<tr>
<th valign="top">

Option



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

*Show Profile Images* 



</td>
<td valign="top">

User profile images appear beside users' posts in forums and feeds, as well as several other locations. Clear this option to turn off the display of user profile images.

For more information, see [Profiles](profiles-5c61b54.md).



</td>
</tr>
<tr>
<td valign="top">

*Allow Users to Upload a Custom Profile Image* 



</td>
<td valign="top">

Disable this option to prevent users from uploading their own user profile images. For example, your organization may already import user profile images from an external source. This option is automatically disabled if *Show Profile Images* is also disabled.

> ### Note:  
> If this option is enabled, any profile images uploaded by the user are shown instead of imported profile images. If the user hasn’t uploaded a profile photo, the default avatar image is shown.

For more information, see [Profiles](profiles-5c61b54.md).



</td>
</tr>
<tr>
<td valign="top">

*Show Profile Job Titles* 



</td>
<td valign="top">

Job titles display in users' profiles for users who have a job title.

For more information, see [Profiles](profiles-5c61b54.md).



</td>
</tr>
<tr>
<td valign="top">

*Use profile locations from third party identity provider* 



</td>
<td valign="top">

If enabled, user profiles show location information from third-party identity provider data instead of user-supplied addresses.

For more information, see [Profiles](profiles-5c61b54.md).



</td>
</tr>
<tr>
<td valign="top">

*Enable users to create their own workspaces* 



</td>
<td valign="top">

If disabled, only administrators can create workspaces.

For more information, see [Workspaces](workspaces-b5d14d2.md), and in the User Guide, see [Create a Workspace](https://help.sap.com/viewer/fec5ca6e3229418f84a932c745cbe985/Cloud/en-US/770f1b03d87d4be6974bc77df3c816a3.html).



</td>
</tr>
<tr>
<td valign="top">

*Enable Delegated Admins control to override the company setting* 



</td>
<td valign="top">

If enabled, area administrators can allow useres of their area to create workspaces even if the preceding option \(*Enable users to create their own workspaces*\) is disabled.

To enable users of an area to create workspaces, area administrators proceed as follows:

1.  In the *Change Admin Area* menu, switch to the administration area.

2.  On the *General Settings* screen under *Area Settings* , select the option *Allow area members to create workspaces*.


For more information, see [Workspaces](workspaces-b5d14d2.md), and in the User Guide, see [How to Create a Workspace](how-to-create-a-workspace-770f1b0.md).



</td>
</tr>
<tr>
<td valign="top">

*Set default for workspace email notifications* 



</td>
<td valign="top">

You can choose whether the email notifications are sent immediately, daily, weekly, or not at all. Users can override this global setting in their email notification preferences.

For more information, see, [About Notifications](about-notifications-fc1ef68.md).



</td>
</tr>
<tr>
<td valign="top">

*Enable company-wide content creation* 



</td>
<td valign="top">

Enable this option for your company so that users can post and create content from their profile and throughout the site, or disable it to restrict posts and content creation to remain within workspaces only.

> ### Note:  
> If this option is disabled, and a user is following another user: They no longer see home page feed updates regarding that user's posts and content creation outside of a workspace context, but they can see other activities \(for example, kudos given to that user or profile updates\).



</td>
</tr>
<tr>
<td valign="top">

*Show profile pages for alumni* 



</td>
<td valign="top">

Alumni users are users who have left your organization.

Select this option to make alumni users' profile pages and their content available, searchable, and visible after users have left the company.

For more information, see [Internal Users](internal-users-888ef2f.md).



</td>
</tr>
<tr>
<td valign="top">

*Clear profile info for alumni* 



</td>
<td valign="top">

Select this option to remove the personal information and image of alumni users from the site. Their office location information is removed, but their manager and job title information is retained.

For more information, see [Internal Users](internal-users-888ef2f.md).



</td>
</tr>
</table>



### Feature Management


<table>
<tr>
<th valign="top">

Option



</th>
<th valign="top">



</th>
</tr>
<tr>
<td valign="top">

*Enable API*



</td>
<td valign="top">

Enables use of the SAP Build Work Zone, advanced edition API for reading and writing content, for example, the SAP Build Work Zone mobile app.



</td>
</tr>
<tr>
<td valign="top">

*Enable File Sharing* 



</td>
<td valign="top">

Allows users to upload files to the site.



</td>
</tr>
<tr>
<td valign="top">

*Enable Feed Share* 



</td>
<td valign="top">

Adds a *Share* button to feed entries, allowing users to share updates with a specified workspace or with the entire company.



</td>
</tr>
<tr>
<td valign="top">

*Enable Content Rating* 



</td>
<td valign="top">

Allows users to rate content that has been uploaded to the site.



</td>
</tr>
<tr>
<td valign="top">

*External Workspace Creation* 



</td>
<td valign="top">

Allows the creation of private workspaces that are intended for, and accessible to, users who aren’t located within your organization's network. You can also delegate this decision to an area administrator.

For more information, see [Workspaces](workspaces-b5d14d2.md), and in the User Guide, see [How to Create a Workspace](how-to-create-a-workspace-770f1b0.md).



</td>
</tr>
<tr>
<td valign="top">

*Allow external users to be created through workspace invitation email*



</td>
<td valign="top">

Available if *External Workspace Creation* is enabled \(*Yes* or *Delegate to Area Admin*\).

Allows external users to be created when accepting an invitation email.

For more information, see [Internal Users](internal-users-888ef2f.md).



</td>
</tr>
<tr>
<td valign="top">

*Technical User details for SAP Cloud Identity invitations*



</td>
<td valign="top">

Available if *External Workspace Creation* is enabled \(*Yes* or *Delegate to Area Admin*\).

Used for authentication to the Identity Authentication service tenant by means of Basic Authentication.

Provide the Identity Authentication service client ID as the user name and the Identity Authentication service client secret as the password of the technical user.

1.  Open your Identity Authentication admin environment: for example, https://dwp.accounts400.ondemand.com/admin/.
2.  Go to *Applications & Resources* \> *Applications*.
3.  Open the SAP Build Work Zone, advanced edition application.
4.  Go to *API Authentication* \> *Client ID and Secrets*, and copy the client ID and secret.

External users that are invited to a workspace are created as users in the Identity Authentication tenant, and as external users of the site.

Clearing the user name resets the user name and password.



</td>
</tr>
<tr>
<td valign="top">

*Wikis* 



</td>
<td valign="top">

Allows users to create wiki pages in the site.

For more information, in the user guide, see [Wiki Pages](wiki-pages-3161f35.md).



</td>
</tr>
<tr>
<td valign="top">

*Persistent Navigation Bar* 



</td>
<td valign="top">

Create a custom site navigation bar with links to workspaces, workspace content, and external workpages without writing any code in the custom header. These tabs appear on all workpages throughout the site, below the top menu bar.

For more information, see [Home Pages](home-pages-000e8a1.md).



</td>
</tr>
<tr>
<td valign="top">

*Designate Blog Post Author* 



</td>
<td valign="top">

Allow a user to designate another user to create blog posts on their behalf. Although the other person can edit and publish the blog post, the name of the user who designated the other author is shown as the content creator.

For more information, in the User Guide, see [Blog Posts](blog-posts-099621a.md).



</td>
</tr>
<tr>
<td valign="top">

*Knowledge Base* 



</td>
<td valign="top">

Enables knowledge base authors to create knowledge base articles \(KBAs\) as part of employee support for their workspaces. A workspace-level setting for knowledge base articles can be enabled or disabled for specific workspaces.

You find the KBAs on a Knowledge Base page tab in a workspace.

This feature is enabled by default at the company and workspace level.

For more information, see [Feature Enablement](feature-enablement-b7a59ee.md), and in the User Guide, see [Knowledge Base](knowledge-base-9937d69.md).



</td>
</tr>
<tr>
<td valign="top">

*Company-wide knowledge base* 



</td>
<td valign="top">

Allows users to see all knowledge base articles from all workspaces that they’re members of by accessing the company *Knowledge Base* from the top menu bar.

By default, the knowledge base feature is enabled for a workspace when the company setting for the knowledge base feature is enabled. Workspace administrators can enable or disable the availability of the knowledge base feature for their workspace when editing the workspace settings.

For more information, see [Feature Enablement](feature-enablement-b7a59ee.md), and in the User Guide, see [Knowledge Base](knowledge-base-9937d69.md).



</td>
</tr>
<tr>
<td valign="top">

*Recommendation Tiles* 



</td>
<td valign="top">

Display recommendation tiles in workspaces.

For more information, in the User Guide, see [Recommendations](recommendations-0a35d00.md).



</td>
</tr>
<tr>
<td valign="top">

*Videos/Audios* 



</td>
<td valign="top">

Allows users to upload or create videos using screen captures or their webcam. Video and audio files are uploaded and encoded for use in the site.

> ### Note:  
> To create videos using non-WebRTC technology, the Adobe Flash Player must be installed. To record a video, see Java Runtime Environment \(JRE\) requirements in [Supported Browsers and Languages](supported-browsers-and-languages-99a0a18.md). The WebRTC player and the Adobe Flash player aren’t required for video playback.

> ### Note:  
> To enable watermarks on videos, or append video snippets before and after an uploaded video, contact your site administrator.



</td>
</tr>
<tr>
<td valign="top">

*Preview PDF documents using PDF viewer* 



</td>
<td valign="top">

Allow inline viewing of PDFs in a browser. If features \(such as print\) aren’t enabled with inline viewing, PDFs can be downloaded with the options to open or save in a PDF viewer.

> ### Note:  
> The *Comment on highlighted area* annotation feature isn’t available with inline PDF viewing.



</td>
</tr>
<tr>
<td valign="top">

*Include Private Workspace Details* 



</td>
<td valign="top">

Administrators can view private workspace names in reporting and compliance features and run reports on a specific private workspace.

For more information, see [Reports](reports-9fd82e0.md).



</td>
</tr>
<tr>
<td valign="top">

*Allow renaming of the external document integration name* 



</td>
<td valign="top">

Allows workspace administrators to change the default name of any of their workspace's external document integrations. If you don’t enable this option, the default name remains consistent throughout the application and can’t be changed by workspace administrators. When added or updated, the documentation integration names are also reflected in the workspace navigation and content navigation breadcrumb links.



</td>
</tr>
<tr>
<td valign="top">

*Enable integrations* 



</td>
<td valign="top">

Users can synchronize news feeds from other services.

> ### Note:  
> In order to set up integrations, users need to have an account with each external service.

For more information, see [External Integrations](external-integrations-969acf7.md).



</td>
</tr>
<tr>
<td valign="top">

*Show Hire Date in member profile* 



</td>
<td valign="top">

Display hire date information in profile pages.

For more information, see [Profiles](profiles-5c61b54.md).



</td>
</tr>
<tr>
<td valign="top">

*Show business records feeds in member profile* 



</td>
<td valign="top">

Display business record feed about user actions, such as comments, on the profile pages of the users.The business record feed on a user's profile pages displays only the actions that this user has made for business records that she or he follows.

To prevent that business record feed is displayed on the users' profile pages, clear this check box.



</td>
</tr>
<tr>
<td valign="top">

*Send daily alert emails to all members* 



</td>
<td valign="top">

Allows sending of content and updates via email.

For more information, see [Configuring Notification Emails](configuring-notification-emails-6076729.md).



</td>
</tr>
<tr>
<td valign="top">

*Send active task reminder to all members* 



</td>
<td valign="top">

Allows sending of reminders to users who are assigned to an active task.

For more information, see [Configuring Notification Emails](configuring-notification-emails-6076729.md).



</td>
</tr>
<tr>
<td valign="top">

*Allow User Level Reporting / Dashboard* 



</td>
<td valign="top">

When this option is enabled, content item owners can view a list of unique viewers and downloaders for their document. The Workspace Members List report is available.

> ### Note:  
> If you disable this option, the number of page views and downloads is still displayed, but the underlying hyperlink is no longer clickable.

For more information, see [Reports](reports-9fd82e0.md).



</td>
</tr>
<tr>
<td valign="top">

*Restrict access to Company Admins only* 



</td>
<td valign="top">

This option depends on the *Allow User Level Reporting* option being selected. If you select this option, only company administrators can run and view workspace reports, and view a list of unique viewers for all workspace content items.



</td>
</tr>
<tr>
<td valign="top">

*Hide contact information for external users* 



</td>
<td valign="top">

Hide information about other external users when a user is logged in as an external user.



</td>
</tr>
<tr>
<td valign="top">

*Enable search appliance integration* 



</td>
<td valign="top">

Allows integration with your company's search appliance. Select the search appliance authorization mechanism from the *OAuth client for search appliance integration* menu. The menu is populated from the *External Integrations* \> *OAuth Clients* screen.



</td>
</tr>
<tr>
<td valign="top">

*Enable SCIM api support* 



</td>
<td valign="top">

The SCIM API is based on the System for Cross-domain Identity Management \(SCIM\), which is an open standard for automating the exchange of user data between different user identity domains.

Enabling this option means that we can use the SCIM API to provision users in SWZ.

The SCIM API Client Name: SCIM API Client



</td>
</tr>
<tr>
<td valign="top">

Hide the *Change Password* link



</td>
<td valign="top">

Hide the *Change Password* link for users provisioned via the SCIM API.



</td>
</tr>
<tr>
<td valign="top">

*Enable document download via CDN* 



</td>
<td valign="top">

When enabled, the Content Delivery Network outside the SAP data center caches documents to boost download speeds and video streaming performance. Globally distributed customers with offices located far away from their SAP Build Work Zone, advanced edition tenant data center host experiences significant performance improvements.



</td>
</tr>
<tr>
<td valign="top">

*Enable Webcam/Screen Recorder using WebRTC technology \(Google Chrome and Mozilla Firefox only\)* 



</td>
<td valign="top">

When selected, when sharing a video via a feed update, users can choose an information icon that displays whether the compatibility checklists have been met for recording a screen capture or webcam recording. Webcam recording is supported only on Google Chrome and Mozilla Firefox browsers. Screen recording is supported only on Google Chrome \(without audio\) and Mozilla Firefox browsers.



</td>
</tr>
<tr>
<td valign="top">

*Enhanced widget styling and page layout*



</td>
<td valign="top">

Displays widgets to optimize the available screen space, improved rotating banner and gallery layouts, a bolder and larger font size, and the removal of some users' profile images.

For more information, in the User Guide, see [How to Add Content to Workspaces](how-to-add-content-to-workspaces-19bf8aa.md).



</td>
</tr>
<tr>
<td valign="top">

*Enable repository configuration at the workspace level for Microsoft Office 365* 



</td>
<td valign="top">

Allows workspace administrators to create custom labels for document integration used by their workspaces.



</td>
</tr>
<tr>
<td valign="top">

*Personal Workplace*



</td>
<td valign="top">

If enabled, users have a *My Workspace*.



</td>
</tr>
</table>



## Features That Users Configure Themselves

There are many settings that users can configure in their account.

For more information, see the SAP Build Work Zone, advanced edition User Guide at [User Settings](user-settings-2b739ae.md).

