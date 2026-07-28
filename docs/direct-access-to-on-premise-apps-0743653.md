<!-- loio07436534d3ad4290ab617d27bddcc55c -->

# Direct Access to On-Premise Apps

The properties that are necessary create a runtime destination for direct access to on-premise SAP S/4HANA apps: SAPUI5, SAP GUI for HTML, Web Dynpro ABAP, and WebClient UI.



First, configure the general properties of the destination, and then add additional properties for SAP GUI for HTML.



## General Properties

> ### Note:  
> Dynamic tiles use OData calls to retrieve the dynamic data that is displayed on the tile. Therefore, direct access to dynamic tiles is not supported, unless the endpoint of the on-premise app is open to the Internet.

In the SAP BTP cockpit, under *Destinations*, create a new runtime destination with the following general properties:


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
> The destination name must be written in lowercase letters, and can't contain the character underscore \(\_\).

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

The URL points **directly** to the UI resources on the internal network host of the on-premise system.

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

</td>
</tr>
<tr>
<td valign="top">

`sap-platform`

</td>
<td valign="top">

ABAP

> ### Note:  
> This is an additional property that you need to add to the destination.



</td>
</tr>
<tr>
<td valign="top">

`sap-client` 

</td>
<td valign="top">

The client number of the ABAP system. For example: 120.

> ### Note:  
> This is an additional property that you need to add to the destination.



</td>
</tr>
</table>

> ### Note:  
> The *Check Connection* option is not relevant for this destination.

For more information, see [Create HTTP Destinations](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/783fa1c418a244d0abb5f153e69ca4ce.html).



<a name="loio07436534d3ad4290ab617d27bddcc55c__section_m2b_h1t_shb"/>

## SAP GUI for HTML Properties

For a SAP GUI for HTML app, you need to add the following additional properties:


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

`sap-sysid`

</td>
<td valign="top">

System ID of the SAP system \(also referred to as SID\)

</td>
</tr>
<tr>
<td valign="top">

`sap-rfc-host`

</td>
<td valign="top">

SAP application server host

</td>
</tr>
<tr>
<td valign="top">

`sap-msg-server`

</td>
<td valign="top">

SAP message server host

</td>
</tr>
<tr>
<td valign="top">

`sap-router`

</td>
<td valign="top">

SAP router string to use for networks being protected by a firewall

</td>
</tr>
<tr>
<td valign="top">

`sap-service`

</td>
<td valign="top">

A concatenated string that contains 4 characters: the first 2 characters are “32”; the last 2 characters are the instance number of the ABAP application server or the SAP system number

</td>
</tr>
<tr>
<td valign="top">

`sap-snc-name`

</td>
<td valign="top">

The name of the secure network communication \(snc\) system

</td>
</tr>
<tr>
<td valign="top">

`sap-snc-qop`

</td>
<td valign="top">

The snc quality of protection \(qop\) level – Authentication, Integrity, Encryption, Max available

</td>
</tr>
</table>

**Related Information**  


[Create Runtime Destinations to Access Apps](create-runtime-destinations-to-access-apps-a57c27c.md "In order to integrate certain apps into your site you need to create a destination.")

[Manual Integration of Apps](manual-integration-of-apps-ddb655a.md "Learn how to integrate apps manually.")

