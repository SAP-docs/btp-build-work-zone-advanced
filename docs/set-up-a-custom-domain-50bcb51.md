<!-- loio50bcb51897074fd985d97f766c9f8698 -->

# Set Up a Custom Domain

In this topic, you'll learn how to set up a custom domain using SAP Cloud Identity Services - Identity Authentication.



To set up a custom domain using SAP Cloud Identity Services - Identity Authentication, you need to create the following custom domains under a single common super domain as follows:

-   One for the SAP Build Work Zone, advanced edition application.

-   One for the authentication - in this case SAP Cloud Identity Services - Identity Authentication.

-   A custom domain for Digital Workplace Service \(DWS\) should also be created. This custom domain should use the same top-level domain as the custom domain for the SAP Build Work Zone, advanced edition application. This custom domain, server certificate, and private key should not be created using the SAP Custom Domain Manager service.




> ### Note:  
> Please make sure that if you have two different subscriptions to SAP Build Work Zone, advanced edition, you need to create a different custom domain for each. You can't share the same custom domain because each one needs to have a unique URL pointing to it.

> ### Note:  
> If your users are using a corporate identity provider, you can use the Identity Authentication service as a proxy to the corporate identity provider, rather than connect to the corporate identity provider directly.



<a name="loio50bcb51897074fd985d97f766c9f8698__section_tvs_p2c_dzb"/>

## Prerequisites


