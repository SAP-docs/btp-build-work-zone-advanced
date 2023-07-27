<!-- loio8288cd29544f4fdca29a8ef6b367278e -->

# Integrating Google Drive

You can provide access to your organization's Google Drive account as a document repository.



While Google Drive supports sharing files of many types, it’s the document files that are the focus of the Google Drive integration.

> ### Note:  
> Only one Google Drive can be integrated into your SAP Build Work Zone, advanced edition.

1.  In the *Administration Console*, select *External Integrations* \> *External Solutions*.
2.  On the *External Applications* page, choose *Add Application* and select *Google Drive* from the dropdown menu.

    The form for integrating access to a Google Drive account opens. Enter the following:


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
    
    Enter a recognizable name. The name appears in the SAP Build Work Zone, advanced edition navigation sidebar and in other locations in SAP Build Work Zone, advanced edition.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Use custom credential*


    
    </td>
    <td valign="top">
    
    To integrate your organization's existing Google Drive account, select this option and enter the OAuth 2.0 client ID and secret.

    If you don’t select this option, you integrate the default SAP Build Work Zone, advanced edition account registered with Google, using a system default client ID and secret.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *OAuth 2.0 Client Id*


    
    </td>
    <td valign="top">
    
    The *client\_id* field that you used to create your existing Google Drive account.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Secret*


    
    </td>
    <td valign="top">
    
    The *client\_secret* that was provided when you created your existing Google Drive account.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Administrative Area*


    
    </td>
    <td valign="top">
    
    Select the area in which you want this document repository to be available. The default is *Company*, which makes it available to all workspaces and areas.


    
    </td>
    </tr>
    </table>
    
3.  Save your entries.

> ### Note:  
> If your organization uses unrecognized or self-signed certificates for network access, or if you want to ensure a more secure connection to your document repository, you must add a trusted certificate authority.

