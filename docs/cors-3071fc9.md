<!-- loio3071fc912ba441fb86b3dd96e24d7f7d -->

# cors

With the cors property, you can support cross-origin requests, for example, by allowing the modification of the request header. Cross-origin resource sharing \(CORS\) permits Web pages from other domains to make HTTP requests to your application domain, where normally such requests would automatically be refused by the Web browser's security policy.

Cross-origin resource sharing is a mechanism that allows restricted resources on a Web page to be requested from another domain \(protocol and port\) outside the domain \(protocol and port\) from which the first resource was served. The CORS configuration enables you to define details to control access to your application resource from other Web browsers. For example, you can specify where requests can originate from or what is allowed in the request and response headers. The following example illustrates a basic CORS configuration:

```
[
  {
      "uriPattern": "^\route1$",
      "allowedMethods": [
        "GET"
      ],
      "allowedOrigin": [
        {
          "host": "host.acme.com",
          "protocol": "https",
          "port": 345
        }
      ],
      "maxAge": 3600,
      "allowedHeaders": [
        "Authorization",
        "Content-Type"
      ],
      "exposeHeaders": [
        "customHeader1",
        "customHeader2"
      ],
      "allowedCredentials": true
    }
]
```

The CORS configuration includes an array of objects with the following properties, some of which are mandatory:

**Available Settings for CORS Options**


<table>
<tr>
<th valign="top">

CORS Property

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

`uriPattern`

</td>
<td valign="top">

String

</td>
<td valign="top">

Yes

</td>
<td valign="top">

A regular expression \(RegExp\) representing the source routes to which the CORS configuration applies. To ensure that the RegExp matches the complete path, surround it with ^ and $,f or example, `"uriPattern": "^\route1$"`. Defaults: none

</td>
</tr>
<tr>
<td valign="top">

`allowedOrigin`

</td>
<td valign="top">

Array

</td>
<td valign="top">

Yes

</td>
<td valign="top">

A comma-separated list of objects each of which contains a host name, port and protocol that are allowed by the server, for example: `[{“host”: "www.acme.com"}]` or `[{“host”: “.acme.com”}]`.

> ### Note:  
> Matching is case-sensitive. In addition, if no port or protocol is specified, the default is `“*”`.

The default configuration is: `[{“host”: "*"}]`, which means that the server allows **any** origin to access the resource.

</td>
</tr>
<tr>
<td valign="top">

`allowedMethods`

</td>
<td valign="top">

Array

</td>
<td valign="top">

No

</td>
<td valign="top">

A comma-separated list of HTTP methods that are allowed by the server, for example, <code>“GET”, “POST”</code>. If `allowMethods` is defined but no method is specified, the default <code>“GET”, “POST”, “HEAD”, “OPTIONS”</code> \(all\) applies.

> ### Tip:  
> The specified methods must be upper-case, for example,`GET`. Matching of the method type is case-sensitive.



</td>
</tr>
<tr>
<td valign="top">

`allowedHeaders`

</td>
<td valign="top">

Array

</td>
<td valign="top">

No

</td>
<td valign="top">

A comma-separated list of request headers that are allowed by the server. the default values are as follows: `[“Origin”, “Accept”, “X-Requested-With”, “Content-Type”, “Access-Control-Request-Method”, “Access-Control-Request-Headers”]`.

</td>
</tr>
<tr>
<td valign="top">

`maxAge`

</td>
<td valign="top">

String

</td>
<td valign="top">

No

</td>
<td valign="top">

A single value specifying the length of time \(in seconds\) a preflight request should be cached for. A negative value that prevents CORS filter from adding this response header to the pre-flight response. If `maxAge` is defined but no value is specified, the default time of “1800” seconds applies.

</td>
</tr>
<tr>
<td valign="top">

`exposeHeaders`

</td>
<td valign="top">

Array

</td>
<td valign="top">

No

</td>
<td valign="top">

A comma-separated list of **response** headers that are allowed to be exposed. If `exposeHeaders` is defined but no response header is specified for exposure, no default value is supplied.

</td>
</tr>
<tr>
<td valign="top">

`allowedCredentials` 

</td>
<td valign="top">

Boolean

</td>
<td valign="top">

No

</td>
<td valign="top">

A Boolean flag that indicates whether the specified resource supports user credentials. The default setting is “true”.

</td>
</tr>
</table>

