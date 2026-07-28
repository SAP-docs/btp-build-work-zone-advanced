<!-- loiof337b802513f437cb4f8cb02efe21990 -->

# Configure Destinations \(On Premise\)

To define a remote content provider, you need to configure a design-time and a runtime destination in the SAP BTP cockpit.



<a name="loiof337b802513f437cb4f8cb02efe21990__section_zl1_zrd_ymb"/>

## Design-Time Destination

The design-time destination defines the location from which to fetch the content that was exposed by the content provider.

When defining a content provider in the Channel Manager, you need to specify the design-time destination so that the provider's content can be fetched and displayed in the Content Explorer.

In the SAP BTP cockpit, in your subaccount, navigate to *Connectivity* \> *Destinations*.

Use the following properties to define the design-time destination:


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

Name

</td>
<td valign="top">

We recommend to add the suffix `dt` to the name.

> ### Note:  
> The name must contain only lowercase letters and must not contain the underscore \(\_\) character.



</td>
</tr>
<tr>
<td valign="top">

Type

</td>
<td valign="top">

HTTP

</td>
</tr>
<tr>
<td valign="top">

URL

</td>
<td valign="top">

The URL to the *Virtual Host* that is defined in the **Cloud Connector**.


<table>
<tr>
<th valign="top">

Content Provider

</th>
<th valign="top">

URL

</th>
</tr>
<tr>
<td valign="top">

SAP S/4HANA, SAP Business Suite

</td>
<td valign="top">

The URL is different, depending on the version of the content exposure tool that is in use:

-   V1

    `http://<host>:<port>/sap/bc/ui2/cdm3/entities`

-   V2

    `http://<host>:<port>/sap/bc/http/ui2/flp_content_exposure/entities`




</td>
</tr>
<tr>
<td valign="top">

SAP Enterprise Portal

</td>
<td valign="top">

`http://<host>:<port>/irj/servlet`

`/prt/prtrw/prtroot/com.sap.portal.cdm.persistency.EPCDMEntitiesComponent`

</td>
</tr>
</table>



</td>
</tr>
<tr>
<td valign="top">

Proxy Type

</td>
<td valign="top">

*OnPremise*

</td>
</tr>
<tr>
<td valign="top">

Authentication Method

</td>
<td valign="top">

> ### Note:  
> The method must also be supported on the side of the content provider.

The following method is supported: *Basic Authentication*.

To connect to the backend, use a service user with permission to read the CDM.

> ### Note:  
> *Principal Propagation* is not supported.



</td>
</tr>
</table>

Add the following additional property \(not relevant to SAP Enterprise Portal\):


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

sap-client

</td>
<td valign="top">

The client number of the ABAP system. For example: `120`

</td>
</tr>
</table>



<a name="loiof337b802513f437cb4f8cb02efe21990__section_szx_c53_ylb"/>

## Runtime Destination

The runtime destination defines the location from which to obtain the resources needed to run the federated apps in runtime.

