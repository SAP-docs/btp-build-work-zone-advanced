<!-- loio97a7ee5b10b3488e872ca84131c8c0ef -->

# Setting Up a Custom Domain

Using the SAP Custom Domain service, administrators can configure a custom domain for exposing a site instead of using the default domain.



<a name="loio97a7ee5b10b3488e872ca84131c8c0ef__section_wzx_yqd_qwb"/>

## What is a Custom Domain?

Instead of using the default domain that is assigned to your subaccount, you can purchase a custom domain with a unique name that is easily recognizable by your users, making them more secure about accessing your site.

For example, if your default domain is `subaccount.cpp.cfapps.eu10.hana.ondemand.com`, you can purchase the domain `mycompany.com`, create a custom domain `sales.mycompany.com`, and securely expose your site under this custom domain.

Using the same domain for a site as well as for all the embedded content including Identity Authentication, enables broader integration scenarios, by avoiding third-party cookies with the respective security drawbacks.

To use custom domains in SAP Build Work Zone, advanced edition, we recommend that you use SAP Cloud Identity Services - Identity Authentication to authenticate your users. If your users are using a corporate identity provider, you can use the Identity Authentication service as a proxy to the corporate identity provider, rather than connect to the Identity Authentication service directly.

In the SAP Build Work Zone, advanced edition scenario, you need to create two custom domains under a single common super domain as follows:

-   One for the SAP Build Work Zone, advanced edition application.

-   One for the authentication - in this case SAP Cloud Identity Services - Identity Authentication.


> ### Note:  
> Please make sure that if you have two different subscriptions to SAP Build Work Zone, advanced edition you need to create a different custom domain for each. You can't share the same custom domain because each one needs to have a unique URL pointing to it.

> ### Note:  
> These are some limitations when using SAP Cloud Identity Services - Identity Authentication
> 
> -   Custom domains aren't supported when accessing a site from the SAP Build Work Zone mobile app.
> 
> -   If an application is launched from a remote content provider connected via direct access \(such as SAP S/4HANA Cloud\), and this content provider doesn't support a common super domain, the app won’t launch. If the content provider is connected via tunneled access, the app will be launched.



<a name="loio97a7ee5b10b3488e872ca84131c8c0ef__section_qns_hxm_4wb"/>

## Prerequisites

-   You're using OpenID Connect \(OIDC\) authentication protocol.

    > ### Note:  
    > Using the Security Assertion Markup Language \(SAML\) authentication protocoI isn't supported. Therefore, if you're already using SAP Cloud Identity Services - Identity Authentication, and need to switch to the OIDC protocol, follow the instructions in this SAP Note [3311563](https://launchpad.support.sap.com/#/notes/3311563).

-   You've configured the required entitlement for the Custom Domain Manager.

-   You have access to the Domain Name System \(DNS\).

-   Please make sure that you've configured clickjacking protection as follows:

    -   SAP S/4HANA Cloud: [Protect Against Clickjacking](https://help.sap.com/viewer/4fc8d03390c342da8a60f8ee387bca1a/latest/en-US/3d1ea8b1a0e145bb851d36d0da376e17.html)
    -   SAP S/4HANA: [Using an Allowlist for Clickjacking Framing Protection](https://help.sap.com/docs/SAP_NETWEAVER_AS_ABAP_751_IP/864321b9b3dd487d94c70f6a007b0397/966b6233e5404ebe80513ae082131132.html).
    -   SAP IBP: [Protect Against Clickjacking](https://help.sap.com/viewer/0292066056f642f1a0f6d9135e39abaf/latest/en-US/3d1ea8b1a0e145bb851d36d0da376e17.html)
    -   SAP BTP ABAP environment: [Protect Against Clickjacking](https://help.sap.com/docs/BTP/10fd1742ea914256abedb34bf15bd069/3d1ea8b1a0e145bb851d36d0da376e17.html?version=Cloud)




<a name="loio97a7ee5b10b3488e872ca84131c8c0ef__section_gf5_jxm_4wb"/>

## Configuration Steps

> ### Note:  
> The process of uploading certificates \(step 3 below\), can take up to four weeks to complete. Once completed, on-premise apps won't be accessible when using the default domain. To avoid a downtime, proceed as soon as possible with the procedure in the table below to switch to Identity Authentication and enable accessing the apps from a custom domain.

> ### Note:  
> The DWS custom domain setup is described in the following KBA: [0002920494](https://launchpad.support.sap.com/#/notes/0002920494)


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

-   For the Identity Authentication tenant.




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

Create a server certificate using the Custom Domain Manager.

> ### Note:  
> This process can take up to four weeks to complete. Once completed, on-premise apps won't be accessible when using the default domain.
> 
> To avoid a downtime, proceed as soon as possible with this procedure to switch to Identity Authentication and enable accessing the apps from a custom domain.



</td>
<td valign="top">

Create a server certificate for your custom domains from a trusted certificate authority.

For more information, see the Custom Domain Manager documentation: [Manage Server Certificates.](https://help.sap.com/docs/CUSTOM_DOMAINS/6f35a23466ee4df0b19085c9c52f9c29/1c4cbe695bed435f80a748a143a8351e.html)



</td>
</tr>
<tr>
<td valign="top">

4



</td>
<td valign="top">

Establish a trust between the subaccount and the Identity Authentication tenant and choose the desired domain.



</td>
<td valign="top">

To use a custom domain, you need to establish a trust between the Identity Authentication tenant and SAP BTP as follows:

-   For new subaccounts, refer to the following documentation: [Establish Trust and Federation Between UAA and Identity Authentication](https://help.sap.com/docs/btp/sap-business-technology-platform/establish-trust-and-federation-between-uaa-and-identity-authentication).

-   For existing subaccounts, migrate from SAML trust configuration to Identity Authentication with OpenID Connect.

    For more information about the migration process, see SAP Note [3311563](https://launchpad.support.sap.com/#/notes/3311563).




</td>
</tr>
<tr>
<td valign="top">

5



</td>
<td valign="top">

Create a CNAME record in the Domain Name Service \(DNS\) so that the custom domain points to the SAP BTP data center.



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

Create a SaaS route for the mapping between your custom domain and the URL of your SAP Build Work Zone, advanced edition subscription.



</td>
<td valign="top">

For more information, see [Manage Saas Routes](https://help.sap.com/docs/CUSTOM_DOMAINS/6f35a23466ee4df0b19085c9c52f9c29/7ad1e85b1cc54366b98c69164731a54d.html).

In the procedure section of this topic, step **e**, you must manually edit the default route of your custom domain \(that you created in **step 2**\) above, and replace it with the subscription URL of SAP Build Work Zone, advanced edition.

> ### Note:  
> If you're using tunneled access to access on-premise apps, in step **e**, edit the SaaS route and use the following format:
> 
> `[subdomain of the SA]-sapdelim-[RT destination name].[service name (launchpad or workzone or workzonehr)].cfapps.[data center].hana.ondemand.com`



</td>
</tr>
<tr>
<td valign="top">

7



</td>
<td valign="top">

Open a support ticket to the Operations team.



</td>
<td valign="top">

Open a ticket with component EP-WZ-DMN, and provide the following information:

-   Subaccount ID

-   Custom domain name

-   URL of the default site


> ### Note:  
> This step is only relevant if you're using XSUAA. If you're using SAP Cloud Identity Services - Identity Authentication, then refer to the following topic: [Configure OpenID Connect Application for Authorization Code Flow.](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/4a9425465cbb4a7aa7c3d86c9cabca51.html?version=Cloud)



</td>
</tr>
</table>

