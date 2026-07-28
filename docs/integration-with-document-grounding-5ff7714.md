<!-- loio5ff7714a86c94e4db68cdaa492d31fdd -->

# Integration With Document Grounding

Integrate SAP Build Work Zone, advanced edition with document grounding to make workspace content available as an AI source.



## Overview

The document grounding capability uses information gathered from documents as a resource for AI tools. To set a workspace as an AI source, simply click *Enable as AI Source* next to the workspace in the following screen: *Administration Console* \> *Area & Workspace Configuration* \> *Workspaces.* 

SAP Build Work Zone, advanced edition includes many types of content that contains company-specific knowledge, which can provide valuable context to AI queries from customers.

**What you should know about using documents in a workspace as an AI source**:

-   Documents that have an access level of 'Hidden' can't be synced for document grounding.

-   If a parent workspace is set as an AI source, its subworkspaces do not automatically become AI sources. They must be configured separately if they need to act as AI sources.

-   Documents from both public and private workspaces can be used as an AI source for document grounding.

    > ### Note:  
    > If you are switching over from a public to a private workspace, please be patient - it can take some time.

-   To ensure the quality of the data fetched from uploaded documents make sure to upload only documents with valid information.


For the list of supported content types for document grounding, see [Supported content types](https://help.sap.com/docs/JOULE/6189c8655c484916bb8eb767126a653a/ade9ce3c7c5546988cccea15ec35d373.html).



## Integration process for document grounding

To integrate SAP Build Work Zone, advanced edition with document grounding, complete the following setup:

1.  Create an OAuth client for document grounding.

    In the Admin Console, go to *External Integrations* \> *OAuth Clients*, and click *Add OAuth Client*.

    -   Name - provide a meaningful name such as "Document Grounding OAuth Client".
    -   Integration Description - describe the OAuth client integration, using text or a URL format. The description doesn't impact the integration itself.

    **Important** - once the OAuth client is created, note down the values of the `Key` and `Secret`. You'll need these values in the next steps.

2.  Enable the document grounding feature.

    In the Admin Console, go to *Feature Enablement* \> *Features*, and in the *Feature Management* section, enable the option *Enable document grounding integration*. Select the OAuth client that you created in the previous step, and save your changes.

3.  Create a destination for this integration.

    In the subaccount cockpit, go to *Connectivity* \> *Destinations*, and create a new destination with the following details:


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
    
    URL
    
    </td>
    <td valign="top">
    
    The URL is `https://<DWS URL>/api/v1/dg-pipeline/metadata`

    You can find the value of your tenant DWS URL in the Admin Console, *Overview* screen.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Type
    
    </td>
    <td valign="top">
    
    Internet
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication
    
    </td>
    <td valign="top">
    
    OAuth2ClientCredentials
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client ID
    
    </td>
    <td valign="top">
    
    Enter the value of the OAuth client `Key` you created earlier.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client Secret
    
    </td>
    <td valign="top">
    
    Enter the value of the OAuth client `Secret` you copied earlier.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service URL Type
    
    </td>
    <td valign="top">
    
    Dedicated
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service URL
    
    </td>
    <td valign="top">
    
    Enter your DWS URL/api/v1/auth/token

    For example: `https://xxx.workzone.ondemand.com/api/v1/auth/token`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Additional Properties
    
    </td>
    <td valign="top">
    
    \(Click *New Property* and manually add these properties to the destination\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    HTML5.DynamicDestination
    
    </td>
    <td valign="top">
    
    true

    > ### Note:  
    > By default, a destination doesn't allow dynamic access. However adding an HTML5.DynamicDestination property and setting it to true, enables dynamic access to the destination to any logged-in user.
    > 
    > Therefore before adding this property to the destination, make sure that the underlying API is not public and requires the correct user credentials.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SetXForwardedHeaders
    
    </td>
    <td valign="top">
    
    false
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    HTML5.SetXForwardedHeaders
    
    </td>
    <td valign="top">
    
    false
    
    </td>
    </tr>
    </table>
    
4.  Complete the set up steps for document grounding. For more information, see [Set Up Document Grounding](https://help.sap.com/docs/JOULE/6189c8655c484916bb8eb767126a653a/ade9ce3c7c5546988cccea15ec35d373.html).

