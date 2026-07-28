<!-- loioa3eceb585c9041218f4abc24eacbff95 -->

# Run Applications Standalone

HTML5 application content can be consumed using a URL.



<a name="loioa3eceb585c9041218f4abc24eacbff95__prereq_rhd_12p_5lb"/>

## Prerequisites

-   In addition to the other backend routes, you have set up the `xs-app.json` file \(see sample code in [Set Up Your Development Environment](set-up-your-development-environment-3db887a.md)\).




## Context

Routes are processed from top to bottom based on a matching between the url path \(after the application key\) and the route source property. HTML5 application content can be consumed using a URL in the following format:

`https://<SubscriberSubdomain>.<Host>.<Domain>/<sapCloudService>.<appName>-<appVersion>/<resourcePath >` 

> ### Note:  
> `sapCloudService` – the `sap.cloud.service` provided in the html5 application `manifest.json` file **without the dots**
> 
> `appName` - the `manifest.json app.id` **without the dots and dashes**
> 
> `appVersion` - the `manifest.json applicationVersion.version`. The appVersion is optional. If not provided, the latest version is used.

For example:


<table>
<tr>
<th valign="top">

Product

</th>
<th valign="top">

Example URL

</th>
</tr>
<tr>
<td valign="top">

SAP Build Work Zone, advanced edition

</td>
<td valign="top">

`https://demo.workzone.cfapps.eu10.hana.ondemand.com/myservice.helloworld-1.0.0/index.html` 

</td>
</tr>
<tr>
<td valign="top">

SAP SuccessFactors Work Zone

</td>
<td valign="top">

`https://demo.workzonehr.cfapps.eu10.hana.ondemand.com/myservice.helloworld-1.0.0/index.html` 

</td>
</tr>
</table>

> ### Note:  
> It is also possible to run the application from the SAP BTP cockpit - in your subaccount, open the *HTML5 Applications* screen, and in the table, locate the link to your application.

**Related Information**  


[Configuring Custom Domains](https://help.sap.com/viewer/74af813c7ee2457cb5eddca0cc70a0c1/Cloud/en-US/1c6c729595f144d9a0bec1b4e2ef1299.html)

