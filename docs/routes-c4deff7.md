<!-- loioc4deff7776b14c4695af3d7ccde57347 -->

# routes

Defines all route objects, for example: `source`, `target`, and, `destination`.



Route order is important: The first matching route is used. Therefore, it is recommended to sort the routes by the most specific source to the more generic one. For example:

> ### Sample Code:  
> ```
> "routes": [
>   {
>     "source": "^/sap/backend/employees(.*)$",
>     "target": "$1",
>     "destination": "sfsf"
>   } ,
>  { 
>     "source": "^/sap/backend/(.*)$",
>     "target": "$1",
>     "destination": "erp",
>   } 
> ]
> ```

> ### Code Syntax:  
> ```
> "routes": [ 
>   { 
>     "source": "^/sap/ui5/1(.*)$", 
>     "target": "$1", 
>     "destination": "ui5", 
>     "scope": "$XSAPPNAME.viewer",
>     "authenticationType": "xsuaa",
>     "csrfProtection": true
>   } 
> ]
> ```



## Routes Properties


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

`source` 

</td>
<td valign="top">

RegEx

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Describes a regular expression that matches the incoming request URL.

A request matches a particular route when its path contains the given pattern. To ensure the RegExp matches the complete path, use the following form:^$\`.

> ### Note:  
> RegExp is applied to the full URL, including query parameters.



</td>
</tr>
<tr>
<td valign="top">

`httpMethods` 

</td>
<td valign="top">

Array of uppercase HTTP methods

</td>
<td valign="top">

No

</td>
<td valign="top">

HTTP methods that are served by this route; the supported methods are: `DELETE`, `GET`, `HEAD`, `OPTIONS`, `POST`, `PUT`, `TRACE`, and `PATCH`.

> ### Tip:  
> If this option isn’t specified, the route serves any HTTP method.



</td>
</tr>
<tr>
<td valign="top">

`target` 

</td>
<td valign="top">

String

</td>
<td valign="top">

No

</td>
<td valign="top">

Defines how the incoming request path is rewritten for the corresponding destination or static resource.

</td>
</tr>
<tr>
<td valign="top">

`destination` 

</td>
<td valign="top">

String

</td>
<td valign="top">

No

</td>
<td valign="top">

The name of the destination to which the incoming request is forwarded. The destination name can be a static string or a regular expression that defines how to dynamically fetch the destination name from the source property or from the host.

> ### Note:  
> Destination name must be written in lowercase letters, and can't contain the character underscore \(\_\).

For more information about additional destination properties, see [Configure Destinations \(HTML5\)](configure-destinations-html5-fab4035.md).

</td>
</tr>
<tr>
<td valign="top">

`service`

</td>
<td valign="top">

String

</td>
<td valign="top">

No

</td>
<td valign="top">

The name of the service to which the incoming request is forwarded.

</td>
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

The name of the endpoint within the service to which the incoming request is forwarded. It must only be used in a route containing a service attribute.

</td>
</tr>
<tr>
<td valign="top">

`preferLocal`

</td>
<td valign="top">

Boolean

</td>
<td valign="top">

No

</td>
<td valign="top">

Defines from which subaccount the destination is retrieved. If`preferLocal` is true, the destination is retrieved from the provider subaccount. If `preferLocal` is false or undefined, the destination is retrieved from the subscriber subaccount.

</td>
</tr>
<tr>
<td valign="top">

`authenticationType`

</td>
<td valign="top">

String

</td>
<td valign="top">

No

</td>
<td valign="top">

The value can be `xsuaa`, `basic`, or `none`. The default value is “xsuaa”. When `xsuaa` is used, the specified UAA server handles the authentication \(the user is redirected to the UAA's logon form\). If `none` is used, then no authentication is needed for this route.

</td>
</tr>
<tr>
<td valign="top">

`csrfProtection` 

</td>
<td valign="top">

Boolean

</td>
<td valign="top">

No

</td>
<td valign="top">

Toggle whether this route needs CSRF token protection. The default value is “true”. The managed application router enforces CSRF protection for any HTTP request that changes state on the server side, for example: PUT, POST, or DELETE.

</td>
</tr>
<tr>
<td valign="top">

`scope`

</td>
<td valign="top">

Array/String/Object

</td>
<td valign="top">

No

</td>
<td valign="top">

The authorization scope required to access the target path. The scope itself is defined in the application's security descriptor \(`xs-security.json`\), for example, <code>“$XSAPPNAME.Display”</code> or <code>“$XSAPPNAME.Create”</code>.

</td>
</tr>
<tr>
<td valign="top">

`cacheControl`

</td>
<td valign="top">

String

</td>
<td valign="top">

No

</td>
<td valign="top">

A string representing the value of the Cache-Control header, which is set on the response when serving static resources. By default the Cache-Control header isn’t set.

The cacheControl property is only effective when the service pointing to HTML5 Application Repository \("service": "html5-apps-repo-rt"\) is set.

</td>
</tr>
<tr>
<td valign="top">

`identityProvider`

</td>
<td valign="top">

String

</td>
<td valign="top">

No

</td>
<td valign="top">

The name of the identity provider you use if it’s provided in the route’s definition. If it isn’t provided, the route is authenticated with the default identity provider.

If you are configuring multiple routes for the same application, use the`origin key` value from the configured identity provider as the route `identityProvider` property value.

> ### Note:  
> If `authenticationType` is set to *Basic Authentication* or *None*, don't define the `identityProvider` property.



</td>
</tr>
</table>

> ### Note:  
> The properties `service` and `destination` are optional. However, at least one of them **must** be defined.



### `httpMethods`

The `httpMethods` option allows you to split the same path across different targets depending on the HTTP method. For example:

> ### Sample Code:  
> ```
> "routes": [ 
>   { 
> 	"source": "^/app1/(.*)$",
> 	"target": "/before/$1/after",
> 	"httpMethods": ["GET", "POST"]
>   } 
> ]
> ```

This route only serves GET and POST requests. Any other method \(including extension ones\) gets a ***405 Method Not Allowed*** response. The same endpoint can be split across multiple destinations depending on the HTTP method of the requests:

> ### Sample Code:  
> ```
> "routes": [ 
> {
>   "source": "^/app1/(.*)$",
>   "destination" : "dest-1",
>   "httpMethods": ["GET"]
> },
> {
>   "source": "^/app1/(.*)$",
>   "destination" : "dest-2",
>   "httpMethods": ["DELETE", "POST", "PUT"]
> } 
> ]
> ```

This sample code routes GET requests to the target `dest-1`, DELETE, POST and PUT to `dest-2`, and any other method receives a ***405 Method Not Allowed*** response. It’s also possible to specify `catchAll` routes, namely routes that don’t specify `httpMethods` restrictions:

> ### Sample Code:  
> ```
> "routes": [ 
> {
>   "source": "^/app1/(.*)$",
>   "destination" : "dest-1",
>   "httpMethods": ["GET"]
> },
> {
>   "source": "^/app1/(.*)$",
>   "destination" : "dest-2"
> }} 
> ]
> ```

In this sample code, GET requests are routed to `dest-1`, and all of the rest are routed to `dest-2`.



<a name="loioc4deff7776b14c4695af3d7ccde57347__section_routes_code_examples"/>

## Route Configuration Examples



### Route with a `destination` and no `target`

> ### Sample Code:  
> ```
> {
>     "source": "^/app1/(.*)$",
>     "destination": "app-1"
> }
> ```

Because there is no target property for that route, no path rewriting takes place. If `/app1/a/b` is received as a path, then a request to `http://localhost:3001/app1/a/b` is sent. The source path is appended to the destination URL.



