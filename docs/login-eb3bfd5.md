<!-- loioeb3bfd57be014ab4830c3122a291ea38 -->

# login

A redirect to the managed application router at a specific endpoint takes place during OAuth2 authentication with the User Account and Authentication service \(UAA\).



This endpoint can be configured in order to avoid possible collisions, as illustrated in the following example:

> ### Sample Code:  
> “login” Property
> 
> ```
> "login": { 
>   "callbackEndpoint": "/custom/login/callback" 
> } 
> ```

> ### Tip:  
> The default endpoint is “`/login/callback`”.

