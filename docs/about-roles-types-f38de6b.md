<!-- loiof38de6bf7e774d4b86d8620597d397a2 -->

# About Roles Types

There are three types of roles in SAP Build Work Zone, advanced edition: default roles that are assigned automatically during the onboarding process, local roles that are created manually to allow access to local apps, and remote roles that are added from remote content providers.



The following sections describe the role types and their assignments in SAP Build Work Zone, advanced edition:



<a name="loiof38de6bf7e774d4b86d8620597d397a2__section_default_roles"/>

## Default Roles

After completing the onboarding to SAP Build Work Zone, advanced edition, default roles are added to the Content Manager.

For every default role that is created during the onboarding process, a corresponding role collection is created in the SAP BTP cockpit.

> ### Note:  
> The default roles can't be removed from the Content Manager.

The following table shows you the default roles that appear in the SAP BTP cockpit as role collections and role titles in the Content Manager:


<table>
<tr>
<th valign="top">

Role Title in the Content Manager

</th>
<th valign="top">

Role Collection Name in the SAP BTP Cockpit

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

SAP Work Zone Administrator Read Only

</td>
<td valign="top">

Workzone\_Admin\_Read\_Only

</td>
<td valign="top">

A role that enables a support administrator to support the company administrator by giving them access to a subset of features.

This role is mainly used to allow support admins access to the UI screens when investigating issues without the ability to change customer configurations.

</td>
</tr>
<tr>
<td valign="top">

SAP Work Zone Administrator

</td>
<td valign="top">

Workzone\_Admin

</td>
<td valign="top">

A role assigned to company administrators. Enables them to carry out admin tasks in the Administration Console and to configure sites according to the organization’s needs.

</td>
</tr>
<tr>
<td valign="top">

SAP Work Zone Area Administrator

</td>
<td valign="top">

Workzone\_Area\_Admin

</td>
<td valign="top">

A role assigned to area administrators. Enables them to carry out tasks in a specific area. Can also do a smaller subset of the company administrator’s tasks.

</td>
</tr>
<tr>
<td valign="top">

SAP Work Zone Internal End User

</td>
<td valign="top">

Workzone\_End\_User

</td>
<td valign="top">

A role assigned to internal end users, allowing them to use SAP Build Work Zone, advanced edition.

</td>
</tr>
<tr>
<td valign="top">

SAP Work Zone External End User

</td>
<td valign="top">

Work Zone\_External \_User

</td>
<td valign="top">

A role assigned to external end users, allowing them to use SAP Build Work Zone, advanced edition.

</td>
</tr>
<tr>
<td valign="top">

SAP Workflow service Admin Role

</td>
<td valign="top">

Workflow\_Admin

</td>
<td valign="top">

Role assigned to administrators working on SAP Workflow service.

</td>
</tr>
<tr>
<td valign="top">

SAP Workflow service End User Role

</td>
<td valign="top">

Workflow\_End\_User

</td>
<td valign="top">

Role assigned to end users working on SAP Workflow service.

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

An end user role for all users in the company.

</td>
</tr>
</table>

> ### Note:  
> For more information about the mapping of role collections to the Identity Authentication Groups, see [Run the Booster](https://help.sap.com/docs/build-work-zone-advanced-edition/sap-build-work-zone-advanced-edition/run-booster). Open this section: *Manual Execution of the Booster*.

The following roles are default Digital Workplace Service \(DWS\) roles that are added via the Administration Console and do not appear in the SAP BTP cockpit.


<table>
<tr>
<th valign="top">

Role

</th>
<th valign="top">

Role ID

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Support Admin

</td>
<td valign="top">

Workzone\_Support\_Admin

</td>
<td valign="top">

A role that enables a support administrator to support the company administrator by giving them access to a subset of features. This will enable them to investigate issues without being able to change customer data or configurations.

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

A key user role giving users limited admin rights designated to them by an administrator to create content.

</td>
</tr>
<tr>
<td valign="top">

Workspace Administrator

</td>
<td valign="top">

 

</td>
<td valign="top">

A key user role that allows users to create a workspace. By creating a workspace, this user becomes the workspace administrator.

</td>
</tr>
</table>



<a name="loiof38de6bf7e774d4b86d8620597d397a2__section_local_roles"/>

## Local Roles

You create local roles to allow access to local apps \(cloud-based apps deployed on the subaccount or subscribed apps\). When you create a local role in the *Content Manager*, a corresponding role collection is created in the SAP BTP cockpit.

To allow users to access apps in a runtime site, you need to perform the following assignments:


<table>
<tr>
<th valign="top">

Where?

</th>
<th valign="top">

Assignment

</th>
</tr>
<tr>
<td valign="top">

Content Manager

</td>
<td valign="top">

In the role editor, assign the relevant apps to the role.

For more information, see [Assign Content to a Role](assign-content-to-a-role-baeaf6e.md).

</td>
</tr>
<tr>
<td valign="top">

Site Studio

</td>
<td valign="top">

In the *Role Assignments* screen, assign roles and content channels to the site.

For more information, see [Assign Roles to Your Site](assign-roles-to-your-site-7afe670.md).

</td>
</tr>
<tr>
<td valign="top">

SAP BTP cockpit

</td>
<td valign="top">

Assign users to the role collection.

</td>
</tr>
</table>

> ### Note:  
> The *Everyone* role is a local role provided out-of-the-box and it can't be deleted.

For more information, see [Manual Integration of Apps](manual-integration-of-apps-ddb655a.md).



<a name="loiof38de6bf7e774d4b86d8620597d397a2__section_remote_roles"/>

## Remote Roles

Remote roles are added to the subaccount to allow access to remote apps. The remote roles and apps are provided by remote content providers.

In the *Channel Manager*, you create a content provider to consume the remote content from the provider. When you create the content provider, you can choose whether to manage its roles through role collections in SAP BTP, or to use the Identity Provisioning service to provision the authorizations directly from the Identity Provider.

As a result of creating the content provider, its roles are added to the *Content Manager*. When you view a role in the *Content Manager*, you can see the apps that are assigned to it.

To allow users to access apps in a runtime site, you need to perform the following assignments:


<table>
<tr>
<th valign="top">

Where?

</th>
<th valign="top">

Assignment

</th>
</tr>
<tr>
<td valign="top">

Site Directory

</td>
<td valign="top">

In the site, assign the role to the site.

For more information, see [Assign Roles to Your Site](assign-roles-to-your-site-7afe670.md).

</td>
</tr>
<tr>
<td valign="top">

SAP BTP cockpit

</td>
<td valign="top">

If you did not select the Identity Provisioning service, you need to assign users to the role collection.

</td>
</tr>
</table>

For more information, see [Federation of Remote Content Providers](https://help.sap.com/viewer/8c8e1958338140699bd4811b37b82ece/Cloud/en-US/fa46cc3ffdb048e9bbadafb2429480d9.html).