### Route with case-insensitive matching

> ### Sample Code:  
> ```
> {
>     "source": {
>       "path": "^/app1/(.*)$",
>       "matchCase": false
>     },
>     "destination": "app-1"
> }
> ```

> ### Note:  
> The property `matchCase` must be boolean. It is optional and has a default value of `true`.



### Route with a `destination` and a `target`

> ### Sample Code:  
> ```
> {
>     "source": "^/app1/(.*)$",
>     "target": "/before/$1/after",
>     "destination": "app-1"
> }
> ```

When a request with path `/app1/a/b` is received, the path rewriting is done according to the rules in the target property. The request is forwarded to `http://localhost:3001/before/a/b/after`.



### Route with a `service`, a `target`, and an `endpoint`

> ### Sample Code:  
> ```
> {
>      "source": "^/odata/v2/(.*)$",
>      "target": "$1",
>      "service": "com.sap.appbasic.country",
>      "endpoint": "countryservice"
> }
> ```

> ### Note:  
> In regular expressions, there is the term capturing group. If a part of a regular expression is surrounded with parenthesis, then what has been matched can be accessed using $ + the number of the group \(starting from 1\). In code sample, $1 is mapped to the \(.\*\) part of the regular expression in the source property.



### Route with dynamic `destination` and `target`

> ### Sample Code:  
> ```
> {
>       "source": "^/destination/([^/]+)/(.*)$",
>       "target": "$2",
>       "destination": "$1",
>       "authenticationType": "xsuaa"
>     }
> ```

If you have another destination configured, use this:

> ### Sample Code:  
> ```
> [
> 	{
> 	"name" : "myDestination",
> 	"url" : "http://localhost:3002"
> 	}
> ]
> ```

When a request with the path `/destination/myDestination/myTarget` is received, the destination is replaced with the URL from `"myDestination"`, the target gets `"myTarget"`, and the request is redirected to `http://localhost:3002/myTarget`.

> ### Note:  
> You can use a dynamic value \(regex\) or a static string for `destination` and `target` values.
> 
> The managed application router first looks for the destination name in the `manifest.yaml` file, and if it is not found, it looks for it in the destination service.



### Destination in Host

For legacy applications that do not support relative URL paths, you must define your URL so that the destination can be extracted from the host. Define the URL in the following way:

`https://<tenant>-<destination>.<customdomain>/<pathofile>`

