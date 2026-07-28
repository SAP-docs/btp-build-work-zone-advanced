<!-- loioa0c76f487e444f588943073146d91aa2 -->

# Configure Application Routing \(xs-app.json\)

The rules that determine which request should be forwarded to which destination are called routes. To define the routing, configure the `xs-app.json` file.

When a business application consists of several different apps \(microservices\), the managed application router provides a single entry point to that business application and is responsible for the following tasks:

-   Dispatch requests to back-end microservices \(reverse proxy\)

-   Authenticate users

-   Serve static content

-   In multitenancy scenarios, derive the tenant information from the URL and forward the information to the XS UAA service so that the authentication request is redirected to the appropriate tenant-specific Identity Provider \(IdP\), for example,using SAML “Bearer Assertions”.


The different applications \(microservices\) are the destinations to which the incoming requests are forwarded. For every destination there can be more than one route.

The routing configuration file is named `xs-app.json`. Its content is formatted according to JavaScript Object Notation \(JSON\) rules.



<a name="loioa0c76f487e444f588943073146d91aa2__section_k5x_xzr_s1b"/>

## User Authentication Services



### User Account and Authentication \(UAA\)

User authentication is performed by the User Account and Authentication \(UAA\) server. In the run-time environment \(on-premise and in the Cloud Foundry environment\), a service is created for the UAA configuration.

-   A calling component accesses a target service by means of the managed application router only if there is no JSON Web Token \(JWT\) available \(for example, if a user invokes the application from a Web browser\).

-   If a JWT is already available \(for example, because the user has already been authenticated\), or if the calling component uses a JWT for its own OAuth client, the calling component calls the target service directly. In this case, the calling component does not need to use the managed application router.

> ### Note:  
> The managed application router does not “hide” the back-end microservices in any way; they remain directly accessible when bypassing the application router. So the back-end microservices must protect all their end points by validating the JWT and implementing proper authorization scope checks.

The managed application router supports the use of the `$XSAPPNAME` placeholder, which you can use in your route configuration, for example, in the `scope` property for the specified route. The value of `$XSAPPNAME` is taken from the UAA configuration \(for example, the `xsappname` property\). For more information, see [Routing Configuration Properties and Syntax](routing-configuration-properties-and-syntax-a7a2e1c.md).



<a name="loioa0c76f487e444f588943073146d91aa2__section_cmm_gb2_p1b"/>

## Sessions

The managed application router establishes a session with the client \(browser\) using a session cookie. The managed application router intercepts all session cookies sent by back-end services and stores them in its own session. To prevent collisions between the various session cookies, back-end session cookies are not sent to the client. On request, the managed application router sends the cookies back to the respective back-end services so the services can establish their own sessions.

> ### Note:  
> Non-session cookies from back-end services **are** forwarded to the client, which might cause collisions between cookies. Applications should be able to handle cookie collisions.



### Session Contents

A session established by the application router typically contains the following elements:

-   Redirect location

    The location to redirect to after logon; if the request is redirected to a UAA logon form, the original request URL is stored in the session so that, after successful authentication, the user is redirected back to it.

-   CSRF token

    The CSRF token value if it was requested by the clients.

-   OAuth token

    The JSON Web Token \(JWT\) fetched from the User Account and Authentication service \(UAA\) and forwarded to back-end services in the `Authorization` header. The client never receives this token. The managed application router refreshes the JWT automatically before it expires \(if the session is still valid\). By default, this routine is triggered 5 minutes before the expiration of the JWT, but it can also be configured with the *<JWT\_REFRESH\>* environment variable \(the value is set in minutes\). If *<JWT\_REFRESH\>* is set to 0, the refresh action is disabled.

-   OAuth scopes

    The scopes owned by the current user, which is used to check if the user has the authorizations required for each request.

-   Back-end session cookies

    All session cookies sent by back-end services.




<a name="loioa0c76f487e444f588943073146d91aa2__section_xj4_pcg_2z"/>

## CSRF Protection

The managed application router \(HTML5 Applications Runtime\) enables CSRF protection for any HTTP method that is not `GET` or `HEAD` and the route is not public. A path is considered public, if it does not require authentication. This is the case for routes with `authenticationType: none` or if authentication is disabled completely via the top level property `authenticationMethod: none`.

To obtain a CSRF token, one must send a `GET` or `HEAD` request with a `x-csrf-token: fetch` header to the managed application router. The application router returns the created token in a `x-csrf-token: <token>` header, where `<token>` is the value of the CSRF token.

If a CSRF protected route is requested with any of the above mentioned methods, `x-csrf-token: <token>` header should be present in the request with the previously obtained token. This request must use the same session as the fetch token request. If the `x-csrf-token` header is not present or is invalid, the application router returns status code “403 - Forbidden”.

**Related Information**  


[Routing Configuration Properties and Syntax](routing-configuration-properties-and-syntax-a7a2e1c.md "The properties defining the routing configuration of the xs-app.json file.")

