<!-- loioa7a2e1c93f6043f2acd7f7db1f258c87 -->

# Routing Configuration Properties and Syntax

The properties defining the routing configuration of the `xs-app.json` file.



<a name="loioa7a2e1c93f6043f2acd7f7db1f258c87__section_hxz_3k3_p1b"/>

## Routing Configuration Properties

The following table lists the properties that either must be set or can be specified as an additional option. Click on the links for information for each property:

**Routing Configuration Properties**


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

[welcomeFile](welcomefile-4a7f9ca.md)

</td>
<td valign="top">

String

</td>
<td valign="top">

The Web page served by default if the HTTP request does not include a specific path, for example, index.html.

</td>
</tr>
<tr>
<td valign="top">

[authenticationMethod](authenticationmethod-1043111.md)

</td>
<td valign="top">

String

</td>
<td valign="top">

The method used to authenticate user requests, for example: “route” or “none” \(no authentication\).

</td>
</tr>
<tr>
<td valign="top">

[routes](routes-c4deff7.md)

</td>
<td valign="top">

Array

</td>
<td valign="top">

Defines all route objects, for example: `source`, `target`, and, `destination`.

</td>
</tr>
<tr>
<td valign="top">

[login](login-eb3bfd5.md)

</td>
<td valign="top">

Object

</td>
<td valign="top">

A redirect to the managed application router at a specific endpoint takes place during OAuth2 authentication with the User Account and Authentication service \(UAA\).

</td>
</tr>
<tr>
<td valign="top">

[logout](logout-ebf7396.md)

</td>
<td valign="top">

Object

</td>
<td valign="top">

You can define any options that apply if you want your application to have central log out end point.

</td>
</tr>
<tr>
<td valign="top">

[destinations](destinations-7fb01b3.md)

</td>
<td valign="top">

Object

</td>
<td valign="top">

Specify any additional options for your destinations.

</td>
</tr>
<tr>
<td valign="top">

[services](services-ff3678d.md)

</td>
<td valign="top">

Object

</td>
<td valign="top">

Specify options for a service in your application.

</td>
</tr>
<tr>
<td valign="top">

[compression](compression-c99f8c9.md)

</td>
<td valign="top">

Object

</td>
<td valign="top">

The `compression` keyword enables you to define if the managed application router compresses text resources before sending them.

</td>
</tr>
<tr>
<td valign="top">

[websockets](websockets-ccf00a6.md)

</td>
<td valign="top">

Object

</td>
<td valign="top">

The managed application router can forward web-socket communication. Web-socket communication must be enabled in the configuration.

</td>
</tr>
<tr>
<td valign="top">

[errorPage](errorpage-750f761.md)

</td>
<td valign="top">

Array

</td>
<td valign="top">

Errors originating in the managed application router show the HTTP status code of the error. It is possible to display a custom error page using the `errorPage` property.

</td>
</tr>
<tr>
<td valign="top">

[cors](cors-3071fc9.md)

</td>
<td valign="top">

Array

</td>
<td valign="top">

Contains the configuration for cross-origin resource sharing.

</td>
</tr>
</table>



<a name="loioa7a2e1c93f6043f2acd7f7db1f258c87__section_qmz_h4c_llb"/>

## JSON-Compliant Syntax

The following example of an `xs-app.json` application descriptor shows the JSON-compliant syntax required and the mandatory and optional properties.

> ### Code Syntax:  
> ```
> {
>   "welcomeFile": "index.html",
>   "authenticationMethod": "route",
>   "sessionTimeout": 10,
>   "pluginMetadataEndpoint": "/metadata",
>   "routes": [				
>     {
>       "source": "^/sap/ui5/1(.*)$",
>       "target": "$1",
>       "destination": "ui5",
>       "csrfProtection": false
>     },
>     {
>       "source": "/employeeData/(.*)",
> 	  "target": "/services/employeeService/$1",
> 	  "destination": "employeeServices",
> 	  "authenticationType": "xsuaa",
> 	  "scope": ["$XSAPPNAME.viewer", "$XSAPPNAME.writer"],
> 	  "csrfProtection": true
>     },
>     {
>       "source": "^/(.*)$",
>       "target": "/web/$1",
>       "localDir": "static-content",
> 	  "replace": {
>         "pathSuffixes": ["/abc/index.html"],
>         "vars": ["NAME"]
>      },
>      {
>        "source": "^/user-api/currentUser$",
>        "target": "/currentUser",
>        "service": "sap-approuter-userapi"
>      }
>   ],
>   "login": {
>      "callbackEndpoint": "/custom/login/callback"
>   },
>   "logout": {
>      "logoutEndpoint": "/my/logout",
>      "logoutPage": "/logout-page.html"
>   },
>   "destinations": {
>      "employeeServices": {
>        "logoutPath": "/services/employeeService/logout",
>        "logoutMethod": "GET"
>      }
>   }, 
>   "responseHeaders" : [
>     {"name": "Content-Security-Policy", "value": "default-src 'self'"}
>   ],
>   "compression": { 
>      "minSize": 2048
>   },
>    "websockets": {
>     "enabled": true
>   },
>   "errorPage": [
>     {"status": [400,401,402], "file": "/custom-err-4xx.html"},
>     {"status": 501, "file": "/custom-err-501.html"}
>   ] 
> }
> ```

**Related Information**  


[Configure Application Routing \(xs-app.json\)](configure-application-routing-xs-app-json-a0c76f4.md "The rules that determine which request should be forwarded to which destination are called routes. To define the routing, configure the xs-app.json file.")

