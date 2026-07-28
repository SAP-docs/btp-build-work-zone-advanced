<!-- loioebf739699f5f4de79ce54cabbfbf6e91 -->

# logout

You can define any options that apply if you want your application to have central log out end point.



In this object, you can define an application's central log out end point by using the `logoutEndpoint` property, as illustrated in the following example:

> ### Sample Code:  
> ```
> "logout" {
>   "logoutEndpoint": "/my/logout"
> }
> ```

Making a `GET` request to “`/my/logout`” triggers a client-initiated central log out. Central log out can be initiated by a client or triggered due to a session timeout, with the following consequences:

-   Client-initiated central log out
    -   Deletes the user session
    -   Requests the log out paths for all your back-end services \(if you provided these paths in the `destinations` and `service` properties\).
    -   Redirects to the User Account and Authentication service \(UAA\) , if such a service is provided, and logs out from there.

-   Session time out
    -   Deletes the user session
    -   Requests the log out paths for all your back-end services \(if you provided these paths in the `destinations` and `service` properties\).


You can use the `logoutPage` property to specify the Web page in one of the following ways:

-   URL path

    The User Account and Authentication service \(UAA\) redirects the user back to the managed application router, and the path is interpreted according to the configured routes.

    The `logoutEndpoint` can be called with query parameters. For example:

    > ### Sample Code:  
    > ```
    > window.location.replace('/my/logout?siteId=3');
    > ```

    These parameters will be appended as is to the redirect URL set by the `logoutPage` property. For example, if the logout section is:

    > ### Sample Code:  
    > ```
    > "logout": {
    >     "logoutEndpoint": "/logout",
    >     "logoutPage": "/logoff.html"
    >   },
    > ```

    The redirect URL will end with:

    > ### Sample Code:  
    > ```
    > /logoff.html?siteId=3
    > ```

    > ### Note:  
    > The resource that matches the URL path specified in the property `logoutPage` should not require authentication; for this route, the property `authenticationType` must be set to `none`.

    In the following example, `my-static-resources` is a folder in the working directory of the application router; the folder contains the file `logout-page.html` along with other static resources.

    > ### Sample Code:  
    > ```
    > { 
    >   "authenticationMethod": "route", 
    >   "logout": { 
    >     "logoutEndpoint": "/my/logout", 
    >     "logoutPage": "/logout-page.html"
    >   }, 
    >   "routes": [ 
    >     {
    >       "source": "^/logout-page.html$", 
    >       "service": "html5-apps-repo-rt", 
    >       "authenticationType": "none"
    >     }
    >   ]
    > } 
    > ```

-   Absolute HTTP\(S\) path

    The User Account and Authentication service \(UAA\) redirects the user to a page \(or application\) different from the managed appplication router.

    > ### Sample Code:  
    > ```
    > "logout": {
    >   "logoutEndpoint": "/my/logout",
    >   "logoutPage": "http://acme.com/employees.portal" 
    > } 
    > ```


