<!-- loio8288cd29544f4fdca29a8ef6b367278e -->

# Integrating Google Drive

You can use a Google Drive account as a document repository.



Only one Google Drive account can be integrated as a document repository in your site. Note that although Google Drive supports sharing files of many types, the integration is applicable to document type only.

> ### Note:  
> To adhere to SAP's security and compliance requirements, the Google Drive integration has been migrated to an SAP-managed Google Cloud Platform account.
> 
> If you configured an integration with your Google Drive account before November 2025, following this change, the next time you click “Connect Google Drive,” you will have to go through a new client authorization flow to be able to access your drive:
> 
> 1.  In the screen that notifies you that you have not yet authorized an access to Google Drive, click *Continue*.
> 2.  In the Sign in screen, choose your Google account.
> 3.  In the screen with the alert that Google hasn't verified this app, click *Advanced* and then click the link to SAP Build Work Zone \(unsafe\) system.
> 4.  In the next screen, you'll be notified that SAP Build Work Zone wants to access your Google account. Click *Continue*.
> 5.  Your Google Drive account should open in SAP Build Work Zone.

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