To enable the managed application router to determine the destination of the URL host, a `DESTINATION_HOST_PATTERN` attribute must be provided as an environment variable. For example, when a request with the path `https://myDestination.some-approuter.someDomain.com/app1/myTarget` is received, the following route is used:

> ### Sample Code:  
> ```
> {
>       "source": "^/app1/([^/]+)/",
>       "target": "$1",
>       "destination": "*",
>       "authenticationType": "xsuaa"
>  }
> 
> ```

In this example, the target is extracted from the source and the `‘$1’` value is replaced with `"myTarget"`. The destination value is extracted from the host and the `"*"` value is replaced with `"myDestination"`.



### Route with service `"html5-apps-repo-rt"` and `cacheControl`

> ### Sample Code:  
> ```
> {
>   "source": "^/index.html$",
>   "service": "html5-apps-repo-rt",
>   "authenticationType": "xsuaa",
>   "cacheControl":"public,max-age=1000,must-revalidate"
> }
> ```



### Route with `httpMethods` restrictions

This option allows you to split the same path across different targets depending on the HTTP method. For example:

> ### Sample Code:  
> ```
> {
>   "source": "^/app1/(.*)$",
>   "target": "/before/$1/after",
>   "httpMethods": ["GET", "POST"]
> }
> ```

This route only supports `GET` and `POST` requests. Any other method \(including extensions\) receives a “405 Method Not Allowed” response. The same endpoint can be split across multiple destinations depending on the HTTP method of the requests:

> ### Sample Code:  
> ```
> {
>   "source": "^/app1/(.*)$",
>   "destination" : "dest-1",
>   "httpMethods": ["GET"]
> },
> {
>   "source": "^/app1/(.*)$",
>   "destination" : "dest-2",
>   "httpMethods": ["DELETE", "POST", "PUT"]
> }
> ```

In this setup, `GET` requests are routed to `"dest-1"`, and all the rest to `"dest-2"`.



### Route with a `scope`

An application-specific scope uses the following format:

`<application-name>.<scope-name>` 

It is possible to configure what scope the user needs to possess in order to access a specific resource. Those configurations are per route. The user should have at least one of the scopes in order to access the corresponding resource.

> ### Sample Code:  
> ```
> {
>     "source": "^/web-pages/(.*)$",
>     "target": "$1",
>     "scope": ["$XSAPPNAME.viewer", "$XSAPPNAME.reader", "$XSAPPNAME.writer"]
> }
> ```

For convenience if your route only requires one scope, the scope property can be a string instead of an array. The following configuration is also valid:

> ### Sample Code:  
> ```
> {
>     "source": "^/web-pages/(.*)$",
>     "target": "$1",
>     "scope": "$XSAPPNAME.viewer"
> }
> ```

You can configure scopes for different HTTP methods, such as `GET`, `POST`, `PUT`, `HEAD`, `DELETE`, `CONNECT`, `TRACE`, `PATCH`, and`OPTIONS`. If some of the HTTP methods are not explicitly set, the behaviour for them is defined by the default property. If there is no default property specified and the HTTP method is also not specified, the request is rejected by default.

> ### Sample Code:  
> ```
> {
>     "source": "^/web-pages/(.*)$",
>     "target": "$1",
>     "scope": {
>       "GET": "$XSAPPNAME.viewer",
>       "POST": ["$XSAPPNAME.reader", "$XSAPPNAME.writer"],
>       "default": "$XSAPPNAME.guest"
>     }
> }
> ```

The application router supports the `$XSAPPNAME` placeholder. Its value is taken \(and then substituted in the routes\) from the UAA configuration.

> ### Note:  
> The substitution is case-sensitive.

You can use the name of the business application directly instead of using the $XSAPPNAME placeholder:

> ### Sample Code:  
> ```
> {
>     "source": "^/backend/(.*)$",
>     "scope": "my-business-application.viewer"
> }
> ```



### Routes with an `identityProvider`

You can define several identity providers for different types of users. In this code example, there are two categories: hospital patients and hospital personnel:

-   patientsIDP – use for authenticating patients.

-   hospitalIDP – use for authenticating all hospital personnel \(doctors, nurses etc..\).


> ### Sample Code:  
> ```
> [
>     { 
> 	"source": "^/patients/sap/opu/odata/(.*)",
> 	"target": "/sap/opu/odata$1",
> 	"destination": "backend",
> 	"authenticationType": "xsuaa",
> 	"identityProvider": "patientsIDP"
>     },
>     {
>         "source": "^/hospital/sap/opu/odata/(.*)",
> 	"target": "/sap/opu/odata$1",
> 	"destination": "backend", "authenticationType": "xsuaa",
> 	"identityProvider": "hospitalIDP"
>     }
> ]
> ```

A patient who tries to log into the system is authenticated by patientIDP, and a doctor who tries to log in is authenticated by hospitalIDP.

> ### Note:  
> If a user logs in as one identity and then wants to perform tasks for another identity type, the user must log out and log back in to the system.
> 
> Dynamic provisioning of the subscriber account identity provider is not supported.
> 
> Identity provider configuration is only supported in the client-side logon redirect flow.

