<!-- loioc9610602fc8c4aeaac9567554c07dfe0 -->

# About the Common Data Model

Any content provider that wants to integrate its content in a site must comply with the same Common Data Model format, to allow integration of content from different sources in a unified way.



Any cloud and on-premise product that wishes to become a content provider of SAP Build Work Zone, and to integrate its content in a site, is required to provide its integration content in the standardized **Common Data Model \(CDM\)** format. The CDM content, that is written in a json file, defines the design-time business content of the site. That includes definitions for business applications, required user roles, visualization aspects such as tiles or cards, how they are grouped together in the site - spaces and pages or groups \(not recommended\), and how apps are launched - deep links or intents.

Complying with a unified schema, enables a seamless federation of content from the content provider into a **central content repository**, cross-product navigation within the site, and making the integrated content available to other scenarios such as SAP Start, Joule Work mobile app, and Joule.

When creating local applications, the administrator must manually configure the site design-time content, to complete the integration flow. However, in the federation scenario, when the content is integrated from content providers, the CDM definitions are received from the content provider and no manual assignments are required, except for assignment of content to the site itself and assignment to users \(when not using the Identity Provisioning service\).


<table>
<tr>
<th valign="top">

Guide

</th>
<th valign="top">

Link

</th>
</tr>
<tr>
<td valign="top">

CDM schema guidelines - a standardized document that describes the CDM metadata, structure, and properties.

</td>
<td valign="top">

[Common Data Model \(CDM\)](https://github.com/SAP/common-data-model/blob/main/README.md).

</td>
</tr>
</table>

**Related Information**  


[Guidelines for Creating a cdm.json](guidelines-for-creating-a-cdm-json-050c6f2.md "An overview of the Common Data Model entities.")

[Defining a Search App in the CDM](defining-a-search-app-in-the-cdm-dc14c90.md "A search app is a special business app that can be provided via CDM.")

