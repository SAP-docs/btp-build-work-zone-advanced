<!-- loio1615cc3c0c9740a19cdfa22ba66dcce0 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Configuring SSO Between SAP BTP and SAP Analytics Cloud

The steps required to establish a system-to-system trust between the SAP BTP tenant and the SAP Analytics Cloud tenant to enable single sign on \(SSO\).



## Overview

To establish trust between the SAP BTP tenant and the SAP Analytics Cloud tenant you need to perform the following steps:


<table>
<tr>
<th valign="top">

Tenant

</th>
<th valign="top">

Action

</th>
</tr>
<tr>
<td valign="top">

SAP BTP

</td>
<td valign="top">

[Step 1 - Extract data for trust configuration](configuring-sso-between-sap-btp-and-sap-analytics-cloud-1615cc3.md#loio1615cc3c0c9740a19cdfa22ba66dcce0__section_step1)

</td>
</tr>
<tr>
<td valign="top">

SAP Analytics Cloud

</td>
<td valign="top">

[Step 2 - Configure a trusted identity provider](configuring-sso-between-sap-btp-and-sap-analytics-cloud-1615cc3.md#loio1615cc3c0c9740a19cdfa22ba66dcce0__section_step2)

</td>
</tr>
<tr>
<td valign="top">

SAP BTP

</td>
<td valign="top">

[Step 3 - Configure a destination](configuring-sso-between-sap-btp-and-sap-analytics-cloud-1615cc3.md#loio1615cc3c0c9740a19cdfa22ba66dcce0__section_step3)

</td>
</tr>
<tr>
<td valign="top">

Both tenants

</td>
<td valign="top">

[Step 4 - Ensure user assignments in both tenants](configuring-sso-between-sap-btp-and-sap-analytics-cloud-1615cc3.md#loio1615cc3c0c9740a19cdfa22ba66dcce0__section_step4)

</td>
</tr>
</table>



<a name="loio1615cc3c0c9740a19cdfa22ba66dcce0__section_step1"/>

## Step 1 - Extract data for trust configuration

You begin by extracting trust configuration data from SAP BTP. You will use this data in Step 2, to establish the SAP BTP subaccount as a trusted identity provider.

1.  In your SAP BTP subaccount, navigate to *Destination Trust*.

2.  In your *Active Trust Certificate*, click *Export*. This downloads a certificate with trust configuration data.

3.  To decode the certificate and obtain the *Provider Name* \(for Step 2\), in your Terminal, navigate to the directory of the downloaded certificate, and use the following command:

    `openssl x509 -in <yourcertificatefilename> -noout -text | grep CN`

    From the response, make a note of the value of the `Issuer: CN`.

    In addition, open the downloaded certificate, copy the entire certificate content \(excluding the `BEGIN` and `END` delimiters\), and save this content for use in Step 2.




<a name="loio1615cc3c0c9740a19cdfa22ba66dcce0__section_step2"/>

## Step 2 - Configure a trusted identity provider

Configure the SAP Analytics Cloud tenant using the values you obtained in Step 1, to establish the SAP BTP subaccount as a trusted identity provider.

1.  Log in to your SAP Analytics Cloud tenant.

2.  At the bottom left of the screen, navigate to the system configuration, by clicking the <span class="SAP-icons-V5"></span> icon and select *Administration*.

3.  In the *App Integration* tab, scroll down to the *OAuth Clients* section.

4.  Save the values of the following fields:

    -   *OAuth2SAML Token URL*: <`OAuth2SAMLTokenURL`\>

    -   *OAuth2SAML Audience*: <`OAuth2SAMLAudience`\>


    You will need these values in Step 3 below.

5.  In the *Configured Clients* subsection, click *\+ Add a New OAuth Client*.

6.  In the *New OAuth Client* dialog box, enter the following values:


    <table>
    <tr>
    <th valign="top">

    Field
    
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
    
    An arbitrary name for your OAuth client. For example, `My Client`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Purpose*
    
    </td>
    <td valign="top">
    
    Select *API Access*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Access*
    
    </td>
    <td valign="top">
    
    Select all the available values.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Authorization Grant*
    
    </td>
    <td valign="top">
    
    Select *SAML 2.0 Bearer*.
    
    </td>
    </tr>
    </table>
    
7.  Click *Add* to create the client.

8.  In the *OAuth Client Information* dialog box, save the values of the following fields:

    -   *OAuth Client ID*: <`OAuthClientID`\>

    -   *OAuth Secret*: <`OAuthClientIDSecret`\>

        Hint: Click *Use Secret*.


    You will need these values in Step 3 below.

9.  In the *App Integration* tab, scroll down to the *Trust Identity Provider* section.

10. Click *\+ Add a Trusted Identity Provider*.

11. In the *Trusted Identity Provider* dialog box, enter the following values:


    <table>
    <tr>
    <th valign="top">

    Field
    
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
    
    A name to indicate the SAP BTP subaccount that you are using.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Provider Name*
    
    </td>
    <td valign="top">
    
    The value of the `Issuer: CN` that you obtained in Step 1.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Signing Certificate*
    
    </td>
    <td valign="top">
    
    The encoded contents of the certificate that you saved in Step 1.
    
    </td>
    </tr>
    </table>
    
12. Click *Done*.




<a name="loio1615cc3c0c9740a19cdfa22ba66dcce0__section_step3"/>

## Step 3 - Configure a destination

Configure a destination in SAP BTP using the OAuth values you obtained from the SAP Analytics Cloud tenant in Step 2.

1.  In your SAP BTP subaccount, navigate to *Destinations*.

2.  Click *Create Destination* and enter the following \(case sensitive\) values:


    <table>
    <tr>
    <th valign="top">

    Field
    
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
    
    The name of the destination, preferably a short one. For example: `SAC`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL*
    
    </td>
    <td valign="top">
    
    The tenant URL of the SAP Analytics Cloud tenant.
    
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
    
    OAuth2SAMLBearerAssesrtion
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Key Store Location*
    
    </td>
    <td valign="top">
    
    Leave empty.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Key Store Password*
    
    </td>
    <td valign="top">
    
    Leave empty.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Audience*
    
    </td>
    <td valign="top">
    
    <`OAuth2SAMLAudience`\> - obtain this value from Step 2
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *AuthContextClassRef*
    
    </td>
    <td valign="top">
    
    `urn:oasis:names:tc:SAML:2.0:ac:classes:PreviousSession`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Client Key*
    
    </td>
    <td valign="top">
    
    <`OAuthClientID`\> - obtain this value from Step 2
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service URL Type*
    
    </td>
    <td valign="top">
    
    dedicated
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service URL*
    
    </td>
    <td valign="top">
    
    <`OAuth2SAMLTokenURL`\> - obtain this value from Step 2
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service User*
    
    </td>
    <td valign="top">
    
    <`OAuthClientID`\> - obtain this value from Step 2
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service Password*
    
    </td>
    <td valign="top">
    
    <`OAuthClientIDSecret`\> - obtain this value from Step 2
    
    </td>
    </tr>
    </table>
    
3.  Click *New Property* to add the following *Additional Properties*:


    <table>
    <tr>
    <th valign="top">

    Field
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *HTML5.DynamicDestination*
    
    </td>
    <td valign="top">
    
    true

    > ### Caution:  
    > Adding an `HTML5.DynamicDestination` property and setting it to true, enables dynamic access to the destination to any logged-in user.
    > 
    > Therefore before adding this property to the destination, make sure that the underlying API is not public and requires the correct user credentials.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *HTML5.SetXForwardedHeaders*
    
    </td>
    <td valign="top">
    
    false
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *nameIdFormat*
    
    </td>
    <td valign="top">
    
    `urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *userIdSource*
    
    </td>
    <td valign="top">
    
    email
    
    </td>
    </tr>
    </table>
    
4.  Save.




<a name="loio1615cc3c0c9740a19cdfa22ba66dcce0__section_step4"/>

## Step 4 - Ensure user assignments in both tenants

Each user who should be able to read the data must be added with identical email addresses to both the SAP Analytics Cloud tenant and the SAP Build Work Zone, advanced edition tenant.

We recommend using the same Identity Authentication tenant for a complete SSO experience.



<a name="loio1615cc3c0c9740a19cdfa22ba66dcce0__section_ikp_jsg_41c"/>

## How to verify that the SSO is working?

To check whether a successful connection has been set up for SSO, use the following URL in your browser:

-   Only users with the Admin role can use a link such as the following:

    `https://<SAPBuildWorkZoneURL>.hana.ondemand.com/dynamic_dest/<BTPDestinationName>/oauthservice/api/v1/tenantinfo`

-   Other users who have access to the content can use a link such as the following:

    `https://<SAPBuildWorkZoneURL>.hana.ondemand.com/dynamic_dest/<BTPDestinationName>/widgetquery/getWidgetData?storyId=<StoryID>&widgetId=<widgetID>&type=kpiTile`


If you receive a response \(with `tokenEndpoint`\), and do not receive any error, this indicates that the connection is working.

**Related Information**  


[Exposing SAP Analytics Cloud KPIs in the Joule Work Mobile App](exposing-sap-analytics-cloud-kpis-in-the-joule-work-mobile-app-59f79cf.md "The steps required to expose SAP Analytics Cloud KPIs as tiles in the Joule Work mobile app and widgets on the home or lock screen.")

