<!-- loioff3678d9c3a94fc4831e982ac8b560dc -->

# services

Specify options for a service in your application.



The services section in `xs-app.json` extends the services configuration in the deployment manifest \(`manifest.yml`\), for example, with some static properties such as an end point.

> ### Sample Code:  
> ```
> {
>   "services": {
>     "com.sap.appbasic.country": {
>       "endpoint": "countryservice",
>       "logoutPath": "/countrieslogout",
>       "logoutMethod": "GET"
>     }
>   }
> }
> ```

The following syntax rules apply:

**Services Properties**


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Type

</th>
<th valign="top">

Mandatory

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`endpoint`

</td>
<td valign="top">

String

</td>
<td valign="top">

No

</td>
<td valign="top">

The name of the attribute in the VCAP\_SERVICES that contains the URL of the service.

</td>
</tr>
<tr>
<td valign="top">

`logoutPath` 

</td>
<td valign="top">

String

</td>
<td valign="top">

No

</td>
<td valign="top">

The log out end point for your destination. The `logoutPath` will be called when central log out is triggered or a session is deleted due to a time out. The request to `logoutPath` contains additional headers, including the JWT token.

</td>
</tr>
<tr>
<td valign="top">

`logoutMethod` 

</td>
<td valign="top">

String

</td>
<td valign="top">

No

</td>
<td valign="top">

The `logoutMethod` property specifies the HTTP method with which the `logoutPath` will be requested, for example, POST, PUT, GET; the default value is POST

</td>
</tr>
</table>

**Related Information**  


[Integrate Business Services](integrate-business-services-1b80373.md "")

