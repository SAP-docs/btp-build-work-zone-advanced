<!-- loiobf7d98cf76df48009d8bc88599b6cd55 -->

# Prepare Business Services

A business service for SAP BTP needs to expose a set of attributes that enable the managed application router to serve business service UI and/or data.

The following attributes should be defined in the `onBind` hook in the service broker implementation.


<table>
<tr>
<th valign="top">

Information

</th>
<th valign="top">

Necessity

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

sap.cloud.service

</td>
<td valign="top">

Mandatory

</td>
<td valign="top">

Service name referenced from xs-app.json route and business service prefix if business service provides a UI

</td>
</tr>
<tr>
<td valign="top">

sap.cloud.service.alias

</td>
<td valign="top">

Optional

</td>
<td valign="top">

Short service name alias for user friendly URL business service prefix.

> ### Note:  
> Make sure the alias is unique in the context of the subaccount.



</td>
</tr>
<tr>
<td valign="top">

endpoints

</td>
<td valign="top">

Mandatory

</td>
<td valign="top">

One or more endpoints that can be used to access business service data.

</td>
</tr>
<tr>
<td valign="top">

html5-apps-repo

</td>
<td valign="top">

Optional

</td>
<td valign="top">

The `html5-apps-repo.app_host_id` contains one or more html5-apps-repo service instance GUIDs \(separated by comma\) that can be used to retrieve business service UIs.

</td>
</tr>
<tr>
<td valign="top">

saasregistryenabled

</td>
<td valign="top">

Optional

</td>
<td valign="top">

Indicates that this business service supports SaaS Registry subscription. If provided, the business service xsappname is returned in the SaaS Registry `getDependencies` callback.

</td>
</tr>
<tr>
<td valign="top">

grant\_type

</td>
<td valign="top">

Optional

</td>
<td valign="top">

The grant type that should be used to trigger requests to the business service.

Allowed values:

-   `user_token` \(default\):The application router performs a token exchange between the login JWT token and the business service token, and uses it to trigger a request to the business service endpoint.

-   `client_credentials`: The application router generates a `client_credentials` token and uses it to trigger a request to the business service endpoint.




</td>
</tr>
</table>

The value of the endpoints is an object containing the following properties:


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Type

</th>
<th valign="top">

Necessity

</th>
<th valign="top">

Default

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

url

</td>
<td valign="top">

String

</td>
<td valign="top">

Mandatory

</td>
<td valign="top">

\-

</td>
<td valign="top">

URL to access business service data

</td>
</tr>
<tr>
<td valign="top">

timeout

</td>
<td valign="top">

Number

</td>
<td valign="top">

Optional

</td>
<td valign="top">

30000ms

</td>
<td valign="top">

Positive integer value representing the maximum wait time for a response \(in milliseconds\) of the business service.

</td>
</tr>
</table>

Business service UIs must be stored in the HTML5 Application Repository and defined in their `manifest.json` files. The dataSource URIs must be relative to the base URL, which means there is no need for a slash as the first character.



<a name="loiobf7d98cf76df48009d8bc88599b6cd55__section_gdm_vnz_kmb"/>

## App descriptor file a business service \(manifest.json file\)

To learn more, refer to the following information about the app descriptor file: [Descriptor for Applications, Components, and Libraries \(manifest.json\)](https://ui5.sap.com/#/topic/be0cf40f61184b358b5faedaec98b2da)

