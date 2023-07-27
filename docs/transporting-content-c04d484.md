<!-- loioc04d4845579946f7943ab18d8175f1b5 -->

# Transporting Content

In SAP Build Work Zone, advanced edition, you can transport business content between different services and different environments. You can also transport certain site content items between subaccounts and data centers.



<a name="loioc04d4845579946f7943ab18d8175f1b5__section_ybn_vfy_cpb"/>

## Overview

There are times when you want to transport content between sites. The transport process is straight forward. In general, you simply export the content from the source system and import the exported file back into the target system.

**Use Cases:**

-   You can transport content between environments – for example, Dev, Test, and Production environments.

-   You can transport content between services – for example, between the SAP Build Work Zone, advanced edition, SAP Cloud Portal, SAP Build Work Zone, standard edition, and SAP SuccessFactors Work Zone services.

-   You can also transport various types of content items from one subaccount to another subaccount - for example, home pages, workspaces, and workspace templates.




<a name="loioc04d4845579946f7943ab18d8175f1b5__section_sfh_lhl_f4b"/>

## What content can be transported between services?



### Transporting selected content items from SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone

The following table describes what content is transported when SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone is the source:


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

SAP Build Work Zone, advanced edition out-of-the-box content - not relevant for the SAP Cloud Portal service.



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

SAP Build Work Zone, advanced edition out-of-the-box content - not relevant for SAP Build Work Zone, standard edition.



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



### Transporting selected content items to SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone

The following table describes what content is transported when SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone is the target:


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

Nothing



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

For more information about how to transport business content, see [Transporting Business Content](transporting-business-content-e89a79c.md)

For more information about how to transport SAP Build Work Zone, advanced edition content items, see [Transporting Home Pages and Workspaces](transporting-home-pages-and-workspaces-0a5c641.md)



<a name="loioc04d4845579946f7943ab18d8175f1b5__section_syn_qqm_wqb"/>

## Transporting Content via SAP Cloud Transport Management Service

You can also use the SAP Cloud Transport Management service to transport content from one system to another. This includes transporting content between landscapes, such as from DEV to TEST, or between data centers. To use SAP Cloud Transport Management, you need to subscribe to it from the source system.

For more information, see [Transporting Content via SAP Cloud Transport Management Service](https://help.sap.com/viewer/8c8e1958338140699bd4811b37b82ece/Cloud/en-US/3d644a1463ba4db7bc7a40b559f3cac1.html).

