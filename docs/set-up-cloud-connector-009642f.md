<!-- loio009642f3831041d9a8d89651158a6099 -->

# Set Up Cloud Connector

Set up the Cloud Connector, which serves as a link between applications running on the platform and on-premise systems. This set up is required when integrating apps from remote on-premise content providers, and when manually integrating apps from on-premise systems.



**Prerequisites**

-   You have installed and started the Cloud Connector

    For more information, see [Installation](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/57ae3d62f63440f7952e57bfcef948d3.html).


**Procedure**

1.  After installing and starting the Cloud Connector, log on to the administration UI and perform the required configuration to make your Cloud Connector operational.

    This includes logging on to the Cloud Connector, setting up connection parameters and an HTTPS proxy, and establishing a connection to the platform.

    For more information, see [Initial Configuration](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/db9170a7d97610148537d5a84bf79ba2.html).

2.  As soon as the initial setup is complete, the tunnel to the cloud endpoint is open, but no requests are allowed to pass. Go to *Cloud To On-Premise* and perform the *Access Control* setup, to specify the back-end systems and resources that can be accessed by your cloud applications:

    -   For a back-end system, specify properties such as the *Backend Type*, the *Protocol*, the *Internal Host*, and the *Virtual Host*.

        > ### Note:  
        > The *Virtual Host* is used as the *URL* property for the destination configuration in the SAP BTP cockpit.

        For more information, see the section *Expose Intranet Systems* in [Configure Access Control \(HTTP\)](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e7d4927dbb571014af7ef6ebd6cc3511.html).

    -   For a resource \(URL path\), you need to grant access to the resources listed in the tables below.

        For more information, see the section *Limit the Accessible Services for HTTP\(S\)* in [Configure Access Control \(HTTP\)](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e7d4927dbb571014af7ef6ebd6cc3511.html).



**Access Control**

The following table lists the required resources that need to be configured for each component:


<table>
<tr>
<th valign="top">

Front End Client

</th>
<th valign="top">

Back-end Client

</th>
<th valign="top">

Embedded Client

</th>
</tr>
<tr>
<td valign="top">

`/sap/bc/bsp/sap/`

</td>
<td valign="top">

`/sap/bc/bsp/sap/`

</td>
<td valign="top">

`/sap/bc/bsp/sap/`

</td>
</tr>
<tr>
<td valign="top">

`/sap/bc/lrep/`

</td>
<td valign="top">

`/sap/bc/gui/`

</td>
<td valign="top">

`/sap/bc/gui/`

</td>
</tr>
<tr>
<td valign="top">

`/sap/bc/ui2/app_index/`

</td>
<td valign="top">

`/sap/bc/ui5_ui5/sap/`

</td>
<td valign="top">

`/sap/bc/lrep/`

</td>
</tr>
<tr>
<td valign="top">

`/sap/bc/ui2/cdm3/`

</td>
<td valign="top">

`/sap/bc/webdynpro/`

</td>
<td valign="top">

`/sap/bc/ui2/app_index/`

</td>
</tr>
<tr>
<td valign="top">

`/sap/bc/ui2/flp/`

</td>
<td valign="top">

`/sap/opu/odata/`

</td>
<td valign="top">

`/sap/bc/ui2/cdm3/`

</td>
</tr>
<tr>
<td valign="top">

`/sap/bc/ui5_ui5/sap/`

</td>
<td valign="top">

`/sap/public/bc/uics/`

</td>
<td valign="top">

`/sap/bc/ui2/flp/`

</td>
</tr>
<tr>
<td valign="top">

`/sap/bc/ui5_ui5/ui2/`

</td>
<td valign="top">

`/sap/public/bc/ur/`

</td>
<td valign="top">

`/sap/bc/ui5_ui5/sap/`

</td>
</tr>
<tr>
<td valign="top">

`/sap/opu/odata/`

</td>
<td valign="top">

`/sap/public/bc/webdynpro/`

</td>
<td valign="top">

`/sap/bc/ui5_ui5/ui2/`

</td>
</tr>
<tr>
<td valign="top">

`/sap/public/bc/ui5_ui5`

</td>
<td valign="top">

`/sap/public/icmandir/its/`

</td>
<td valign="top">

`/sap/bc/webdynpro/`

</td>
</tr>
<tr>
<td valign="top">

`/sap/public/bc/uics/`

</td>
<td valign="top">

`/sap/bc/nwbc/`

</td>
<td valign="top">

`/sap/opu/odata/`

</td>
</tr>
<tr>
<td valign="top">

`/sap/public/bc/ui2`

</td>
<td valign="top">

`/sap/bc/bsp/srmnxp/`

</td>
<td valign="top">

`/sap/public/bc/ui5_ui5`

</td>
</tr>
<tr>
<td valign="top">

``

</td>
<td valign="top">

 

</td>
<td valign="top">

`/sap/public/bc/uics/`

</td>
</tr>
<tr>
<td valign="top">

``

</td>
<td valign="top">

 

</td>
<td valign="top">

`/sap/public/bc/ur/`

</td>
</tr>
<tr>
<td valign="top">

``

</td>
<td valign="top">

 

</td>
<td valign="top">

`/sap/public/bc/webdynpro/`

</td>
</tr>
<tr>
<td valign="top">

``

</td>
<td valign="top">

 

</td>
<td valign="top">

`/sap/public/icmandir/its/`

</td>
</tr>
<tr>
<td valign="top">

``

</td>
<td valign="top">

 

</td>
<td valign="top">

`/sap/bc/nwbc/`

</td>
</tr>
<tr>
<td valign="top">

``

</td>
<td valign="top">

 

</td>
<td valign="top">

`/sap/bc/bsp/srmnxp/`

</td>
</tr>
<tr>
<td valign="top">

``

</td>
<td valign="top">

 

</td>
<td valign="top">

`/sap/public/bc/ui2`

</td>
</tr>
</table>

**Related Information**  


[Configure Destinations \(On Premise\)](configure-destinations-on-premise-f337b80.md "To define a remote content provider, you need to configure a design-time and a runtime destination in the SAP BTP cockpit.")

[Tunneled Access to On-Premise Apps](tunneled-access-to-on-premise-apps-f41f67f.md "The properties that are necessary to create a runtime destination for tunneled access to on-premise SAP S/4HANA apps: SAPUI5, SAP GUI for HTML, Web Dynpro ABAP, and WebClient UI.")

