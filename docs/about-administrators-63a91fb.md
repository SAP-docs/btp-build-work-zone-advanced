<!-- loio63a91fb1d4dd4fefaf46358be0f8bfa4 -->

# About Administrators

Setting up of a site is done mainly by the different administrator roles. They design and manage the working environment to meet the unique needs of the company and to make it a user-friendly environment.



<a name="loio63a91fb1d4dd4fefaf46358be0f8bfa4__section_s5x_pgv_zkb"/>

## Administrator Types

In SAP Build Work Zone, advanced edition, there are five types of administrators as depicted in the diagram below. The company admin, area admin, and support admin are assigned as admins through roles, while the page content admin and the workspace admin are key users with specific set of capabilities, and are not assigned to any admin role.

![Company Administrator can access the full range of capabilities for configuring a site. Area administrators manage only content from their area. Support administrators have can access a subset of admin capabilities to support company administrators. Page content administrators have limited rights to manage the content of custom pages. Workspace administrators manage the workspace that they created or they can be assigned as administrator of a workspace that they're invited to.](images/Admin_Users_New_4b9be73.png)



<a name="loio63a91fb1d4dd4fefaf46358be0f8bfa4__section_nbn_gsw_12c"/>

## Assigning Users as Admins in Identity Authentication

As part of the SAP Build Work Zone, advanced edition/SAP SuccessFactors Work Zone onboarding process, several user groups are created in Identity Authentication to reflect the admin personas\*\*: Workzone\_Admin, Workzone\_Area\_Admin, and Workzone\_Support\_Admin. Each user group is assigned to a set of roles. For more information about which roles are assigned to each admin group, see [About Roles Types](about-roles-types-f38de6b.md). Users that are assigned to these groups are then being provisioned into SAP Build Work Zone, advanced edition/SAP SuccessFactors Work Zone with the relevant role assignments.

\*\* In SAP SuccessFactors Work Zone the Identity Authentication group names are slightly different.



<a name="loio63a91fb1d4dd4fefaf46358be0f8bfa4__section_ahw_ywl_trb"/>

## Assigning Administrators Manually

It is possible to assign internal users as administrators from the Admin Console:

1.  Open *Users* \> *Internal Users*.
2.  Select a user and under *Actions*, click *Edit*.
3.  In the *Edit Profile* screen, select the user type. Here you have the option to assign the user as a company administrator or support administrator.
4.  To assign a user as area administrator, first switch the view of the Admin Console from a company view to a relevant area view, and then under *User Type* you will see an option to choose area administrator.

> ### Note:  
> When assigning users as administrators via the Admin Console or via the SCIM API \(only possible for company admins\), these users will not be assigned to role collections in the SAP BTP cockpit. To make sure these users have all the necessary admin rights, including ones for integrated products such as the UI Theme Designer, it is required to assign the users all the relevant role collections in the cockpit, according to this list: [About Roles Types](about-roles-types-f38de6b.md).



<a name="loio63a91fb1d4dd4fefaf46358be0f8bfa4__section_idv_4rv_zkb"/>

## Administrator Permissions

The following table shows the access privileges of Company, Area, and Support administrators in the Administration Console. The Page Content Admin and the Workspace Admin aren't considered to be administrators and therefore aren’t listed in this table.


<table>
<tr>
<th valign="top">

Screen in Administration Console

</th>
<th valign="top">

Company Admin

</th>
<th valign="top">

Area Admin

</th>
<th valign="top">

Support Admin

</th>
</tr>
<tr>
<td valign="top">

*Change Admin Area*

</td>
<td valign="top">

√

</td>
<td valign="top">

√

</td>
<td valign="top">

√

</td>
</tr>
<tr>
<td valign="top">

*Overview Screen*

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Overview screen for the company

</td>
<td valign="top">

√

</td>
<td valign="top">

√

</td>
<td valign="top">

√

</td>
</tr>
<tr>
<td valign="top">

Overview screen for an area in the company

</td>
<td valign="top">

√

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

*General*

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

View general information of a site

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

√

</td>
</tr>
<tr>
<td valign="top">

*Users*

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Users

\(viewing and adding new users\)

</td>
<td valign="top">

√

</td>
<td valign="top">

√

area specific

</td>
<td valign="top">

√

</td>
</tr>
<tr>
<td valign="top">

User Lists

</td>
<td valign="top">

√

</td>
<td valign="top">

√

area specific

</td>
<td valign="top">

√

</td>
</tr>
<tr>
<td valign="top">

External Users

\(management\)

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

√

</td>
</tr>
<tr>
<td valign="top">

Alias Accounts

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

√

</td>
</tr>
<tr>
<td valign="top">

*Authentication & Authorization*

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

SAML Trusted IDPs

\(adding\)

</td>
<td valign="top">

√

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

SAML Local Identity Provider

\(configuration\)

</td>
<td valign="top">

√

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

*Theming & Branding*

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Theme Manager

\(configuration\)

</td>
<td valign="top">

√

</td>
<td valign="top">

√

area specific

</td>
<td valign="top">

√

</td>
</tr>
<tr>
<td valign="top">

Local Theme Designer

\(configuration\)

</td>
<td valign="top">

√

</td>
<td valign="top">

√

area specific

</td>
<td valign="top">

√

</td>
</tr>
<tr>
<td valign="top">

Email Templates

\(configuration\)

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

*Area & Workspace Configuration*

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

√

</td>
</tr>
<tr>
<td valign="top">

Administrative Areas

\(configuration\)

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Home Page

\(customization\)

</td>
<td valign="top">

√

</td>
<td valign="top">

√

area specific

</td>
<td valign="top">

√

</td>
</tr>
<tr>
<td valign="top">

Profiles

\(administration\)

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

√

</td>
</tr>
<tr>
<td valign="top">

Content Templates

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

√

</td>
</tr>
<tr>
<td valign="top">

Workspaces

\(management\)

</td>
<td valign="top">

√

</td>
<td valign="top">

√

area specific

</td>
<td valign="top">

√

</td>
</tr>
<tr>
<td valign="top">

Workspace Templates

\(administration\)

</td>
<td valign="top">

√

</td>
<td valign="top">

√

area specific

</td>
<td valign="top">

√

</td>
</tr>
<tr>
<td valign="top">

*UI Integration*

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Cards

</td>
<td valign="top">

√

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Widget Builders

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

*External Integrations*

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Business Content

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Microsoft Teams

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

External Solutions

</td>
<td valign="top">

√

</td>
<td valign="top">

√

area specific

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

OAuth Clients

\(adding\)

</td>
<td valign="top">

√

</td>
<td valign="top">

√

area specific

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Bots

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Extensions Catalog

</td>
<td valign="top">

√

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

*Feature Enablement*

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Kudos

\(configuration\)

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Hashtags

\(administration\)

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Knowledge Base Categories

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Features

\(configuration\)

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

*Compliance & Security*

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

External User Terms of Service

\(configuration\)

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Custom Terms of Service

\(configuration\)

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Content Administration

\(configuration\)

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Compliance

\(monitoring\)

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Security

\(configuration\)

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

*Analytics*

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Reports

</td>
<td valign="top">

√

</td>
<td valign="top">

√

area specific

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Third-Party Analytics

</td>
<td valign="top">

√

</td>
<td valign="top">

 

</td>
<td valign="top">

 

</td>
</tr>
</table>



<a name="loio63a91fb1d4dd4fefaf46358be0f8bfa4__section_zsn_14d_b2c"/>

## Page Content Administrators

Page content administrators can be subject matter experts for an area or company. They can manage the content and design of custom home pages.

You can assign page content administrators in the Admin Console, in *Users* \> *Internal Users*. Choose a user and click *Actions* \> *Make Page Content Admin*. If you don't see this option in the menu, it means that the user has never logged into the system.

Page content administrators can:

-   Edit content in the home page.
-   Manage translation.
-   Create tabs and subtab.
-   Create, publish, and maintain all content in home page repository.

