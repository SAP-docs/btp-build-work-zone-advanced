<!-- loio992318c8057a4ed2a2c69e8b1e8bffb4 -->

# Features

On the *Feature Enablement* \> *Features* screen, you can enable or disable many features and options centrally, for the entire company.

The following settings apply to the entire company. They can be referred to as "global settings". Some settings, for example certain workspace settings, can be disabled locally by a workspace administrator, even through the setting is enabled in the company level.





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

If enabled, area administrators can allow users of their area to create workspaces even if the preceding option \(*Enable users to create their own workspaces*\) is disabled.

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

For more information, see [Managing Internal Users](managing-internal-users-888ef2f.md).

</td>
</tr>
<tr>
<td valign="top">

*Clear profile info for alumni* 

</td>
<td valign="top">

Select this option to remove the personal information and image of alumni users from the site. Their office location information is removed, but their manager and job title information is retained.

For more information, see [Managing Internal Users](managing-internal-users-888ef2f.md).

</td>
</tr>
<tr>
<td valign="top">

*External Users*

</td>
<td valign="top">

-   *Allow external users to access workspaces*: when enabled, external users can be invited as members to public or private workspaces, and can access as non-members public workspaces.
-   *Allow workspace admins to set the access policy to All external users or All users*: when enabled, workspace admins \(and not only company admins\) can provide non-members access to ‘All external users’ and ‘All user'.
-   *Enable automatic creation of external users through workspace invitation email*: when enabled, any external user \(who exists in the IdP\), is automatically created and provisioned to SAP Build Work Zone, advanced edition upon accepting a workspace invitation, and performing a self-registration. For more information, see [About External Users](about-external-users-4378212.md).
-   *Client ID and Secret*: To allow SAP Build Work Zone, advanced edition trigger API calls towards Identity Authentication and perform external user authentication, enter the Client ID and secret generated for SAP Build Work Zone, advanced edition in the Identity Authentication admin environment. For more information, see [Configuring External Users Authentication](configuring-external-users-authentication-df89bb3.md).



</td>
</tr>
</table>



### Integration Features


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

*Enable SCIM API support* 

</td>
<td valign="top">

The SCIM API is based on the System for Cross-domain Identity Management \(SCIM\), which is an open standard for automating the exchange of user data between different user identity domains.

The SCIM API support feature must always be enabled and it allows the provisioning of users and user lists to SAP Build Work Zone, advanced edition.

As an admin, you can assign an OAuth client from the list of available clients, and this OAuth client can only be assigned to one integration feature, therefore it will be used only for the SCIM API. Once selected, that OAuth client can't be deleted in the *External Integrations* \> *OAuth Clients* screen.

> ### Note:  
> After switching the SCIM API OAuth client, the *Trigger Setup* step must be re-run to update the displayed credentials in the onboarding configurator.



</td>
</tr>
<tr>
<td valign="top">

*Use profile information from the SCIM API* 

</td>
<td valign="top">

If enabled, the user profile shows information taken from the SCIM API instead of user-supplied, for the following fields: location, nickname, and display name. When taken from the SCIM API, these values appear in the profile as read-only.

For more information, see [Profiles](profiles-5c61b54.md).

</td>
</tr>
<tr>
<td valign="top">

*Enable search appliance integration* 

</td>
<td valign="top">

Enables integration with your company's search appliance to make content searchable in a single unified interface.

As an admin, you can assign an OAuth client from the list of available clients, and this OAuth client can only be assigned to one integration feature, therefore it will be used only for the search appliance. Once selected, that OAuth client can't be deleted in the *External Integrations* \> *OAuth Clients* screen.

</td>
</tr>
<tr>
<td valign="top">

*Enable document grounding integration* 

</td>
<td valign="top">

Enable the integration with document grounding to make content from workspaces that are marked as AI sources available to AI queries.

As an admin, you can assign an OAuth client from the list of available clients, and this OAuth client can only be assigned to one integration feature, therefore it will be used only for document grounding. Once selected, that OAuth client can't be deleted in the *External Integrations* \> *OAuth Clients* screen.

For more information, see [Integration With Document Grounding](integration-with-document-grounding-5ff7714.md).

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

*Enable repository configuration at the workspace level for Microsoft Office 365* 

</td>
<td valign="top">

Allows workspace administrators to create custom labels for document integration used by their workspaces.

</td>
</tr>
<tr>
<td valign="top">

*Show business records feeds in member profile* 

</td>
<td valign="top">

Display business record feed about user actions, such as comments, on the profile pages of the users. The business record feed on a user's profile pages displays only the actions that this user has made for business records that she or he follows.

To prevent that business record feed is displayed on the users' profile pages, clear this check box.

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

For more information about how to access this feature, go to *Settings* \> *Advanced Settings* \> *Integrations*.

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

*Wikis* 

</td>
<td valign="top">

Allows users to create wiki pages in the site.

For more information, in the user guide, see [About Wiki Pages](about-wiki-pages-3161f35.md).

</td>
</tr>
<tr>
<td valign="top">

*Persistent Navigation Bar* 

</td>
<td valign="top">

Create a custom site navigation bar with links to workspaces and workspace content without writing any code in the custom header. These tabs appear on all workpages throughout the site, below the top menu bar.

For more information, see [Home Pages](home-pages-000e8a1.md).

</td>
</tr>
<tr>
<td valign="top">

*Designate Blog Post Author* 

</td>
<td valign="top">

Allow a user to designate another user to create blog posts on their behalf. Although the other person can edit and publish the blog post, the name of the user who designated the other author is shown as the content creator.

For more information, in the User Guide, see [About Blog Posts](about-blog-posts-099621a.md).

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

*Show Hire Date in member profile* 

</td>
<td valign="top">

Display hire date information in profile pages.

For more information, see [Profiles](profiles-5c61b54.md).

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

When enabled, the Content Delivery Network outside the SAP data center caches documents to boost download speed. Globally distributed customers with offices located far away from their SAP Build Work Zone, advanced edition tenant data center host experiences significant performance improvements.

Tencent CDN is available on all data centers except for the EU Access regions \(EU11 and CH20\).

</td>
</tr>
<tr>
<td valign="top">

*Enable document download via CDN* 

</td>
<td valign="top">

When enabled, the Content Delivery Network outside the SAP data center caches documents to boost download speed. Globally distributed customers with offices located far away from their SAP SAP Build Work Zone, advanced edition tenant data center host experiences significant performance improvements.

Tencent CDN is available on all China region data centers - cn20-int1, cn40-int1, cn20-1, cn40-1.

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

For more information, in the User Guide, see [How to Use the Workpage Editor](how-to-use-the-workpage-editor-9164929.md).

</td>
</tr>
<tr>
<td valign="top">

*My Workspace*

</td>
<td valign="top">

If enabled, internal users can create their own My Workspace.

</td>
</tr>
<tr>
<td valign="top">

*Enable caching of user permissions in site and workspace menus*

</td>
<td valign="top">

If enabled, user permissions in site and workspace menus are cached to improve performance. Note that any permission changes will be reflected only after logging out and logging back in.

</td>
</tr>
</table>

