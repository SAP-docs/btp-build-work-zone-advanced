<!-- loioad2103e2fde342878bcf41a8ae8a0bd8 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# HTML5 Apps Content Provider \(Local Repository\)

An overview of federating content from the *HTML5 Apps* content provider.



When you subscribe to SAP Build Work Zone, advanced edition, the *HTML5 Apps* content provider is created automatically in the *Channel Manager*. At this point, the provider is empty, so that when you view it in the *Content Explorer*, it has no content. Any app that is deployed to SAP BTP, is automatically added as content to this provider.

> ### Note:  
> The *HTML5 Apps* content provider reflects the local repository of HTML5 apps deployed to the subaccount. It shouldn't be confused with an HTML5 business solution that is deployed to the subaccount as a SaaS application \(and usually consists of several UI modules, business logic and a connection to a database\). For more information about the HTML5 business solution type, see [Federation of Business Solutions](federation-of-business-solutions-2686d71.md).

To add content to the *HTML5 Apps* content provider, you need to perform the following tasks:


<table>
<tr>
<th valign="top">

Step

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

Develop an HTML5 app

</td>
<td valign="top">

[Basic Development Flow](basic-development-flow-ea482cc.md)

</td>
</tr>
<tr>
<td valign="top">

Expose the HTML5 app to SAP Build Work Zone, advanced edition by configuring its `manifest.json` file.

</td>
<td valign="top">

[Expose HTML5 Applications in SAP Build Work Zone, advanced edition](expose-html5-applications-in-sap-build-work-zone-advanced-edition-3a0e6d6.md)

</td>
</tr>
<tr>
<td valign="top">

Deploy the HTML5 app to the same subaccount as the subscription to SAP Build Work Zone, advanced edition.

</td>
<td valign="top">

[Build and Deploy Content](build-and-deploy-content-4394315.md)

</td>
</tr>
<tr>
<td valign="top">

In the Channel Manager, update the *HTML5 Apps* content provider to obtain the up-to-date content.

> ### Note:  
> It is necessary to update the content provider in the Channel Manager also after making any updates to the content of the provider, such as adding apps or changing destinations, for example.



</td>
<td valign="top">

In case of errors, click the report link to see more detailed information.

</td>
</tr>
</table>

To integrate apps and shell plugins from the *HTML5 Apps* content provider, you need to perform the following tasks:


<table>
<tr>
<th valign="top">

Step

</th>
<th valign="top">

Task

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

1.

</td>
<td valign="top">

In the *Content Explorer*, select and add the HTML5 applications that you want to run and any shell plugins that you want to use.

</td>
<td valign="top">

[Add Content to Your Subaccount](add-content-to-your-subaccount-507a8b5.md)

</td>
</tr>
<tr>
<td valign="top">

2.

</td>
<td valign="top">

In the *Content Manager*, assign the applications you added to the relevant groups and catalogs.

</td>
<td valign="top">

[Assign Apps to Groups](assign-apps-to-groups-6f60d52.md)

[Assign Apps to a Catalog \(Optional\)](assign-apps-to-a-catalog-optional-f63e4b5.md)

</td>
</tr>
<tr>
<td valign="top">

3.

</td>
<td valign="top">

In the *Content Manager*, assign the applications and shell plugins you added to the relevant roles.

</td>
<td valign="top">

[Assign Content to a Role](assign-content-to-a-role-baeaf6e.md)

</td>
</tr>
<tr>
<td valign="top">

4.

</td>
<td valign="top">

From the *Site Directory*, click :gear: on the site tile to open the Site Studio. In the Role Assignments screen, assign the roles/content channels to the site.

</td>
<td valign="top">

[Assign Roles to Your Site](assign-roles-to-your-site-7afe670.md)

</td>
</tr>
</table>

> ### Note:  
> You can create a **local copy** of an HTML5 app that was added from the HTML5 Apps content provider. For more information, see [Creating Local Copies of HTML5 Apps](creating-local-copies-of-html5-apps-7b456e6.md).

