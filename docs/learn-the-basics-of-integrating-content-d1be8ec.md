<!-- loiod1be8ec2bcc641198abd60ed817b5d9e -->

# Learn the Basics of Integrating Content

Learn about the different ways to add business content to your site and the basic terms that you'll come across.



**What is business content?**

Business content is composed of business apps and of roles that define access permissions to those apps. In addition, there may be additional items, such as groups, catalogs, pages, and spaces.



**What is a content provider?**



A content provider is a source of business content that can be integrated in SAP Build Work Zone, advanced edition. This content can be exposed by remote cloud or on-premise systems, or by business solutions deployed locally to SAP BTP.



**What does federating business content from a content provider mean?**

Federating business content means integrating this content in SAP Build Work Zone, advanced edition, so that it can be accessed from business sites.

The following table describes the types of content providers that are available:


<table>
<tr>
<th valign="top">

Content Provider Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Remote content providers

</td>
<td valign="top">

This federation scenario consists of a content exposure step, which is done on the content provider side, and a content consumption step, which is done in SAP Build Work Zone, advanced edition.

On the consumer subaccount, the content is federated at the **role** level, and the exposed roles are added to the Content Manager together with their app assignments. You then assign a role to a site, so that business content \(such as apps, groups, catalogs\) assigned to a specific role can be accessed from the site.

Supported content providers include SAP IBP, SAP S/4HANA Cloud, SAP S/4HANA, SAP Business Suite, and SAP Enterprise Portal.

For more information, see:

-   [Content Providers - Cloud Solutions](content-providers-cloud-solutions-d92cf2f.md)

-   [Content Providers - On-Premise Solutions](content-providers-on-premise-solutions-a12a002.md)




</td>
</tr>
<tr>
<td valign="top">

HTML5 business solutions

</td>
<td valign="top">

An HTML5 business solution is developed and deployed to a provider subaccount, so that it can be consumed from different consumer subaccounts using destinations, as long as all the subaccounts use the same Identity Authetication tenant.

On the consumer subaccount, the content is federated at the **role** level, and the business roles are added to the Content Manager together with their app assignments. You then assign a role to a site, so that business content \(such as apps, groups, catalogs\) assigned to a specific role can be accessed from the site.

For more information, see [Federation of Business Solutions](federation-of-business-solutions-2686d71.md).

</td>
</tr>
<tr>
<td valign="top">

SAP BTP content providers

</td>
<td valign="top">

SAP BTP content providers are content providers that are developed and deployed to a specific subaccount on SAP BTP and must be consumed from the same subaccount. The following providers are available:

-   HTML5 Apps

    An HTML5 Apps provider reflects all the HTML5 apps that are deployed to the HTML5 App Repository that is assigned to the subaccount.

    For more information, see [HTML5 Apps Content Provider \(Local Repository\)](html5-apps-content-provider-local-repository-ad2103e.md).

-   Launchpad Modules

    You can consume launchpad modules that have been configured as content providers.

    For more information, see [Launchpad Modules Content Providers](launchpad-modules-content-providers-713f2f8.md).




</td>
</tr>
</table>





**What is manual integration of content?**

In this scenario, the site administrator manages the application configuration. Apps, groups, and catalogs are added manually and assigned to the business roles. This is done in the Content Manager \(the tool you use to manage the business content items for your subaccount: apps, catalogs, groups, roles, and shell plugins\).

For more information, see [Manual Integration of Apps](manual-integration-of-apps-ddb655a.md).

