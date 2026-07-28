<!-- loio2d651c7486004d269624255bcda4290a -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Subaccount Settings

There are a number of features that affect your site on the subaccount level.

To get to your subaccount settings, go to the Site Manager as follows:

1.  Under your avatar, click *Administration Console*.

2.  Go to the *External Integrations* screen, expand it, and click *Business Content*.

3.  In the screen that opens, click *Content Manager*.

In the side navigation panel of your site, click the :gear: \(Settings\) icon. You'll notice a strip of tabs at the top of the screen. From here, you can do the following:


<table>
<tr>
<th valign="top">

Tab

</th>
<th valign="top">

Details

</th>
<th valign="top">

Link to more information

</th>
</tr>
<tr>
<td valign="top">

*Error Log*

</td>
<td valign="top">

From this screen, you can troubleshoot the approuter errors in the system during the last 24 hours.

</td>
<td valign="top">

[Diagnosing System Errors Using Error Logs](https://help.sap.com/viewer/b03c84105ff74f809631e494bd612e83/Cloud/en-US/11efe4198fcc4a54a86ed660fd925f4d.html)

</td>
</tr>
<tr>
<td valign="top">

*Notifications*

</td>
<td valign="top">

By default you are using the default notifications mechanism that displays notifications only from SAP Build Work Zone, advanced edition.

From this screen you can switch to the central SAP BTP notification mechanism in order to view notifications from additional notification providers.

Once you've successfully switched to the SAP BTP notification mechanism, there are two elements that you can configure:

-   Choose the authentication identifier that is relevant to your provider - the identifier can be an *Email* or a *User ID*.

-   Generate credentials.

    Before developers can enable their custom apps to publish notifications, they need the details of a destination that you create in the SAP BTP cockpit. To create the destination, you'll first need to generate the credentials on this screen.


> ### Note:  
> To access this tab and configure the authentication identifier and generate credentials, you need to add the relevant business roles to a new or existing role collection. For more information about how to do this, see SAP Note [3315110](https://me.sap.com/notes/3315110).



</td>
<td valign="top">

[Managing Notifications](managing-notifications-08d8ac6.md)

</td>
</tr>
<tr>
<td valign="top">

*Alias Mapping*

</td>
<td valign="top">

> ### Note:  
> Relevant only to manual integration of apps - not federated content.

When a back-end system has aliases, in this screen, you'll need to map these aliases to the relevant runtime destination to enable successful navigation to the apps.

</td>
<td valign="top">

[Map Back-End System Aliases to Runtime Destinations](https://help.sap.com/viewer/ad4b9f0b14b0458cad9bd27bf435637d/Cloud/en-US/0a7f9acd4dba4aa1b84f7f36b3330d84.html)

</td>
</tr>
<tr>
<td valign="top">

*Security Headers*

</td>
<td valign="top">

HTTP security headers provide an extra layer of security by restricting actions that the browser and server allow once your site is running. To protect the data, in this screen you can add one or more of the supported HTTP security headers.

</td>
<td valign="top">

[Using Security Headers](using-security-headers-da26650.md) 

</td>
</tr>
<tr>
<td valign="top">

*Identity Provisioning*

</td>
<td valign="top">

Connect your subaccount with the SAP Cloud Identity Services - Identity Provisioning, which handles provisioning of identities and their authorizations to various cloud and on-premise business applications.

</td>
<td valign="top">

[Configure Integration with the Identity Provisioning Service](https://help.sap.com/docs/WZ_STD/8c8e1958338140699bd4811b37b82ece/1c231333f1d24ae0a8e60ce688c4f692.html) 

</td>
</tr>
<tr>
<td valign="top">

*Identity Authentication*

> ### Note:  
> For subscriptions created after 20th March 2025, Identity Authentication is the default authentication mechanism and this step is not required. Therefore, this tab won't appear in the menu bar.



</td>
<td valign="top">

SAP Cloud Identity Services - Identity Authentication is a cloud service for authentication, single sign-on, and user management. Enable this setting, to switch from SAP Authorization and Trust Management service \(XSUAA\) to Identity Authentication. This change doesn't affect the authentication flow for the other services in the subaccount.

> ### Note:  
> Before enabling the use of Identity Authentication, make sure that you have an OIDC-based trust between SAP Cloud Identity Services – Identity Authentication and SAP BTP. For more information, see [Establish Trust and Federation Between SAP Authorization and Trust Management Service and SAP Cloud Identity Services](https://help.sap.com/docs/btp/sap-business-technology-platform/establish-trust-and-federation-between-uaa-and-identity-authentication?version=Cloud)



</td>
<td valign="top">

[Set Up a Custom Domain](set-up-a-custom-domain-50bcb51.md) 

</td>
</tr>
<tr>
<td valign="top">

*Custom Domains*

</td>
<td valign="top">

Administrators should select a preferred custom domain for their subaccount from the list of available domains configured in the Custom Domain Service.

</td>
<td valign="top">

-   [Set up a Custom Domain - SAP Authentication and Trust Management \(XSUAA\)](set-up-a-custom-domain-sap-authentication-and-trust-management-xsuaa-ae475bf.md)

-   [Set Up a Custom Domain](set-up-a-custom-domain-50bcb51.md)




</td>
</tr>
<tr>
<td valign="top">

*Mobile Settings*

</td>
<td valign="top">

SAP Mobile Services enables simple mobile application development, configuration, and management.

You can configure settings related to the Joule Work mobile app directly from this screen However, please make sure you have the required role.

> ### Note:  
> The Joule Work mobile app is enabled per site while the mobile settings are configured in the subaccount level, Therefore, any change to the mobile settings \(for example, passcode policy\) will affect all sites that are connected to the Joule Work mobile app in this subaccount.



</td>
<td valign="top">

For more information about SAP Mobile Services, see [SAP Mobile Services documentation](https://help.sap.com/doc/f53c64b93e5140918d676b927a3cd65b/Cloud/en-US/docs-en/index.html).

For more information about the required roles, see [Mobile Services Admin Cockpit](https://help.sap.com/docs/mobile-start/mobile-start-administration-guide/start-admin-cockpit-access-control).

</td>
</tr>
</table>

