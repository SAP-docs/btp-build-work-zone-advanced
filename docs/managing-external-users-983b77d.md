<!-- loio983b77d60c0a49109406a47d825ab3ee -->

# Managing External Users

Manage the external users that have access to the system.



External users must be added to the Identity Provider and then provisioned to SAP Build Work Zone, advanced edition. Once they have been provisioned, you can manage their settings in the *Administration Console* \> *Users* \> *External Users* screen.

For more information about how to add and configure external users, see [About External Users](about-external-users-4378212.md).


<table>
<tr>
<th valign="top">

Task

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Manage domains

</td>
<td valign="top">

To make external logins more secure, you can set either an `allowlist` or a `blocklist` of email domains from which external users can log in to SAP Build Work Zone, advanced edition.

This setting is only available if you've enabled the access of external users to workspaces in the *Administration Console* \> *Feature Enablement* \> *Features*:

![Shows the option to enable external users access to workspaces.](images/IAS_Credentials_1388c6e.png)

</td>
</tr>
<tr>
<td valign="top">

Filter users according to status

</td>
<td valign="top">

Select how to filter the users in the *Show* dropdown list.

</td>
</tr>
<tr>
<td valign="top">

Stop sending emails to an external user.

</td>
<td valign="top">

From the *Action* dropdown list, choose *Edit*, and in *Email Settings*, choose *Stop all emails*.

</td>
</tr>
<tr>
<td valign="top">

Review usage

</td>
<td valign="top">

Allows the company administrator to view a single user's complete history of which pages or content \(office documents, PDFs, images, videos, blogs, or wikis\) a user has viewed.

Includes also other user's profile pages, the comments they've made, which content they've liked, which content they've uploaded or modified, and which content they've deleted, including user, administrator, and system modified profile information.

> ### Note:  
> To enable this feature, the admin first needs to enable content administration in the *Compliance & Security* \> *Content Administration* screen.



</td>
</tr>
<tr>
<td valign="top">

Edit user profile

</td>
<td valign="top">

Next to the user, in the *Action* dropdown list, choose *Edit*. There are some details that can't be modified on SAP Build Work Zone, advanced edition side because they must be changed on the IdP side.

</td>
</tr>
<tr>
<td valign="top">

Export user data

</td>
<td valign="top">

You can trigger the export of an external user's data. When the export is done, you'll get a notification that includes the user's email telling you if the export was successful, or if it failed.

If the export was successful, a ZIP file is added to your user profile under *My Exports*. From here you can download the exported file.

> ### Note:  
> You can't export the data of more than one user at a time.



</td>
</tr>
</table>



<a name="loio983b77d60c0a49109406a47d825ab3ee__section_bdr_kmb_nsb"/>

## Additional Actions

Apart from the management tasks mentioned above, there are many other features that you can set up for your external users:


<table>
<tr>
<th valign="top">

Task

</th>
<th valign="top">

Description

</th>
<th valign="top">

More information

</th>
</tr>
<tr>
<td valign="top">

Show the number of external users and external user licenses.

</td>
<td valign="top">

See the *Overview* section in the Administration Console.

</td>
<td valign="top">

[Overview](overview-120b50d.md)

</td>
</tr>
<tr>
<td valign="top">

Configure a theme for external users.

</td>
<td valign="top">

Configure a theme for external users in *Theming & Branding*.

</td>
<td valign="top">

[About Local and Global Themes](about-local-and-global-themes-f68b18b.md)

</td>
</tr>
<tr>
<td valign="top">

Configure an email template for external users.

</td>
<td valign="top">

Configure an email template for external users under *Theming & Branding* \> *Email Templates*, or use the email template for internal users.

</td>
<td valign="top">

[Email Templates](email-templates-b998d91.md)

</td>
</tr>
<tr>
<td valign="top">

Configure a home page for external users.

</td>
<td valign="top">

Configure a home page for external users under *Area & Workspace Configuration* \> *Home Page*. If you don't configure a home page, a default home page is shown.

</td>
<td valign="top">

[Home Pages](home-pages-000e8a1.md)

</td>
</tr>
<tr>
<td valign="top">

Set a customized terms of service agreement for your external users .

</td>
<td valign="top">

Define the text of the terms of service agreement for external users from *Compliance & Security* \> *Terms of Service* screen.

</td>
<td valign="top">

[Terms of Service](terms-of-service-fa7a091.md)

</td>
</tr>
</table>

