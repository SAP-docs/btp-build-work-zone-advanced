<!-- loiob3c804e1f999448b8011a475fea1da6c -->

# Add an OAuth Client

You can authorize an external application to access the SAP Build Work Zone, advanced edition API by registering an application as an OAuth client.

1.  In the *External Integrations* section, on the *OAuth Clients* page, choose *Add OAuth Client*.

    The *Register a new OAuth Client* form opens.

2.  Enter the following values:


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
    
    Enter a meaningful name that allows company administrators to recognize what the client is.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Feed Filtering*


    
    </td>
    <td valign="top">
    
    Select a value from the dropdown list..


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Integration URL*


    
    </td>
    <td valign="top">
    
    Enter the URL to the client application API metadata.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Callback URL*


    
    </td>
    <td valign="top">
    
    Enter the callback URL for the client application API calls.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Support URL*


    
    </td>
    <td valign="top">
    
    Enter the support URL for the client application API.


    
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

    For more information about webhooks, see [Chatbot Actions](50-Chatbots/chatbot-actions-f640146.md) in the developer guide.


    
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
    
    Select the area in which you want this OAuth Client configuration to be available. The default is *Company*, which makes it available to all groups and areas. Selecting a specific area limits the scope of the OAuth Client configuration and only area administrators assigned to the area and company administrators can manage the configuration.


    
    </td>
    </tr>
    </table>
    
3.  Save your entries.


