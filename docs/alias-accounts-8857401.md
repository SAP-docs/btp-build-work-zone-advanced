<!-- loio8857401c21b94dec9143cf14fa57d2d3 -->

# Alias Accounts

As a Company administrator, you can create user alias accounts and assign users to the account using a specific email address.



<a name="loio8857401c21b94dec9143cf14fa57d2d3__section_a25_2vd_1tb"/>

## What is an alias account?

Users can use alias accounts to easily identify a point of contact for a specific communication. For example, for new hire employees of a large, global organization, it's easier to contact a user named HR Helpdesk with HR-related questions than it is to find out the name of the exact contact person.

When you create an alias account, you typically give the user a different contact name or a nickname that is relevant to their role in the company.

A use case would be: Create three different alias accounts such as: `Customer Support` for customer inquiries, `Accounts` to manage invoices, and `HR HelpDesk` to manage HR-related issues. You can then assign multiple users to each alias account. For example, you can assign a few HR employees to the `HR HelpDesk` alias account. In this way, users who need to contact HR will have a single contact to use for their questions and any one of the users assigned to this alias account will be able to reply.

Once a user is assigned to a user alias account, they are able to access their alias account from the user actions menu under their avatar. If they're assigned to multiple alias accounts, they can switch between them.

> ### Note:  
> Alias users are SAP Build Work Zone, advanced edition local / technical users . They don't have corresponding accounts in other integrated products. For example, they don't have an account in SAP SuccessFactors and they can't view SAP Successfactors Learning content.

For more information, see [Switching Between User Alias Accounts](switching-between-user-alias-accounts-3f23100.md).



<a name="loio8857401c21b94dec9143cf14fa57d2d3__section_k1z_5wd_1tb"/>

## How to create an alias account?

You create alias accounts from the Administration Console as follows:

1.  From the Administration Console, open the *Users* section and click *Alias Accounts*.

2.  Click *New Alias Account*.

3.  In the *Basic Profile Information* area, below the automatically generated *Alias User ID*, enter the *Alias Account Name*.

4.  Optionally, in the *Description* text box, enter some text to describe the purpose of the alias.

5.  Click *Save*.




<a name="loio8857401c21b94dec9143cf14fa57d2d3__section_b5x_vyd_1tb"/>

## How to add users to an alias account

Once you've created the alias account, you can add users to it.

1.  In the *Add users to alias account* field, search for the name of each user that you want to add to the alias account. If you want to remove any of these users, then click *Remove* next to their name in the *Users* list.

2.  Click *Save*.




<a name="loio8857401c21b94dec9143cf14fa57d2d3__section_zs3_qzd_1tb"/>

## How to authenticate users of an alias account

Alias accounts can also be used as a system user \(for example, for a chatbot\) to work with other applications using APIs.

You can enable users that have alias accounts to use SAP Build Work Zone, advanced edition APIs, but first you need to create an OAuth client for them as follows:

1.  In the *API Access* section, click *Add OAuth2 Access Token*.

2.  Select an OAuth client from the dropdown list.

3.  Click *OK*.


The token information updates and displays in this section, along with the OAuth client name.

For more information, see [Add an OAuth Client](add-an-oauth-client-b3c804e.md).



<a name="loio8857401c21b94dec9143cf14fa57d2d3__section_ek1_y12_1tb"/>

## Other Settings


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

*Email Settings*



</td>
<td valign="top">

Enable sending emails to an alias account \(or you can stop them\).



</td>
</tr>
<tr>
<td valign="top">

*Contact Information*



</td>
<td valign="top">

Add the contact information of an alias user so that they can receive notifications.



</td>
</tr>
</table>