-   Make sure that you’ve switched to SAP Cloud Identity Services - Identity Authentication.

    For more information, see [Post Booster Configuration](https://help.sap.com/docs/build-work-zone-advanced-edition/sap-build-work-zone-advanced-edition/post-booster-configuration).

-   Make sure you've established a trust between the Identity Authentication tenant and SAP BTP as follows:
    -   For new subaccounts, refer to the following documentation: [Establish Trust and Federation Between UAA and Identity Authentication](https://help.sap.com/docs/btp/sap-business-technology-platform/establish-trust-and-federation-between-uaa-and-identity-authentication).

    -   For existing subaccounts, migrate from SAML trust configuration to Identity Authentication with OpenID Connect.

        For more information about the migration process, see SAP Note [3311563](https://me.sap.com/notes/3311563).



-   You're using OpenID Connect \(OIDC\) authentication protocol.

    > ### Note:  
    > Using the Security Assertion Markup Language \(SAML\) authentication protocoI isn't supported. Therefore, if you're already using SAP Cloud Identity Services - Identity Authentication, and need to switch to the OIDC protocol, follow the instructions in this SAP Note To set a default site, in the Site Directory of your subaccount, choose a site as the default site, and click the … on the site tile. From the action menu, choose [3311563](https://me.sap.com/notes/3311563).

-   You've configured the required entitlement for the Custom Domain Manager.

-   You have access to the Domain Name System \(DNS\).

-   Please make sure that you've configured clickjacking protection as follows:

    -   SAP S/4HANA Cloud: [Protect Against Clickjacking](https://help.sap.com/viewer/4fc8d03390c342da8a60f8ee387bca1a/latest/en-US/3d1ea8b1a0e145bb851d36d0da376e17.html)
    -   SAP S/4HANA: [Using an Allowlist for Clickjacking Framing Protection](https://help.sap.com/docs/SAP_NETWEAVER_AS_ABAP_751_IP/864321b9b3dd487d94c70f6a007b0397/966b6233e5404ebe80513ae082131132.html).
    -   SAP IBP: [Protect Against Clickjacking](https://help.sap.com/viewer/0292066056f642f1a0f6d9135e39abaf/latest/en-US/3d1ea8b1a0e145bb851d36d0da376e17.html)
    -   SAP BTP ABAP environment: [Protect Against Clickjacking](https://help.sap.com/docs/BTP/10fd1742ea914256abedb34bf15bd069/3d1ea8b1a0e145bb851d36d0da376e17.html?version=Cloud)




<a name="loio50bcb51897074fd985d97f766c9f8698__section_hwy_y2c_dzb"/>

## Configuration Steps

The following table gives you an outline of what configuration steps need to be carried out. For more detailed information about how to do these steps, please refer to the following tutorial: [Get Started with Creating a Custom Domain in SAP Build Work Zone, advanced edition](https://developers.sap.com/tutorials/cp-portal-cloud-foundry-create-custom-domain-adv.html)

> ### Note:  
> The process of uploading certificates \(step 3 below\), can take up to two weeks to complete. Once completed, on-premise apps won't be accessible when using the default domain. To avoid a downtime, proceed as soon as possible with the procedure in the table below to switch to Identity Authentication and enable accessing the apps from a custom domain.


<table>
<tr>
<th valign="top">

Step number

</th>
<th valign="top">

Action

</th>
<th valign="top">

More information

</th>
</tr>
<tr>
<td valign="top">

1

</td>
<td valign="top">

Subscribe to the Custom Domain Manager.

</td>
<td valign="top">

To use the Custom Domain Manager, you need to subscribe to it. You do this in the SAP BTP cockpit in the *Instances and Subscriptions* tab of your subaccount.

For more information, see the Custom Domain Manager documentation: [Initial Setup](https://help.sap.com/docs/CUSTOM_DOMAINS/6f35a23466ee4df0b19085c9c52f9c29/1deab96e7aec447fbf8b683ba91a42e0.html).

</td>
</tr>
<tr>
<td valign="top">

2

</td>
<td valign="top">

Create the following custom domains:

-   For your subaccount in SAP Build Work Zone, advanced edition 

-   For Digital Workplace Service \(DWS\)

-   For the Identity Authentication tenant.

-   \[Optional\] For on-premise apps using tunnelled access.

For example:

If the reserved domain is `mycompany.com`, then the custom domains would look like this:

-   **SAP Build Work Zone**: <code>workzone.mycompany.com</code>

-   **IdP**: `idp.mycompany.com`

-   **On-premise such as SAP S/4HANA**: `s4.mycompany.com`


> ### Note:  
> Please make sure that when you create your custom domain, that you don't add a double dash to the domain name.



</td>
<td valign="top">

-   You create a custom domain for your subaccount in the Custom Domain Manager.

    For more information, see the Custom Domain Manager documentation: [Manage Reserved and Custom Domains.](https://help.sap.com/docs/CUSTOM_DOMAINS/6f35a23466ee4df0b19085c9c52f9c29/25ec7eaf439341e7bf52a280d3797c6e.html)

    > ### Note:  
    > If you're using tunneled access to access on-premise apps, add a custom domain for each runtime destination that is configured in your subaccount and mapped to your on-premise provider.
    > 
    > Use the following format: `[runtime destination name].[your reserved domain]`

-   You configure a custom domain for the Identity Authentication service in the SAP Cloud Identity Services - Identity Authentication admin environment.

    For more information, see the following Identity Authentication documentation: [Use Custom Domain in Identity Authentication.](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/c4db840ff2464e12ab68d94efb0769c3.html)




</td>
</tr>
<tr>
<td valign="top">

3

</td>
<td valign="top">

Create server certificates for both SAP Build Work Zone, advanced edition and the Identity Authentication tenant custom domains as follows:

-   For the subscription to use the Custom Domain Manager.

-   For the Identity Authentication tenant, use the Identity Authentication service.

> ### Note:  
> This process can take up to two weeks to complete. Once completed, on-premise apps won't be accessible when using the default domain.
> 
> To avoid a downtime, proceed as soon as possible with this procedure to switch to Identity Authentication and enable accessing the apps from a custom domain.



</td>
<td valign="top">

Make sure you have configured Transport Layer Security \(TLS\) and create a server certificate for your custom domains from a trusted certificate authority.

-   For more information, see the Custom Domain Manager documentation: [Manage TLS Configurations](https://help.sap.com/docs/custom-domain/custom-domain-manager/manage-tls-configurations?&version=Cloud) and [Manage Server Certificates](https://help.sap.com/docs/CUSTOM_DOMAINS/6f35a23466ee4df0b19085c9c52f9c29/1c4cbe695bed435f80a748a143a8351e.html).

-   For more information, see the Identity Authentication documentation: [Use Custom Domain in Identity Authentication](https://help.sap.com/docs/identity-authentication/identity-authentication/use-custom-domain-in-identity-authentication?version=Cloud).




</td>
</tr>
<tr>
<td valign="top">

4

</td>
<td valign="top">

Create the following SaaS routes:

1.  Create a SaaS route for the mapping between your custom domain and the URL of your SAP Build Work Zone, advanced edition subscription.

2.  Create a SaaS route for the mapping between your runtime destination custom domain and the URL with the`-sapdelim` string.




</td>
<td valign="top">

For more information, see [Manage Saas Routes](https://help.sap.com/docs/CUSTOM_DOMAINS/6f35a23466ee4df0b19085c9c52f9c29/7ad1e85b1cc54366b98c69164731a54d.html).

For step 2:

If you have a runtime destination that is used for your on-premise apps with tunneled access, in the *Edit Route* step of the *Manage SaaS Route* procedure, use the following format:

-   For the `ondemand.com` domain:

    `[subdomain of the subaccount]-sapdelim-[Runtime destination name].[service name (launchpad or workzone or workzonehr)].cfapps.[data center].hana.ondemand.com`




</td>
</tr>
<tr>
<td valign="top">

5

</td>
<td valign="top">

Create a CNAME record in the Domain Name Service \(DNS\) so that the custom domain points to the SAP BTP data center.

> ### Note:  
> If your Cloud Foundry Environment, API endpoint is on an extension landscape such as eu10-004, you need to map your DNS to the main landscape. This is because the SAP BTP service that your subaccount is subscribed to, is located in the main landscape.
> 
> For more information, see [Custom Domains in Extension Landscapes](https://help.sap.com/docs/custom-domain/custom-domain-manager/custom-domains-in-extension-landscapes?version=Cloud).



</td>
<td valign="top">

You must configure the Domain Name System \(DNS\) in order to route traffic to an application on your custom domain. For each custom domain that you use, you must create a CNAME mapping from the custom domain to its Cloud Foundry domain.

For more information, see the Custom Domain Manager documentation: [Configure the DNS for a Custom Domain.](https://help.sap.com/docs/CUSTOM_DOMAINS/6f35a23466ee4df0b19085c9c52f9c29/ec2903f6c1a7400aabd77fbbbdefa25b.html) 

</td>
</tr>
<tr>
<td valign="top">

6

</td>
<td valign="top">

Configure redirect URI.

</td>
<td valign="top">

-   For new subscriptions, \(created after September 4th, 2025\), *URI* and *Post Logout Redirect URIs* for custom domains will be done automatically after the custom SaaS Route mapping has been added. For more information, see [SaaS Applications with SAP Identity Service-Based User Authentication.](https://help.sap.com/docs/custom-domain/custom-domain-manager/saas-applications-with-sap-identity-service-based-user-authentication)

-   For existing subscriptions, the IAS administrator needs to manually configure the *URI* and *Post Logout Redirect URIs* for the custom domain in the Identity Authentication tool.

    This should be done after subscribing to SAP Build Work Zone, advanced edition, and after the custom domain has been configured in the Custom Domain manager \(including the Saas Route Mapping\).

    Refer to the following topic: [Configure OpenID Connect Application for Authorization Code Flow.](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/4a9425465cbb4a7aa7c3d86c9cabca51.html?version=Cloud)

    The following is an example of the recommended URI, which should be configured in your Identity Authentication tenant, OpenID connect configuration:<code><b>https://*.mycompany.com/**</b></code>

    This configuration covers both log in and logout callback URIs.




</td>
</tr>
<tr>
<td valign="top">

7

</td>
<td valign="top">

Select the domain for your subaccount.

</td>
<td valign="top">

Select the preferred custom domain for your subaccount from the list of available domains configured in the Custom Domain Service.

You can do this in the Subaccount Settings screen, under the *Custom Domains* tab.

For more information, see [Subaccount Settings](subaccount-settings-2d651c7.md)

</td>
</tr>
<tr>
<td valign="top">

8

</td>
<td valign="top">

Transition between SAP Jam and SAP Build Work Zone, advanced edition

</td>
<td valign="top">

For more information, see Step 10 in the tutorial: [Get Started with Creating a Custom Domain in SAP Build Work Zone, advanced edition](https://developers.sap.com/tutorials/cp-portal-cloud-foundry-create-custom-domain-adv.html).

</td>
</tr>
</table>



<a name="loio50bcb51897074fd985d97f766c9f8698__section_jmz_wfc_dzb"/>

## Limitations

If you're using version 1 \(V1\) for the exposure of ABAP-based content, the following limitation applies. For more information about V1 and V2, see the first note in [Federation of Remote Content Providers](https://help.sap.com/docs/cloud-portal-service/sap-cloud-portal-service-on-cloud-foundry/federation-of-remote-content-providers).

If an application is launched from a remote content provider connected via direct access \(such as SAP S/4HANA Cloud\), and this content provider doesn't support a common super domain, the app won’t launch. If the content provider is connected via tunneled access, the app will be launched.



<a name="loio50bcb51897074fd985d97f766c9f8698__section_tky_hhj_pzb"/>

## Using a Custom Domain in Mobile

For more information about the required setup for using a custom domain in mobile, see [Setting Up a Custom Domain for SAP Build Work Zone Advanced Mobile App](https://help.sap.com/docs/WZ/b03c84105ff74f809631e494bd612e83/274e2348b45e43d7b3ed865964c4a2fa.html) 



