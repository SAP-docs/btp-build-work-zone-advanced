<!-- loio75aaf054cba44ef2b7f4579ba3d1a390 -->

# Email Notifications

Configure your preferred email SMTP server that will be used to send email notifications.



Notifications can be configured based on your specific scenario. For local notifications, SAP Build Work Zone, advanced edition provides two native notification mechanisms. The separate SAP Notification service is used for notifications issued from other providers.



The native notification mechanisms provided by SAP Build Work Zone, advanced edition cover all events within the site, such as new and changed content, requests to access, and actions related to workspaces. These two mechanisms allow you to manage notifications:

1.  By using the **default SMTP server** provided by SAP Build Work Zone, advanced edition.

2.  Or by switching to your own **custom SMTP server**.


**For Scenarios Utilizing Local Notifications:**


<table>
<tr>
<th valign="top">

Notification Mechanism

</th>
<th valign="top">

Email Configuration

</th>
</tr>
<tr>
<td valign="top">

SAP Build Work Zone, advanced edition - Default

</td>
<td valign="top">

You can enable/disable the notification emails, choose the email frequency, and more. For more information, see [Configuring Notification Emails](configuring-notification-emails-6076729.md).

</td>
</tr>
<tr>
<td valign="top">

SAP Build Work Zone, advanced edition - Custom SMTP Server

</td>
<td valign="top">

To switch to your own SMTP server, provide the server settings in the Admin Console. For more information, see [Configure a Custom SMTP Server](configure-a-custom-smtp-server-407647d.md).

</td>
</tr>
</table>

Use the SAP Notification service if you wish to receive notifications from multiple notification providers in a centralized manner. However, it is crucial to note that local SAP Build Work Zone, advanced edition notifications will still be managed and processed through the pre-configured native notification mechanism. These notifications are not handled by the SAP Notification service.

**For Scenarios with Multiple Notification Providers:**


<table>
<tr>
<th valign="top">

Notification mechanism

</th>
<th valign="top">

Email Configuration

</th>
</tr>
<tr>
<td valign="top">

SAP Notification service

</td>
<td valign="top">

To receive emails from the SAP Notification service, configure destinations to the SMTP server. For more information, see [Configuring an SMTP Mail Destination](configuring-an-smtp-mail-destination-e403f2c.md).

</td>
</tr>
</table>

