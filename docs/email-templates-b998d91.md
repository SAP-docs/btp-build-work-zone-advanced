<!-- loiob998d917712942efb566bf00cfe23475 -->

# Email Templates

Email templates allow an admin to customize the look and feel of both internal-facing and external-facing emails. This includes the ability to customize the branding, terminology, and add extra information to emails sent to end users.

You can manage your email templates on the *Theming & Branding* \> *Email Templates* screen.

You can set up different email templates for internal and external recipients and preview those changes before publishing.

When sending emails, SAP Build Work Zone, advanced edition creates a multiparty message \(as in [https://www.w3.org/Protocols/rfc1341/7\_2\_Multipart.html](https://www.w3.org/Protocols/rfc1341/7_2_Multipart.html)\) that contains two versions of the same email: an HTML version and a plain text version. When a user opens an email, their browser or email client shows the HTML version if supported, otherwise the plain text version is displayed. To enable multiparty messaging, you provide both HTML and plain text settings where relevant.

For the HTML version, use the following:

-   *Email Background Style*
-   *Page Background Style*
-   *Page Header HTML*
-   *Page Footer HTML*
-   *Footer HTML*

For the plain text version, use the following:

-   *Page Header Plain Text*
-   *Page Footer Plain Text*
-   *Footer Plain Text*

You can do the following on the *Email Templates* screen:


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

Set up email templates



</td>
<td valign="top">

1.  Select *Enable custom email template* to activate this feature and to enable you to make email template changes.

    The panel displays the preview of the email layout, with edit boxes.

2.  To change the CSS style sheets and the display of the given email sections, in the relevant section, choose *Edit* and make your changes on the right-hand side of the screen.
3.  For the page header, page footer, and footer sections, you can specify the language and enter translated text for that section.

    If any of these fields don't have a translation available for a language, the value for the “Unspecified” language is used.

4.  To save your changes, choose *Update*.

    The changes aren't published yet, but you can now preview and test them.




</td>
</tr>
<tr>
<td valign="top">

Preview and test email templates



</td>
<td valign="top">

After you've updated the templates, you preview and test changes to the email templates.

1.  Choose *Preview*.

    A *Send Email Template* dialog box opens.

2.  Enter the email addresses of the users who preview the revisions. Enter multiple email addresses by separating them with commas.
3.  Choose *Send*.

    Emails are sent to the recipients with your template changes.




</td>
</tr>
<tr>
<td valign="top">

Publish email template changes



</td>
<td valign="top">

When you've previewed the template changes, and want to set them to use, choose *Publish*.



</td>
</tr>
<tr>
<td valign="top">

Revert the email template changes



</td>
<td valign="top">

After updating an email template, you can choose *Revert to Published Version* to roll back your saved changes. The changes are reverted, and the published email template settings are restored.



</td>
</tr>
<tr>
<td valign="top">

Configure an email template for external users



</td>
<td valign="top">

1.  On the *External* tab, deselect the *Same settings used for Internal Email Template* checkbox.
2.  Make your changes, in the same way as you did for the internal template.
3.  Update, preview, and publish the changes.

You can always revert to a single email template. See the next task.



</td>
</tr>
<tr>
<td valign="top">

Revert to a single email template for both internal and external users



</td>
<td valign="top">

1.  To return to using the same email template for both internal and external users, select the *Same settings used for Internal Email Template* checkbox.

2.  Choose *Publish*.




</td>
</tr>
<tr>
<td valign="top">

Disable the use of email templates



</td>
<td valign="top">

1.  If you decide that you no longer want to use customized email templates, clear the *Enable custom email template* checkbox.

2.  Choose *Update* to save the change.




</td>
</tr>
</table>

