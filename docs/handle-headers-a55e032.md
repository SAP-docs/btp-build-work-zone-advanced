<!-- loioa55e032df09344ae9493205ec0872a62 -->

# Handle Headers

Learn how to handle different headers - forwarding, hop-by-hop, and custom headers.



<a name="loioa55e032df09344ae9493205ec0872a62__section_ayn_r3q_thb"/>

## Forwarding Header

The managed application router sends the following `x-forwarding-` headers to the route targets:


<table>
<tr>
<th valign="top">

Header Name

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`x-forwarded-host`

</td>
<td valign="top">

Contains the host header that is sent from the client to the managed application router.

</td>
</tr>
<tr>
<td valign="top">

`x-forwarded-proto`

</td>
<td valign="top">

Contains the protocol that is used by the client to connect to the managed application router.

</td>
</tr>
<tr>
<td valign="top">

`x-forwarded-for`

</td>
<td valign="top">

Contains the address of the client that connects to the managed application router.

</td>
</tr>
<tr>
<td valign="top">

`x-forwarded-path`

</td>
<td valign="top">

Contains the original path that the client requested.

</td>
</tr>
</table>

If a client performs a path rewriting, it sends the `x-forwarded-proto`, `x-forwarded-host`, and the `x-forwarded-path` headers to the managed application router. The values of these headers are forwarded to the route targets without modifications instead of being generated from the application router request URL. The `x-forwarded-path` header of a request does not impact the source pattern of routes in the `xs-app.json`.



<a name="loioa55e032df09344ae9493205ec0872a62__section_r1v_s3q_thb"/>

## Hop-by-Hop Headers

The hop-by-hop headers are only for a single transport-level connection and are not forwarded by the managed application router:

-   `Connection`
-   `Keep-Alive`
-   `Public`
-   `Proxy-Authenticate`
-   `Transfer-Encoding`
-   `Upgrade`



<a name="loioa55e032df09344ae9493205ec0872a62__section_fr4_53q_thb"/>

## Custom Header

`x-custom-host` is used to support the managed application router behind an external reverse proxy. The x-custom-host header must contain the internal reverse proxy host.

In a multi-tenancy landscape, the managed application router can be called from multiple tenants. During the authentication flow, the application router uses the tenant ID to fetch the authentication token from XSUAA. The application router extracts the tenant ID from the corresponding host using the tenant host pattern configuration.

In an external reverse proxy flow, the managed application router uses the `x-custom-host` to extract the tenant ID using the tenant host pattern configuration.

If the `x-custom-host` is not provided, the managed application router uses the host header to extract the tenant ID.

