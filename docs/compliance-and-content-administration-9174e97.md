<!-- loio9174e97a7a1a4f2dada24e1ced4668b8 -->

# Compliance and Content Administration

In the *Compliance & Security* section, you set up the rules of compliance that your company follows, and monitor how your users comply to these rules.



<a name="loio9174e97a7a1a4f2dada24e1ced4668b8__section_r5p_dsj_hlb"/>

## Compliance

The *Compliance* screen, on the *Dictionary* tab, allows you to configure a pair of word lists or dictionaries. In the dictionary for compliance, you add words that can indicate an inappropriate communication of sensitive company information \(data leaks\). In the dictionary for profanity, you compile a list of offensive terms. Posts and private messages can be scanned against this dictionary for matches with the words in the dictionaries.

The compliance and profanity alerts don’t prevent users from posting inappropriate terms, nor do they send email notifications if users do post inappropriate terms. They only flag instances of users' use of the terms listed and enabled in the compliance and profanity dictionaries.


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

Enable compliance and profanity alerts



</td>
<td valign="top">

You enable this feature on the *Feature Enablement* \> *Features* screen. Content that has been posted before enabling the alerts isn’t scanned or flagged.



</td>
</tr>
<tr>
<td valign="top">

Configure the compliance dictionaries



</td>
<td valign="top">

For compliance as well as for profanity, on the *Dictionary* tab, choose *Add Term*, and enter a comma-separated list of terms.



</td>
</tr>
<tr>
<td valign="top">

Respond to dictionary matches



</td>
<td valign="top">

On the *Pending Flagged Items* tab, respond to matching items as follows:

-   Choose *Alert* to send notifications as follows:

    -   If the content is in a workspace, the workspace administrators are notified.

    -   If the content is outside of a workspace, for example, in a user's profile, the user's manager is notified.


    The notification email cites the flagged content and includes a hyperlink for reviewing the content.

-   To dismiss a flagged item that isn’t a problem, select the item and choose *Ignore*.

The item is removed from the *Pending Flagged Items* list, but remains accessible from the *History* list.



</td>
</tr>
<tr>
<td valign="top">

Disable dictionary terms



</td>
<td valign="top">

If the dictionary contains a term that you no longer want to be checked in scans, on the *Dictionary* tab, in the *Action* column, choose *Disable*.



</td>
</tr>
<tr>
<td valign="top">

Set an email address to receive a copy of feed items



</td>
<td valign="top">

This option allows you to set one or more email addresses that receive a copy of each feed event or private message sent to anyone in your company.

> ### Note:  
> Since routing all feed items can generate a massive amount of data, we recommended that you specify a dedicated email address to use with this feature.

-   Choose *Add Compliance Email*.




</td>
</tr>
<tr>
<td valign="top">

Remove email addresses for receiving copies of feed items



</td>
<td valign="top">

You clear all email addresses as follows:

1.  Choose *Add Compliance Email*.

2.  Choose *Clear* and then *Save*.


You can now add new email addresses.



</td>
</tr>
<tr>
<td valign="top">

Download a compliance report



</td>
<td valign="top">

On the *Compliance* screen, choose *Download Compliance Report* to go to the *Reports* screen, where you can run and download compliance reports.



</td>
</tr>
<tr>
<td valign="top">

View the compliance history



</td>
<td valign="top">

Choose the *History* tab.

A table shows all previously flagged items that have been responded to, and the *Action* column indicates whether they have been set as ignored or alerted.



</td>
</tr>
</table>



<a name="loio9174e97a7a1a4f2dada24e1ced4668b8__section_pk4_dsj_hlb"/>

## Content Administration

The *Compliance and Security* \> *Content Administration* screen allows you to manage *Abuse Reporting*, *Purge Settings*, and *Usage Auditing*.

You enable this feature on the *Feature Enablement* \> *Features* screen.


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

Enable content administration



</td>
<td valign="top">

By enabling content administration, you as a company or support administrator can access all workspaces in your site. You can then view, edit, and delete any workspace or content item within an administrative area or the entire company. Any items marked as inappropriate appear in the *Items Pending Review* panel.

Content administration is disabled by default.

On the *Content Administration* screen, choose *Enable Content Administration*.



</td>
</tr>
<tr>
<td valign="top">

Configure abuse reporting



</td>
<td valign="top">

*Abuse Reporting* allows users to report content as either spam or as abusive.

-   Make sure that content administration is enabled, and on the *Abuse Reporting* tab, choose *Configure Abuse Reporting*.


Any content that is reported by your users and meets the criteria that you configured is shown in the *Items Pending Review* panel.

Abuse reporting is disabled by default.



</td>
</tr>
<tr>
<td valign="top">

Respond to reported abuse



</td>
<td valign="top">

When users have tagged workspace activity as abuse or spam and the number of times equals the configured thresholds, then the workspace activity is hidden and queued for the company administrator to review. Notifications are sent to the company administrator to let them know there’s inappropriate content requiring their review.

Reported abuse that users have submitted appears in the *Items Pending Review* panel.

Each reported piece of content is shown as it originally appeared in the site, with the name of the user who posted it, and the date on which they posted it. There can also be additional details, such as the URLs for hyperlinked text or images. Also, the name of the person who reported the abuse is shown, together with any comments that they added about why they found the content inappropriate. A timestamp of how long ago the item was marked as inappropriate is displayed.

When reviewing an item marked as inappropriate, you don’t have to review the related feed posts. That way, all related comments and posts can be deleted or restored without one-by-one review.

Review the item and choose the appropriate response:

-   Choose *Restore* to return the content to its original location and viewable state.
-   Choose *Delete* to remove the content from the site.



</td>
</tr>
<tr>
<td valign="top">

Set the time after which trash cans are purged



</td>
<td valign="top">

In the *Purge Settings*, administrators can configure to permanently delete items that are older than the specified age.

-   Make sure that content administration has been enabled, and on the *Purge Settings* tab, enter the number of days and save your entry.


A daily purge of all items that have been in your company's users' trash cans for longer than the specified number of days is performed.



</td>
</tr>
<tr>
<td valign="top">

Audit a user's history



</td>
<td valign="top">

The *Usage Auditing* feature allows the company administrator to view a single user's complete history. The history shows which workpages or content \(such as PDFs, images, blogs, wikis, or other user's profile pages\) a user has viewed. The history also includes the user's comments and likes, which content they’ve uploaded, modified, and deleted \(including user, administrator, and system-modified profile information\). Audit events contain the user's name, the event type \(viewed, added, edited, or deleted\), and the exact system time when the event occurred.

-   Make sure that content administration has been enabled, and on the *Usage Auditing* tab, enter the settings and save your entries.

    > ### Note:  
    > Usage audits, even in CSV format, can be large, so make sure that you have plenty of free disk space to save these summaries.




</td>
</tr>
</table>

**Related Information**  


[Reports](reports-9fd82e0.md "SAP Build Work Zone, advanced edition administrator reports display information about many aspects of SAP Build Work Zone, advanced edition usage. Reports can include adoption metrics (such as user information, user contribution, and consumption activity), and disk usage statistics.")

