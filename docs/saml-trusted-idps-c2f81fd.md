<!-- loioc2f81fd55cf5451c9c6c5e3c55760d0f -->

# SAML Trusted IDPs

Security Assertion Markup Language \(SAML\) enables single sign-on \(SSO\). When you register a trusted SAML identity provider \(IDP\), users are authenticated and stored in SAP Build Work Zone, advanced edition.

By registering an external application as a SAML trusted Identity Provider \(IDP\), you allow the application to access the SAP Build Work Zone, advanced edition user ID and authorization information. Users then see only the content they're authorized to view when SAP Build Work Zone, advanced edition features are integrated into an external application.

**How to register SAML trusted IDPs**

You manage SAML trusted IDPs in the *Administration Console*.

1.  In the *Administration Console*, expand the *Authentication & Authorization* section and click *SAML Trusted IDP*.

2.  To add an identity provider, click *Register your SAML Trusted IDP*.

3.  You can upload a metadata file that contains the settings or you can enter the values manually:

    > ### Note:  
    > The following settings apply only to the Digital Workplace Service \(DWS\) component of the product. For more information about the overall trust settings, see [User Authentication, Provisioning and Authorization](user-authentication-provisioning-and-authorization-f04c185.md).


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
    
    *IDP ID*


    
    </td>
    <td valign="top">
    
    Enter the URL of your identity provider, or a name that indicates who the trusted SAML identity provider is, or the application name for which the trusted SAML identity provider is providing single sign-on services.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Single Sign-On URL*


    
    </td>
    <td valign="top">
    
    Enter the URL used for single sign-on \(SSO\) with the identity provider \(IDP\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Single Log-Out URL*


    
    </td>
    <td valign="top">
    
    Enter the URL used for single log-out \(SLO\) with the identity provider \(IDP\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Default Name ID Format*


    
    </td>
    <td valign="top">
    
    Enter which name ID format is to be used in an authentication request.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Default Name ID Policy SP Name Qualifier*


    
    </td>
    <td valign="top">
    
    Enter the default service provider \(SP\) name qualifier that is to be used in an authentication request.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *X509 Certificate \(Base64\)*


    
    </td>
    <td valign="top">
    
    Enter the Transport Layer Security \(TLS\) public key certificate string for the client application's API access.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Enabled* 


    
    </td>
    <td valign="top">
    
    \[Optional\] Specifies whether SAML Assertions are accepted from this identity provider. Select *Enabled* to make this trusted SAML identity provider available immediately.

    > ### Note:  
    > You can enable or disable the entry in the *SAML Trusted IDPs* page at any time.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *External*


    
    </td>
    <td valign="top">
    
    Specifies whether this trusted SAML identity provider is used to authenticate external users.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Administrative Area*


    
    </td>
    <td valign="top">
    
    Select the area in which you want this SAML Trusted IDP configuration to be available. The default is *Company*, which makes it available to all workspaces and areas. Selecting a specific area limits the scope of the SAML Trusted IDP configuration and limits the management of that configuration to either area administrators who are responsible for that area or to company administrators.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Primary*


    
    </td>
    <td valign="top">
    
    The default IDP used for SSO redirect. There can only be one primary IDP in a company. This setting can't be changed by the admin.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Issuer namespace*


    
    </td>
    <td valign="top">
    
    There can be only one primary identity provider configured within your organization. This option is preset to *Company Specific*.


    
    </td>
    </tr>
    </table>
    
4.  Choose *Register*.

**Manage your SAML Trusted IDPs**


<table>
<tr>
<th valign="top">

Action



</th>
<th valign="top">

More information



</th>
</tr>
<tr>
<td valign="top">

Enable or disable a SAML Trusted IDP.



</td>
<td valign="top">

Change the slider control in the left-most column of the row with the SAML Trusted IDP.



</td>
</tr>
<tr>
<td valign="top">

View the information for a SAML Trusted Identity Provider.



</td>
<td valign="top">

Click *Action* in the right-most column of the row with the SAML Trusted IDP, and then select*View* from the menu.

A page displays the configuration details of the selected SAML trusted IDP.

You can either modify the information by clicking *Edit* or return to the *SAML Trusted IDPs* page by clicking *Back*.



</td>
</tr>
<tr>
<td valign="top">

Edit a configured SAML Trusted IDP.



</td>
<td valign="top">

There are 2 ways to edit a SAML trusted IDP:

-   Click *Action* in the right-most column of the row with the SAML Trusted IDP, and then select *Edit* from the menu.

-   Click *View* from the same menu, to view the details of the relevant SAML Trusted IDP and then click *Edit* at the bottom of the details page.


*Save* the changes that you make.



</td>
</tr>
<tr>
<td valign="top">

Delete a SAML Trusted Identity Provider entry.



</td>
<td valign="top">

Click *Action* in the right-most column of the row with the SAML Trusted IDP that you want to delete, and then click*Delete* from the menu.

A confirmation dialog box appears. Click *Delete* to confirm and remove the selected SAML Trusted IDP record.



</td>
</tr>
</table>