> ### Note:  
> For SAP Enterprise Portal runtime destination information, please refer to [3286048](https://me.sap.com/notes/3286048)

> ### Note:  
> When federating applications from SAP S/4HANA or SAP Business Suite, there may be more than one runtime destination, and each runtime destination can have several aliases. When defining the content provider in the Channel Manager, you need to map the aliases to their corresponding destinations. For more information, see [Manage Content Providers \(On Premise\)](manage-content-providers-on-premise-021bc11.md).

Use the following properties to define the runtime destination:

> ### Note:  
> Multiple runtime destinations with identical URLs, but different authentication methods, are not supported.
> 
> In case multiple content channels are using the same backend, please make sure to use the same runtime destination with the same authentication method.


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

Name

</td>
<td valign="top">

We recommend to add the suffix `rt` to the name.

> ### Note:  
> The name must contain only lowercase letters and must not contain the underscore \(\_\) character.



</td>
</tr>
<tr>
<td valign="top">

URL

</td>
<td valign="top">

The URL of the Virtual Host of your Cloud Connector.

You find this value in the Cloud Connector Administration tool - select *Cloud to On-Premise* and in *Access Control*, use the value in the *Virtual Host* column.

For example: `http://qky:44300`

For more information, see [Set Up Cloud Connector](set-up-cloud-connector-009642f.md).

> ### Note:  
> For Web Dynpro ABAP applications, if they include SAP Business Client `(CompatibilityMode=TRUE)`, it is necessary to configure the value of the Cloud Connector virtual host to be the same as the full path. For more information, see the settings for *WDA Apps Integration Mode* in [Maintaining Launchpad App Descriptor Items](https://help.sap.com/docs/ABAP_PLATFORM_NEW/a7b390faab1140c087b8926571e942b7/2894d1b77e1f438ba0876a32f09124fd.html?version=latest).



</td>
</tr>
<tr>
<td valign="top">

Proxy Type

</td>
<td valign="top">

*OnPremise*

</td>
</tr>
<tr>
<td valign="top">

Authentication Method

</td>
<td valign="top">

Depends on the authentication method in use. To use single sign on \(SSO\), select *Principal Propagation*.

</td>
</tr>
</table>

Add the following additional properties:


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

HTML5.DynamicDestination

</td>
<td valign="top">

Add this property and set its value to `true` when you are creating a destination for a dynamic tile.

> ### Note:  
> -   In a productive environment, we do not recommend using this property with the *Basic Authentication* authentication method.
> 
> -   To enable CSRF protection via the approuter, set the`CEP.EnableCsrfProtection` destination property to *true* for all dynamic destinations where their respective backend doesn’t handle CSRF protection.
> 
>     If your backend is already protected, there’s no need to add this property.



</td>
</tr>
<tr>
<td valign="top">

sap-platform

</td>
<td valign="top">

`ABAP`

</td>
</tr>
<tr>
<td valign="top">

sap-client

</td>
<td valign="top">

The client number of the ABAP system. For example: `120`

</td>
</tr>
<tr>
<td valign="top">

sap-sysid

</td>
<td valign="top">

System ID of the SAP system \(also referred to as SID\). For example: `QKY`

</td>
</tr>
<tr>
<td valign="top">

launchpad.wa.productId, launchpad.wa.productVersion

</td>
<td valign="top">

To enable SAP Companion content \(on-screen help\) for the SAP S/4HANA apps running on this system \(destination\), you need to configure the product and version of the SAP Companion content that corresponds to the SAP S/4HANA apps. For more information, see [Activating SAP Companion Content](activating-sap-companion-content-8f77268.md).

</td>
</tr>
<tr>
<td valign="top">

sap-provider-label

</td>
<td valign="top">

Add this property to provide a user-friendly display name for the system of a destination. This system label is used in various runtime features, such as:

-   It can be displayed directly on each tile of an SAP S/4HANA app, if this setting was enabled in the Site Settings. For more information, see [Site Settings](site-settings-ca74965.md).

-   It is shown in the drop-down list of the search results \(only when using the *Spaces and Page - New Experience* view mode\) and in the Search Results page.

-   In the *Source System* field in the user *Default Values* option, located under the User Actions menu - *Settings* \> *Default Values*.

-   In the App Finder.




</td>
</tr>
<tr>
<td valign="top">

sap-service

</td>
<td valign="top">

A concatenated string that contains 4 characters: the first 2 characters are “32”; the last 2 characters are the instance number of the ABAP application server or the SAP system number. For example: `3200`

</td>
</tr>
</table>



### Runtime Destination for Dynamic Data

A dynamic tile displays data that is updated during runtime. To retrieve the dynamic data, it is necessary to define an additional runtime destination for dynamic data. When defining a content provider in the Channel Manager, the default value for the dynamic data destination is the same one as the default runtime destination. However, you can select a different destination than the default one, if required.

**Related Information**  


[Manage Content Providers \(On Premise\)](manage-content-providers-on-premise-021bc11.md "The administrator uses the Channel Manager to define, edit, and get updates from remote content providers running on premise.")

[Configure SSO](configure-sso-14f44d4.md "This section describes the steps for configuring Single Sign On (SSO) to access on-premise systems, such as SAP S/4HANA or SAP Business Suite, using principal propagation.")

