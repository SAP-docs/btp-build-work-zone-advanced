<!-- loiob3c804e1f999448b8011a475fea1da6c -->

# OAuth Clients

You can authorize an external application to access the SAP Build Work Zone, advanced edition API by registering an application as an OAuth client.

An OAuth client is an application or service that requests access to protected user data or resources. OAuth clients handle delegated authorization, and they consist of a client ID, client secret, and redirect URIs: specific web addresses where the server will send the user and the authorization token after the user approves access.

-   In the Admin Console, go to *External Integrations* \> *OAuth Clients*. In the table, you can find all the OAuth clients that are already configured for the system. Currently, the following three integration features are configured automatically upon enabling them in the *Features* screen: SCIM API, Documentation Grounding, and Search Appliance. All the rest of the OAuth clients require manual configuration.

    > ### Note:  
    > -   Document Grounding, Search Appliance, and SCIM API integration features must all be assigned to a dedicated OAuth client.
    > -   You can't change the OAuth client assignments of the integration features in this screen. All changes can only be done in the *Feature Enablement* \> *Features* screen.
    > -   It is not possible to delete an OAuth client if it's assigned to an integration feature. To delete a client you must first unassign it in the *Feature Enablement* \> *Features*.

-   To add a new OAuth client, click *Add OAuth Client* and specify the following information, then save your changes.


    <table>
    <tr>
    <th valign="top">

    Setting
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Name*
    
    </td>
    <td valign="top">
    
    **\[Mandatory\]** Enter a meaningful name.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Feed Filtering*
    
    </td>
    <td valign="top">
    
    Select a value from the dropdown list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Integration Description*
    
    </td>
    <td valign="top">
    
    Add a link to web page that describes the application. The description doesn't impact the integration and only provides more information.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Callback URL*
    
    </td>
    <td valign="top">
    
    Enter a callback URL for the client application API calls.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Support URL*
    
    </td>
    <td valign="top">
    
    Enter a support URL for the client application API.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Can Suppress Notifications*
    
    </td>
    <td valign="top">
    
    Select the checkbox to allow the suppression of notifications from external data sources that use this OAuth client. It’s up to the developers of this external application integration whether they disable notifications, but this setting determines whether notification suppression is permitted from this external application.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Can Suppress Webhooks*
    
    </td>
    <td valign="top">
    
    Select the checkbox to allow the suppression of webhooks for specific OData calls in the OAuth client. It’s up to the developers of this external application integration whether they disable webhooks, but this setting determines whether webhook suppression is permitted from this external application.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *X509 Certificate \(Base64\)*
    
    </td>
    <td valign="top">
    
    Enter the Transport Layer Security \(TLS; supersedes SSL\) public key certificate string for client application API access.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Administrative Area*
    
    </td>
    <td valign="top">
    
    Select the area in which you want this OAuth Client configuration to be available. The default is *Company*, which makes it available to all areas. Selecting a specific area limits the scope of the OAuth Client configuration and only area administrators assigned to the area and company administrators can manage the configuration.
    
    </td>
    </tr>
    </table>
    
-   After the new OAuth client is created, you can view its details from the main table.

