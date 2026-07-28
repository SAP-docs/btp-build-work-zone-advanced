<!-- loioce262ff4eb134bdc82852cee15cdfb81 -->

# Supported Declarative and Component Card Features

An overview of card features and whether they are supported on different SAP Build Work Zone editions.



## Background

UI integration cards consist of different card types, such as declarative cards, component cards, etc. For more information see, [Card Types](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/overview/cardTypes).

While declarative cards are fully supported in both SAP Build Work Zone, advanced edition and SAP Build Work Zone, standard edition, this is not the case in component cards. Some component card features are only supported in SAP Build Work Zone, advanced edition.

This gap becomes an issue when cards are uploaded as app visualizations in SAP Build Work Zone, standard edition. If the uploaded card contains a reference to a feature that is only supported in SAP Build Work Zone, advanced edition, the card will fail to render at runtime. This issue affects both SAP Build Work Zone, standard edition Web client and its mobile client on the Joule Work mobile app.

> ### Note:  
> In design-time, the card visualization will be available in the content gallery and will be displayed inside the page editor. However, the card will fail to render at runtime and will result in an error.



<a name="loioce262ff4eb134bdc82852cee15cdfb81__section_oz5_pvk_5dc"/>

## Supported & Not Supported Card Features

The following table provides information about different card features and whether they are supported on different clients.


<table>
<tr>
<th valign="top">

Card Feature

</th>
<th valign="top">

SAP Build Work Zone, advanced edition \(Web\)

</th>
<th valign="top">

SAP Build Work Zone, standard edition \(Web\)

</th>
<th valign="top">

Joule Work Mobile App

</th>
</tr>
<tr>
<td valign="top">

Declarative Card

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Declarative Card with Extension

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Component Card

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

No - filtered out

</td>
</tr>
<tr>
<td valign="top">

Read context variables for **all editions**:

-   `sap.workzone.currentUser` 



</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Read context variables for SAP Build Work Zone, advanced edition:

-   `global_uuid`, `user_type`, `time_zone`, `sap.workzone.currentUser`, `sap.workzone.currentWorkspace`, `sap.workzone.currentCompany`



</td>
<td valign="top">

Yes

</td>
<td valign="top">

No

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Read context variables for SAP SuccessFactors Work Zone and SAP Build Work Zone, advanced edition contexts:

-   `sap.successfactors.*`



</td>
<td valign="top">

Yes

</td>
<td valign="top">

No

</td>
<td valign="top">

No

</td>
</tr>
<tr>
<td valign="top">

Read/Add/Change/Refresh context variables

</td>
<td valign="top">

Yes

</td>
<td valign="top">

No

</td>
<td valign="top">

No

</td>
</tr>
</table>

> ### Note:  
> -   Read context support means that the host environment supports the following methods: `getContextValue` and `getContext`.
> -   Conext Awareness \(last item\) means that the host environment also supports the method `updateContext`.

