<!-- loioa57c27ce348241a89d56874bef9a7a07 -->

# Create Runtime Destinations to Access Apps

In order to integrate certain apps into your site you need to create a destination.



<a name="loioa57c27ce348241a89d56874bef9a7a07__section_gcj_yfp_11c"/>

## Introduction

To integrate different app UI technologies in the SAP Build Work Zone, advanced edition, such as on-premise SAP S/4HANA apps \(SAP GUI for HTML, Web Dynpro ABAP, and SAPUI5\), and apps deployed on SAP BTP, Cloud Foundry environment \(HTML5\), you need to create an HTTP destination for accessing these apps, \(referred to as a runtime destination\) in the SAP BTP cockpit.

> ### Note:  
> This is a different flow from adding HTML5 apps from the default HTML5 Content Provider where the HTML apps are deployed to your tenant. This flow involved integrating apps from SAP BTP that are not available from the provider.



<a name="loioa57c27ce348241a89d56874bef9a7a07__section_crj_syk_mjb"/>

## Direct and Tunneled Access

The properties of the runtime destination differ according to the way you access the apps. You can set up access to apps in one of the following ways:


<table>
<tr>
<th valign="top">

Access Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Direct Access

</td>
<td valign="top">

Access is possible only **within** the corporate network \(or via VPN\).

Direct access is always used to access cloud apps.

In the destination configured on SAP BTP cockpit:

-   The *URL* points directly to the UI resources on the internal network host of the system.

-   The *Proxy Type* is *Internet*.




</td>
</tr>
<tr>
<td valign="top">

Tunneled Access

</td>
<td valign="top">

Access is possible from the corporate network or from the **Internet** using the **Cloud Connector** as a secure tunnel.

Tunneled access is used to access on-premise apps.

In the destination configured on SAP BTP cockpit:

-   The *URL* points to the *Virtual Host* that is defined in the Cloud Connector.

-   The *Proxy Type* is *On Premise*.




</td>
</tr>
</table>

> ### Note:  
> Direct access can also be used when accessing on-premise apps. However, in this case there is a limitation in accessing dynamic tiles \(because the data needs to be fetched from the backend\), unless the endpoint of the on-premise app is open to the Internet. For more information, see [Restrictions](restrictions-b259464.md).

> ### Note:  
> It is possible to combine in a single site applications that are configured to be available either via direct or tunneled access, by creating two destinations to the same system and configuring the apps accordingly. When accessing the site from the Internet, all the app tiles will be visible, but access will be possible only to the ones configured with the destination to the Cloud Connector.

**Related Information**  


[Direct Access to Cloud Apps](direct-access-to-cloud-apps-b695a24.md "The properties that are necessary to create a runtime destination for apps deployed to SAP BTP, Cloud Foundry environment and SAP BTP, ABAP environment.")

[Tunneled Access to On-Premise Apps](tunneled-access-to-on-premise-apps-f41f67f.md "The properties that are necessary to create a runtime destination for tunneled access to on-premise SAP S/4HANA apps: SAPUI5, SAP GUI for HTML, Web Dynpro ABAP, and WebClient UI.")

[Direct Access to On-Premise Apps](direct-access-to-on-premise-apps-0743653.md "The properties that are necessary create a runtime destination for direct access to on-premise SAP S/4HANA apps: SAPUI5, SAP GUI for HTML, Web Dynpro ABAP, and WebClient UI.")

