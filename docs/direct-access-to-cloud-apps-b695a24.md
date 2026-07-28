<!-- loiob695a2432f5c465b83a94e80c9f9cd8e -->

# Direct Access to Cloud Apps

The properties that are necessary to create a runtime destination for apps deployed to SAP BTP, Cloud Foundry environment and SAP BTP, ABAP environment.



In the SAP BTP cockpit, under *Destinations*, create a new runtime destination with the following properties:


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

`Name`

</td>
<td valign="top">

The name of the destination.

> ### Note:  
> Destination name must be written in lowercase letters, and can't contain the character underscore \(\_\).

This name will be displayed in the *System* list in the *Properties* tab of the App editor, so that you can select it when configuring an app that runs on this system. For more information, see [Configure Apps](configure-apps-4ba745b.md).

> ### Caution:  
> If you change the name of the destination, it's not updated automatically in the app. You must select the updated *System* value from the list in the *Properties* tab of the App editor, for every app configured to use this destination.



</td>
</tr>
<tr>
<td valign="top">

`URL`

</td>
<td valign="top">

The domain of the app.


<table>
<tr>
<th valign="top">

Platform

</th>
<th valign="top">

Obtaining the Domain

</th>
</tr>
<tr>
<td valign="top">

SAP BTP, Cloud Foundry environment

</td>
<td valign="top">

To obtain the domain, launch the app and from the app URL, copy the domain.

For example, if the app URL is:

[https://ux-integration-cflp-apps-exciseduty-approuter.cfapps.sap.hana.ondemand.com/cp.portal/site\#ExciseDutyShipToMaster-configure%3Fsap-ui-app-id-hint=com.sap.icd.edpoc.ExciseDutyMasterDataShipToMaster](https://ux-integration-cflp-apps-exciseduty-approuter.cfapps.sap.hana.ondemand.com/cp.portal/site#ExciseDutyShipToMaster-configure%3Fsap-ui-app-id-hint=com.sap.icd.edpoc.ExciseDutyMasterDataShipToMaster)

Then the app domain is:

[https://ux-integration-cflp-apps-exciseduty-approuter.cfapps.sap.hana.ondemand.com](https://ux-integration-cflp-apps-exciseduty-approuter.cfapps.sap.hana.ondemand.com)

</td>
</tr>
<tr>
<td valign="top">

SAP BTP, ABAP environment

</td>
<td valign="top">

To obtain the domain, launch the app and from the app URL, copy the domain and add `-web`.

For example, if the app URL is:

```
https://95dd8c1f-9cd4-4de9-b928-0b89cd0c49b3.abap.eu10.hana.ondemand.com/ui#ExampleApp
```

Your app domain to which you have added `-web` is:

```
https://95dd8c1f-9cd4-4de9-b928-0b89cd0c49b3.abap-web.eu10.hana.ondemand.com
```



</td>
</tr>
</table>

> ### Note:  
> The URL must start with `https://`



</td>
</tr>
<tr>
<td valign="top">

`ProxyType`

</td>
<td valign="top">

`Internet`

This value indicates direct access to the app, and requires the app to be reachable within the network.

> ### Note:  
> The `OnPremise` value is currently not supported.



</td>
</tr>
<tr>
<td valign="top">

`Authentication`

</td>
<td valign="top">

`NoAuthentication`

This value specifies the authentication type to connect to the app.

</td>
</tr>
<tr>
<td valign="top">

`sap-platform` 

</td>
<td valign="top">


<table>
<tr>
<th valign="top">

Platform

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

SAP BTP, Cloud Foundry environment

</td>
<td valign="top">

`CF` 

</td>
</tr>
<tr>
<td valign="top">

SAP BTP, ABAP environment

</td>
<td valign="top">

`ABAP` 

</td>
</tr>
</table>

> ### Note:  
> This is an additional property you need to add to the destination.



</td>
</tr>
</table>

> ### Note:  
> The *Check Connection* option is not relevant for this destination.

For more information, see [Create HTTP Destinations](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/783fa1c418a244d0abb5f153e69ca4ce.html).

**Related Information**  


[Manual Integration of Apps](manual-integration-of-apps-ddb655a.md "Learn how to integrate apps manually.")

