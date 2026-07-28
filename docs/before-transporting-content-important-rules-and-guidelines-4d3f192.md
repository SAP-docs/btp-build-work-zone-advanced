<!-- loio4d3f19227b3549b3a78980aee771d37f -->

# Before Transporting Content - Important Rules and Guidelines

The rules and guidelines regarding transporting content and the related content that is also exported when exporting content items.



## What is Exported When Selecting Local Content Items in the Content Manager?

The following table describes the related content that is also exported when exporting selected local content items.


<table>
<tr>
<th valign="top">

Selected Local Content Item

</th>
<th valign="top">

Related Content That Is Also Transported

</th>
</tr>
<tr>
<td valign="top">

Role

</td>
<td valign="top">

-   Apps assigned to the role

-   Groups to which the apps are assigned

-   Catalogs to which the apps are assigned


> ### Note:  
> The Everyone role is **not** exported even if it was selected.
> 
> The related content of the Everyone role is also not transported.



</td>
</tr>
<tr>
<td valign="top">

Group

</td>
<td valign="top">

Apps assigned to the group

</td>
</tr>
<tr>
<td valign="top">

Catalog

</td>
<td valign="top">

Apps assigned to the catalog

</td>
</tr>
<tr>
<td valign="top">

App

</td>
<td valign="top">

Apps have no related content.

</td>
</tr>
</table>



<a name="loio4d3f19227b3549b3a78980aee771d37f__section_y5k_jlz_scc"/>

## Transporting Federated Roles and Federated Apps

In the Content Manager, you can select to export federated roles and federated apps. Federated roles are roles that were added from remote content channels or from HTML5 business solutions. Federated apps are apps that were added from SAP BTP content providers.

Note that before **importing** federated roles or apps, you need to make sure that:

-   Their content channel exists also in the Channel Manager of the target environment.

-   The ID of the content channel in the target environment is identical to the ID in the source environment. For more information, see [Edit the ID of a Content Provider](edit-the-id-of-a-content-provider-28d9ffa.md).

-   The role to which a federated app is assigned needs to be available on the target environment – either as a result of exporting it as well, or by adding the role to the content in the target environment.


Otherwise, the federated roles or apps will not be imported, and you will receive a warning message listing the missing content channels.

