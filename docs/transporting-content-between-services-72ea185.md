<!-- loio72ea1855cd624d3cbe687ec713d449e3 -->

# Transporting Content Between Services

The content that is transported from SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone when they are the source system, and the content that is transported to SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone when they are the target system.



<a name="loio72ea1855cd624d3cbe687ec713d449e3__section_sfh_lhl_f4b"/>

## Transporting selected content items from SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone

The following table describes what content is transported when SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone is the source system:


<table>
<tr>
<th valign="top">

Source

</th>
<th valign="top">

Target

</th>
<th valign="top">

What is transported?

</th>
<th valign="top">

What is filtered out?

</th>
</tr>
<tr>
<td valign="top">

SAP Build Work Zone, advanced edition/SAP SuccessFactors Work Zone

</td>
<td valign="top">

SAP Cloud Portal service

</td>
<td valign="top">

Selected business content items such as apps, roles, groups, catalogs, and shell plugins.

</td>
<td valign="top">

SAP Build Work Zone, advanced edition out-of-the-box content - not relevant for the SAP Cloud Portal service. In addition, apps with a card visualization are also not transported.

</td>
</tr>
<tr>
<td valign="top">

SAP Build Work Zone, advanced edition/SAP SuccessFactors Work Zone

</td>
<td valign="top">

SAP Build Work Zone, standard edition

</td>
<td valign="top">

Selected business content items such as apps, roles, groups, catalogs, and shell plugins.

</td>
<td valign="top">

SAP Build Work Zone, advanced edition out-of-the-box content - not relevant for SAP Build Work Zone, standard edition. In addition, apps with a card visualization are also not transported.

</td>
</tr>
<tr>
<td valign="top">

SAP Build Work Zone, advanced edition/SAP SuccessFactors Work Zone

</td>
<td valign="top">

SAP SuccessFactors Work Zone /SAP Build Work Zone, advanced edition

</td>
<td valign="top">

 

</td>
<td valign="top">

SAP Build Work Zone, advanced edition out-of-the-box content - this content does not need to be transported because it's already delivered with any site. Selected business content items such as apps, roles, groups, catalogs, and shell plugins.

</td>
</tr>
</table>



<a name="loio72ea1855cd624d3cbe687ec713d449e3__section_syn_qqm_wqb"/>

## Transporting selected content items to SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone

The following table describes what content is transported when SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone is the target system:


<table>
<tr>
<th valign="top">

Source

</th>
<th valign="top">

Target

</th>
<th valign="top">

What is transported?

</th>
<th valign="top">

What is filtered out?

</th>
</tr>
<tr>
<td valign="top">

SAP Cloud Portal service

</td>
<td valign="top">

SAP Build Work Zone, advanced edition/SAP SuccessFactors Work Zone

</td>
<td valign="top">

Selected business content items such as apps, roles, groups, catalogs, and shell plugins.

</td>
<td valign="top">

Freestyle site entities

For example, pages, menu, widgets

</td>
</tr>
<tr>
<td valign="top">

SAP Build Work Zone, standard edition

</td>
<td valign="top">

SAP Build Work Zone, advanced edition/SAP SuccessFactors Work Zone

</td>
<td valign="top">

Selected business content items such as apps, roles, groups, catalogs, and shell plugins.

</td>
<td valign="top">

Spaces and pages.

</td>
</tr>
<tr>
<td valign="top">

SAP SuccessFactors Work Zone/SAP Build Work Zone, advanced edition

</td>
<td valign="top">

SAP Build Work Zone, advanced edition/SAP SuccessFactors Work Zone

</td>
<td valign="top">

-   Selected business content items such as apps, roles, groups, catalogs, and shell plugins

-   SAP Build Work Zone, advanced edition content items such as home pages, workspaces, and workspace templates.




</td>
<td valign="top">

SAP Build Work Zone, advanced edition out-of-the-box content - this content doesn't need to be transported because it's already delivered with any site.

</td>
</tr>
</table>

> ### Note:  
> Exporting a site from SAP Cloud Portal service or SAP Build Work Zone, standard edition and importing it into SAP Build Work Zone, advanced edition isn't supported. You can only export/import selected content.

For more information about how to transport SAP Build Work Zone, advanced edition content items, see [Transporting Workspace Content Items](transporting-workspace-content-items-0a5c641.md)

