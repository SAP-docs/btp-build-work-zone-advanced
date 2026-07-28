<!-- loiod430ae74cc444e86a30cbda178cc7ab1 -->

# SAPUI5 Apps

The SAPUI5-specific property required to configure SAPUI5 apps. This is the same property for both SAP S/4HANA apps and cloud apps, however the way to locate the value is different.



<a name="loiod430ae74cc444e86a30cbda178cc7ab1__section_rnv_tfy_yhb"/>

## SAP S/4HANA App


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

<code><b>SAPUI5 Component Name (ID)</b></code> 

</td>
<td valign="top">

Enter the registered name of the SAPUI5 component, defined in the `component.js` file, without the `.component` suffix.

</td>
</tr>
</table>



### Locating the Property Value

To locate the value of the <code><b>SAPUI5 Component Name</b></code> for your SAPUI5 app, you can use the [SAP Fiori apps reference library](https://fioriappslibrary.hana.ondemand.com/).

**Procedure**

1.  In the SAP Fiori apps reference library, select the app you would like to configure.

2.  In the details pane of the app, click the *IMPLEMENTATION INFORMATION* tab.

3.  Open the *Configuration* section, and under *SAPUI5 Application*, you can find the value of the *SAPUI5 Component* in the corresponding column.


> ### Note:  
> Under *Target Mapping\(s\)*, you can also find the *Sematic Object* and *Semantic Action* values for this app.



<a name="loiod430ae74cc444e86a30cbda178cc7ab1__section_rfv_c1y_43b"/>

## Cloud App

> ### Note:  
> The SAP Build Work Zone, advanced edition and the consumed app must run in the **same subaccount**.
> 
> You must subscribe to the SAP Build Work Zone, advanced edition in the **same** subaccount as the app you want to consume.


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

<code><b>SAPUI5 Component Name (ID)</b></code> 

</td>
<td valign="top">

Launch the app and from the app URL copy the value of the following parameter: `sap-ui-app-id-hint` 

</td>
</tr>
</table>

**Related Information**  


[Manual Integration of Apps](manual-integration-of-apps-ddb655a.md "Learn how to integrate apps manually.")

[Configure Apps](configure-apps-4ba745b.md "Add a local app to your subaccount by manually configuring its properties in the dedicated editors.")

[Supported Browsers and Languages](supported-browsers-and-languages-99a0a18.md "")

