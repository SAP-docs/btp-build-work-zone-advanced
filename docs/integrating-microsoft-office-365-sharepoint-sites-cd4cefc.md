<!-- loiocd4cefc4685f4fd2b3d915bac6b28737 -->

# Integrating Microsoft Office 365 SharePoint Sites

You can integrate sites from your Microsoft Office 365 SharePoint so that the users can access them in SAP Build Work Zone, advanced edition.



<a name="loiocd4cefc4685f4fd2b3d915bac6b28737__section_tts_bs2_blb"/>

## Prerequisites

-   Set up an Azure Active Directory \(Azure AD\) tenant. For more information see, [**Quickstart: Set up a tenant**](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-create-new-tenant)
-   Register the SAP Build Work Zone, advanced edition application with the Microsoft identity platform. For more information, see [**Quickstart: Register an application with the Microsoft identity platform**](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app)

**Important notes for the configuration parameters:**


<table>
<tr>
<th valign="top">

Parameter



</th>
<th valign="top">

More details



</th>
</tr>
<tr>
<td valign="top">

Secret value



</td>
<td valign="top">

Copy the secret value and keep it for when you configure the application in the SAP Build Work Zone, advanced edition admin console. This is the only time this information is displayed.



</td>
</tr>
<tr>
<td valign="top">

Redirect URI structure



</td>
<td valign="top">

URI structure: <DWS URL\>/office365/authorized



</td>
</tr>
<tr>
<td valign="top">

Redirect URI hostname pattern



</td>
<td valign="top">

You can find the hostname pattern that should be used here: [Solution Architecture and Authentication Details](solution-architecture-and-authentication-details-1fd9ea4.md)



</td>
</tr>
<tr>
<td valign="top">

Required API permissions



</td>
<td valign="top">

Please use the following API permissions:

-   Microsoft Graph: `User.Read`
-   SharePoint: `AllSites.Read` and `AllSites.Write`



</td>
</tr>
<tr>
<td valign="top">

User consent settings



</td>
<td valign="top">

If you change the user consent settings to *Do not allow user consent*, please open a support ticket on component `LOD-SF-JAM-SWZ` for further adjustments. For more information, see [**More on API permissions and admin consent**](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#more-on-api-permissions-and-admin-consent) 



</td>
</tr>
</table>



<a name="loiocd4cefc4685f4fd2b3d915bac6b28737__section_k2j_d4g_m5b"/>

## Register the application in SAP Build Work Zone, advanced edition

Create an external application entry to register your external application with SAP Build Work Zone, advanced edition.

1.  In the *Administration Console*, select *External Integrations* \> *External Solutions*.
2.  Choose *Add Application* and select *Microsoft Office 365*.

    Add the following information in the external application form and save your changes.


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
    
    Enter a meaningful name, such as one that describes the external application and its dedicated use. This name appears, for example, in the navigation sidebar, so it’s important to make it something recognizable.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Top-Level Site URL*


    
    </td>
    <td valign="top">
    
    The base URL of your organization's SharePoint server. It must be in one of the following formats:

    ```
    https://<tenant>.sharepoint.com
    https://<tenant>.sharepoint.com/sites/<site>
    ```


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *OAuth 2.0 Client Id*


    
    </td>
    <td valign="top">
    
    The string from the *Client ID* field in your Microsoft Azure configuration.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Secret*


    
    </td>
    <td valign="top">
    
    The value that was displayed in the *keys* section when you saved your Microsoft Azure configuration.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Administrative Area*


    
    </td>
    <td valign="top">
    
    Select the area in which you want this document repository to be available. The default is *Company*, which makes it available to all administrative areas and workspaces.


    
    </td>
    </tr>
    </table>
    



<a name="loiocd4cefc4685f4fd2b3d915bac6b28737__section_ndx_3pg_m5b"/>

## Register the external document libraries

Add the document libraries that you want to make available to the users.

1.  In the *Administration Console*, select *External Integrations* \> *External Solutions*.
2.  Next to the Microsoft Office 365 application, choose *Action*, and select *Manage Document Libraries* from the context menu.
3.  Follow the instructions on the screen to allow SAP Build Work Zone, advanced edition to access the Office 365 application. The *<Office365\_service\>: Document Libraries* screen appears when access is granted.
4.  Choose *Add Document Library*.
5.  Set the name. The name appears in the workspace navigation pane once workspace administrators set up access to a given repository.
6.  Set the *Document Library URL*, which is found by navigating to the document library, and copying the browser URL.

    The URL for the Microsoft Office 365 application must be in one of the following formats:

    ```
    https://<tenant>.sharepoint.com/<subsite>
    https://<tenant>.sharepoint.com/sites/<site>/<subsite>
    ```

7.  Click *Create*.



<a name="loiocd4cefc4685f4fd2b3d915bac6b28737__section_vb3_kpg_m5b"/>

## Next steps

-   If your organization uses unrecognized or self-signed certificates for network access, or if you want to ensure a more secure connection to your document repository, proceed with adding a trusted certificate authority. See [Add a Trusted Certificate Authority](add-a-trusted-certificate-authority-0f5c6b2.md).
-   Browse all linked SharePoint repositories and documents within your workspace. For more information, see [**Microsoft SharePoint**](https://help.sap.com/docs/WZ/fec5ca6e3229418f84a932c745cbe985/59d116a174cf42458e1cafd75cff286b.html).

