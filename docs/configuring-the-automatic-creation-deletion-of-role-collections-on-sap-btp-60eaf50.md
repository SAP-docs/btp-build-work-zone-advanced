<!-- loio60eaf507ecfe484a9d05e273687d8491 -->

# Configuring the Automatic Creation/Deletion of Role Collections on SAP BTP

To enable the creation or deletion of role collections on SAP BTP automatically, it is necessary to configure a destination to the Identity Authentication service.



> ### Note:  
> This procedure is relevant to content providers that are using SAP BTP role mechanism. It is not relevant to content providers that are using the Identity Provisioning service to provision authorizations.

When configuring a remote content provider, if the *Automatically add all content items to subaccount* option is enabled, all the roles are added to the subaccount, and the relevant role collections are also created in the SAP BTP cockpit with the following name format: `~<content provider>_<role>`.

If the content provider is set up to send automatic updates \(using a callback URL\), any change on the provider side will lead to automatic creation or deletion of role collection in SAP BTP cockpit. To ensure the creation of role collections, you need to obtain the Identity Authentication API credentials using SAP BTP CLI.



### Step 1: Obtain API Credentials

To ensure role collections creation and deletion during content provider automatic syncs, you need to get access to the APIs of the Identity Authentication service. Use the SAP BTP command-line interface \(btp CLI\) to create API credentials. For example:

```
$ btp create security/api-credential --name my-credential --subaccount <subaccount id>
```

The response will show the credentials in the following format:

```
Name: my-credential
Client ID: <client id>
Credential Type: secret
Client Secret: <secret>
Read-only: false
Token URL: https://<host>.authentication.<data center>.hana.ondemand.com/oauth/token
API URL: https://api.authentication.<data center>.hana.ondemand.com
```



### Step 2: Create Destination to Identity Authentication

1.  Navigate to *Connectivity* \> *Destinations* and choose *Create Destination*.
2.  Enter the following destination properties:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Name*
    
    </td>
    <td valign="top">
    
    `xsuaa-apiaccess`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Type*
    
    </td>
    <td valign="top">
    
    HTTP
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL*
    
    </td>
    <td valign="top">
    
    `<API URL>`

    Copy this value from the value of `API URL` in the output of the CLI command.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Proxy Type*
    
    </td>
    <td valign="top">
    
    Internet
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Authentication*
    
    </td>
    <td valign="top">
    
    OAuth2ClientCredentials
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Client ID*
    
    </td>
    <td valign="top">
    
    `<Client ID>`

    Copy this value from the value of `Client ID` in the output of the CLI command.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Client Secret*
    
    </td>
    <td valign="top">
    
    `<Client Secret>`

    Copy this value from the value of `Client Secret` in the output of the CLI command.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service URL Type*
    
    </td>
    <td valign="top">
    
    Dedicated
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service URL*
    
    </td>
    <td valign="top">
    
    `<Token URL>`

    Copy this value from the value of `Token URL` in the output of the CLI command.
    
    </td>
    </tr>
    </table>
    
3.  Make sure that the option *Use default JDK truststore* is selected.

**Related Information**  


[Set Up Automatic Updates for Content Providers](set-up-automatic-updates-for-content-providers-b5f4f4e.md "Administrators can set up automatic updates of content consumed from a remote content provider. This replaces the need to manually fetch updated content in the Channel Manager every time the content changes.")

