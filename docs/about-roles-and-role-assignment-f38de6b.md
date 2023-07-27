<!-- loiof38de6bf7e774d4b86d8620597d397a2 -->

# About Roles and Role Assignment

There are three types of roles in SAP Build Work Zone, advanced edition: default roles that are assigned automatically during the onboarding process, local roles that are created manually to allow access to local apps, and remote roles that are added from external providers.



To allow access to applications on your site, you need to complete a 3-way assignment \(more details below\):

-   Assign apps to roles - done in the *Content Manager* screen.
-   Assign roles to site - done in the *Site Settings* screen.
-   Assign users to roles - done in the *Users* screen of the SAP BTP cockpit.



## Default Roles

In the *Content Manager*, you can find six default roles that were added to your subaccount during the onboarding to SAP Build Work Zone, advanced edition roles for the company administrator, area administrator, internal user, external user, SAP Workflow admin, and SAP Workflow user.

Each role is assigned to a relevant user group in SAP Cloud Identity Services - Identity Authentication and it allows access to apps that are relevant to that user type. For example, the administrator role is assigned to the Workzone\_Admin user group in the Identity Authentication service, and it allows access to the Administration Console. You can open the role in the *Content Manager* and see all assigned apps in the *Assignment* panel.

> ### Note:  
> These roles can't be removed.

For your reference, the following table describes the default role assignment to the Identity Authentication user groups and the corresponding role collections in SAP BTP cockpit:


<table>
<tr>
<th valign="top">

Persona



</th>
<th valign="top">

Identity Authentication Group



</th>
<th valign="top">

Role Collection - SAP Build Work Zone, advanced edition 



</th>
<th valign="top">

Role Collection - SAP SuccessFactors Work Zone



</th>
</tr>
<tr>
<td valign="top">

Company Admin



</td>
<td valign="top">

Workzone\_Admin



</td>
<td valign="top">

Workzone\_Admin

Workflow\_Admin\*

Workflow\_End\_User\*

Workzone\_XSUAA\_ Access



</td>
<td valign="top">

HR\_Workzone\_Admin

HR\_Workflow\_Admin \*

HR\_Workflow\_End\_User \*



</td>
</tr>
<tr>
<td valign="top">

Area Admin



</td>
<td valign="top">

Workzone\_Area\_Admin



</td>
<td valign="top">

Workzone\_Area\_Admin

Workflow\_End\_User\*



</td>
<td valign="top">

HR\_Workzone\_Area\_Admin

HR\_Workflow\_End\_User\*



</td>
</tr>
<tr>
<td valign="top">

Support Admin



</td>
<td valign="top">

Workzone\_Support\_Admin



</td>
<td valign="top">

Workzone\_Admin

Workflow\_End\_User\*



</td>
<td valign="top">

HR\_Workzone\_Admin

HR\_Workflow\_End\_User \*



</td>
</tr>
<tr>
<td valign="top">

Page Content Admin



</td>
<td valign="top">

Workzone\_Page\_Content\_Admin



</td>
<td valign="top">

Workzone\_End\_User

Workflow\_End\_User\*



</td>
<td valign="top">

HR\_Workzone\_End\_User

HR\_Workflow\_End\_User\*



</td>
</tr>
<tr>
<td valign="top">

Full Access User



</td>
<td valign="top">

Workzone\_End\_User



</td>
<td valign="top">

Workzone\_End\_User

Workflow\_End\_User\*



</td>
<td valign="top">

HR\_Workzone\_End\_User

HR\_Workflow\_End\_User \*



</td>
</tr>
<tr>
<td valign="top">

External User



</td>
<td valign="top">

Workzone\_User\_Type\_public



</td>
<td valign="top">

Workzone\_External\_User



</td>
<td valign="top">

HR\_Workzone\_External\_User



</td>
</tr>
</table>

\* Workflow roles are assigned only if there's a subscription to the Workflow service \(optional\).



<a name="loiof38de6bf7e774d4b86d8620597d397a2__section_gzq_3hj_hnb"/>

## Local Roles

Local roles are added to the subaccount to allow access to local apps \(cloud-based apps deployed on the subaccount or subscribed apps\).

> ### Note:  
> The role *Everyone* is a local role provided out-of-the-box and it can't be deleted.

To add a local role:

1.  In the *Content Manager*, add a new role. For every role that you add, a corresponding role collection is created in the SAP BTP cockpit, using the following values:

    SAP BTP role name - <role ID\>

    SAP BTP role description - <role title\>-<role description, if exists\>

2.  Assign local apps to the role in the *Assignments* panel.

For more information about integrating local apps, see [Manual Integration of Apps](https://help.sap.com/viewer/8c8e1958338140699bd4811b37b82ece/Cloud/en-US/ddb655ae45e44d499f2fa0ce503a46d9.html) 



<a name="loiof38de6bf7e774d4b86d8620597d397a2__section_jvw_51l_hnb"/>

## Remote Roles

Remote roles are added to the subaccount to allow access to remote apps. They are provided by external content providers.

When you configure an external content provider in the *Provider Manager* editor and you fetch its content, remote roles are added to the *Content Explorer* tab in the *Content Manager*.

You can add roles from the *Content Explorer* to your subaccount. Each role is added with its assigned apps.

For every role that you add, a corresponding role collection is created in the SAP BTP cockpit, using the following values:

SAP BTP role name - <role ID\>

SAP BTP role description - <role title\>-<role description, if exists\>

For more information about integrating remote apps, see [Federation of Remote Content Providers](https://help.sap.com/viewer/8c8e1958338140699bd4811b37b82ece/Cloud/en-US/fa46cc3ffdb048e9bbadafb2429480d9.html) 



<a name="loiof38de6bf7e774d4b86d8620597d397a2__section_ggn_w1l_hnb"/>

## Assigning Roles to the Site

To allow access to your site, assign local and remote roles to your site as follows:

1.  Open the *Site Directory*.
2.  Click the cog button on your site tile to open the *Site Settings* screen.
3.  Click the *Edit* button and add the local and remote roles in the *Assignments* panel on the right.
4.  Click *Save*.

