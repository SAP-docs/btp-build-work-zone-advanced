<!-- loiof41f67f46e454be2a1986a8589695cf0 -->

# Tunneled Access to On-Premise Apps

The properties that are necessary to create a runtime destination for tunneled access to on-premise SAP S/4HANA apps: SAPUI5, SAP GUI for HTML, Web Dynpro ABAP, and WebClient UI.



First, configure the general properties of the destination, and then add additional properties for SAP GUI for HTML.



> ### Note:  
> Tunneled access requires the use of the Cloud Connector to provide a secure tunnel. However, note that using tunneled access might expose on-premise resources outside the organization network. Make sure that you examine the security measures of these resources before selecting to use tunneled access.



## General Properties

In the SAP BTP cockpit, under *Destinations*, create a new destination with the following general properties:


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

> ### Caution:  
> -   The destination name cannot contain the underscore \(\_\) character.
> 
> -   The destination name must be in lowercase letters.

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

The URL to the *Virtual Host* that is defined in the **Cloud Connector**.

> ### Note:  
> The URL must start with `http://`

> ### Note:  
> When using tunneled access to access an app, a URL with the following structure is generated:
> 
> <code><b>&lt;consumer subdomain&gt;-sapdelim-&lt;runtime destination name&gt;</b>.&lt;product&gt;...</code>
> 
> The length of the URL segment in bold must not exceed 63 characters. Note that `-sapdelim-` \(10 characters\) is a fixed string in this segment.



</td>
</tr>
<tr>
<td valign="top">

`ProxyType`

</td>
<td valign="top">

`OnPremise` 

</td>
</tr>
<tr>
<td valign="top">

sap-platform

</td>
<td valign="top">

`ABAP`

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
<tr>
<td valign="top">

`HTML5.DynamicDestination`

</td>
<td valign="top">

Add this property and set its value to `true` when you are creating a destination for a dynamic tile.

For more information, see [Configure Apps](configure-apps-4ba745b.md).

> ### Note:  
> This is an additional property that you need to add to the destination.

> ### Caution:  
> Adding an `HTML5.DynamicDestination` property and setting it to true, enables dynamic access to the destination to any logged-in user.
> 
> Therefore before adding this property to the destination, make sure that the underlying API is not public and requires the correct user credentials.



</td>
</tr>
</table>

> ### Note:  
> The *Check Connection* option is not relevant for this destination.

For more information, see [Create HTTP Destinations](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/783fa1c418a244d0abb5f153e69ca4ce.html).



<a name="loiof41f67f46e454be2a1986a8589695cf0__section_m2b_h1t_shb"/>

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

