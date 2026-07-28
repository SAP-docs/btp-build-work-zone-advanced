<!-- loioccf00a67c70c4124b92abb73f64f3afa -->

# websockets

If enabled in the configuration,the managedapplication router managed can forward web-socket communication.



If the back-end service needs authentication, the upgrade request should contain a valid session cookie. The managed application router supports the destination schemata "`ws`", "`wss`", "`http`", and "`https`".

> ### Sample Code:  
> ```
> {
>   "websockets": {
>     "enabled": true
>   }
> }
> ```

The `websockets` property should be added to the `xs-app.json` of the deployed HTML5 application. When an incoming request for an application in the repository goes through the application router, it retrieves the application's configuration from the repository. If this flag is set, the application router creates a web-socket connection to the back end \(the target url of the request\) and acts as a proxy which delivers messages on top of the `ws` protocol from the back end to the user, and vice versa.

> ### Restriction:  
> A web-socket ping is not forwarded to the back-end service.

