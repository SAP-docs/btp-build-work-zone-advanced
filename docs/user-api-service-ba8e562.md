<!-- loioba8e562216de4faab94ba7982b225327 -->

# User API Service

The application router exposes a user API that returns the details of the users who are logged in to the application.

The user API supports two endpoints:

-   `/currentUser` : returns all details of logged in users

-   `/attributes`: returns the main user properties

    > ### Note:  
    > Returning `content-type` in a response has now been updated according to common API standards. The `user-api` is now returning `“content-type = application/json”`, which may require an adjustment to HTML5 applications coding such as removing the `JSON.parse` code, as this will be done automatically.


The`/currentUser` endpoint response has the following format:

> ### Sample Code:  
> ```
> ```
> {
>    "firstname": "John",
>    "lastname": "Doe",
>    "email": "john.doe@sap.com",
>    "name": "john.doe@sap.com",
>    "displayName": "John Doe (john.doe@sap.com)"
> }
> ```
> 
> ```

The `/attributes` endpoint response has the following format:

> ### Sample Code:  
> ```
> ```
> {
>    "firstname": "John",
>    "lastname": "Doe",
>    "email": "john.doe@sap.com",
>    "name": "john.doe@sap.com"
> }
> ```
> 
> ```

> ### Note:  
> The `"name"` property is the user ID in the identity provider, which in many cases is also the email address.



<a name="loioba8e562216de4faab94ba7982b225327__section_awl_xch_p4b"/>

## Configuring the User API Service in the Routing Configuration File

The user API can be implemented by modelling an [xs-app.json route](routes-c4deff7.md) using the `sap-approuter-userapi` service .

The following example handles both endpoints:

> ### Sample Code:  
> ```
> {
>     "source": "^/user-api(.*)",
>     "target": "$1",
>     "service": "sap-approuter-userapi"
> }
> 
> ```

The following example uses only the `/currentUser` endpoint:

> ### Sample Code:  
> ```
> {
>     "source": "^/user-api/currentUser$",
>     "target": "/currentUser",
>     "service": "sap-approuter-userapi"
> }
> ```

**Related Information**  


[routes](routes-c4deff7.md "Defines all route objects, for example: source, target, and, destination.")

