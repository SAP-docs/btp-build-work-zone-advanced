<!-- loiofab4035652cb4fc48503c65dc841d335 -->

# Configure Destinations \(HTML5\)

A destination defines the back-end connectivity. In its simplest form, a destination is a URL to which requests are forwarded. There must be a destination for every single app \(microservice\) that is a part of the business application.

Destination configuration is provided by the `destination service`.



<a name="loiofab4035652cb4fc48503c65dc841d335__section_jnr_jtt_5lb"/>

## Mandatory Properties of a Destination

When you configure the mandatory properties of a destination, note the following guidelines:

**Mandatory Properties of a Destination**


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Type

</td>
<td valign="top">

Only HTTP is supported.

</td>
</tr>
<tr>
<td valign="top">

Authentication

</td>
<td valign="top">

All authentication types are supported.

-   When using `basic authentication`, `User` and `Password` are mandatory.
-   When using `principal propagation`, the proxy type is `on-premise`.
-   When using `OAuth2SAMLBearerAssertion`, the `uaa.user` scope in the `xs-security.json` file is required.



</td>
</tr>
<tr>
<td valign="top">

ProxyType

</td>
<td valign="top">

Supported types:

-   `on-premise` \(if set, binding to SAP BTP connectivity service is required\)

-   `internet`

    > ### Note:  
    > The `private-link` proxy type is not supported.




</td>
</tr>
</table>



<a name="loiofab4035652cb4fc48503c65dc841d335__section_hxw_gtt_5lb"/>

## Additional Properties of a Destination

When you configure additional properties of a destination, note the following guidelines:

**Additional Properties of a Destination**


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

HTML5.ForwardAuthToken

</td>
<td valign="top">

The OAuth token contains the user identity, scopes, and other attributes. It’s signed by the UAA so it can be used for user authentication and authorization with back-end services.

If `true`, the OAuth token is sent to the destination. The default value is `false`.

-   If the `ProxyType` is set to `on-premise`, **don’t** set the `ForwardAuthToken` property to `true`.
-   If the `Authentication` is other than `NoAuthentication`, **don’t** set the `ForwardAuthToken` property to `true`.



</td>
</tr>
<tr>
<td valign="top">

HTML5.ForwardAuthCertificates

</td>
<td valign="top">

If `true`, the certificates and key of the authentication service are added to the HTTP connection to the destination, to enable the mTLS \(mutual TLS authentication\) handshake between the application router and the backend application.

The default value is `false`.

</td>
</tr>
<tr>
<td valign="top">

HTML5.Timeout

</td>
<td valign="top">

Positive integer representing the maximum time to wait for a response \(in milliseconds\) from the destination. The default value is **30000 ms**. If you have a backend application that performs complex and time consuming processing, it is recommended to configure a destination timeout of at least **120000 ms** to avoid potential timeouts in case of network slowness.

> ### Note:  
> The timeout value specified also applies to the destination's log out path \(if defined\), which belongs to the `destination` property.



</td>
</tr>
<tr>
<td valign="top">

HTML5.PreserveHostHeader

</td>
<td valign="top">

This is expected by some back-end systems like AS ABAP, which don’t process `x-forwarded-*` headers.

If `true`, the managed application router preserves the host header in the back-end request.

</td>
</tr>
<tr>
<td valign="top">

HTML5.DynamicDestination

</td>
<td valign="top">

If `true`, the managed application router allows this destination to be used dynamically on the host or path level.

For more information, see [Passing Information to the Backend Using a Destination](passing-information-to-the-backend-using-a-destination-e6dd664.md).

> ### Note:  
> To enable CSRF protection via the approuter, set the`CEP.EnableCsrfProtection` destination property to *true* for all dynamic destinations where their respective backend doesn’t handle CSRF protection.
> 
> If your backend is already CSRF protected, you must not add this property.

> ### Caution:  
> Adding the <code><b>HTML5DynamicDestination</b></code> property and setting it to true, enables dynamic access to the destination to any logged-in user.
> 
> Therefore before adding this property to the destination, make sure that the underlying API is not public and requires the correct user credentials.



</td>
</tr>
<tr>
<td valign="top">

HTML5.SetXForwardedHeaders

</td>
<td valign="top">

If `true`, the managed application router adds X-Forwarded-\(Host, Path, Proto\) headers to the back-end request.

The default value is `true`.

</td>
</tr>
<tr>
<td valign="top">

HTML5.StrictConnectionMode

</td>
<td valign="top">

If `true`, the application router uses strict HTTP agents with conservative connection pooling settings for this destination. These settings include shorter socket timeouts and FIFO \(First-In, First-Out\) scheduling. This option is recommended for mTLS and certificate-based authentication scenarios. The default value is `false`.

</td>
</tr>
<tr>
<td valign="top">

sap-client

</td>
<td valign="top">

This is expected by ABAP back-end systems.

If `true`, the managed application router propagates the `sap-client` and its value as a header in the back-end request.

</td>
</tr>
</table>

