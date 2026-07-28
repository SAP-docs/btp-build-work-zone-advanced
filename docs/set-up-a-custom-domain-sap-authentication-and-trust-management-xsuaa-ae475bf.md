<!-- loioae475bf4dd944a70b864751c93e6bc5c -->

# Set up a Custom Domain - SAP Authentication and Trust Management \(XSUAA\)

You can set up a custom domain using SAP Authentication and Trust management service \(XSUAA\).



<a name="loioae475bf4dd944a70b864751c93e6bc5c__section_kyb_pgx_r2c"/>

## Overview

Some scenarios, such as using a custom domain in the site, are fully supported only when the default authentication method is SAP Cloud Identity Services - Identity Authentication. In China \(Shanghai\) region, Identity Authentication is not supported for the use of custom domain , and instead the authentication is done via the SAP Authentication and Trust Management service \(XSUAA\).

When using XSUAA-based custom domain you can expect the following limitations:

-   Integrating applications from SAP BTP content providers as well as remote content providers is not supported except for local content from the HTML5 repo. The reason is that the runtime destination of the federated content must also support the specific custom domain pattern.
-   Running applications in an iframe could result in issues related to third-party cookies, unless the apps are added from the HTML5 repo, and as long as the apps and the site are using the same super domain. This is applicable to both static and dynamic \(OData calls\) tiles.



## Prerequisites

-   You've configured the required entitlement for the Custom Domain Manager.

-   You have access to the Domain Name System \(DNS\).

-   You've configured clickjacking protection as follows:

    -   SAP S/4HANA Cloud: [Protect Against Clickjacking](https://help.sap.com/viewer/4fc8d03390c342da8a60f8ee387bca1a/latest/en-US/3d1ea8b1a0e145bb851d36d0da376e17.html)
    -   SAP S/4HANA: [Using an Allowlist for Clickjacking Framing Protection](https://help.sap.com/docs/SAP_NETWEAVER_AS_ABAP_751_IP/864321b9b3dd487d94c70f6a007b0397/966b6233e5404ebe80513ae082131132.html).
    -   SAP IBP: [Protect Against Clickjacking](https://help.sap.com/viewer/0292066056f642f1a0f6d9135e39abaf/latest/en-US/3d1ea8b1a0e145bb851d36d0da376e17.html)
    -   SAP BTP ABAP environment: [Protect Against Clickjacking](https://help.sap.com/docs/BTP/10fd1742ea914256abedb34bf15bd069/3d1ea8b1a0e145bb851d36d0da376e17.html?version=Cloud)




<a name="loioae475bf4dd944a70b864751c93e6bc5c__section_enb_xcc_dzb"/>

## Configuration Steps

> ### Note:  
> Please take into account that if you need to open a ticket in step 6, processing the ticket can take up to four weeks.


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



Create a custom domain for:

-   SAP Build Work Zone, advanced edition

-   Digital Workplace Service \(DWS\)




</td>
<td valign="top">

You create a custom domain for your subaccount in the Custom Domain Manager.

For more information, see the Custom Domain Manager documentation: [Manage Reserved and Custom Domains.](https://help.sap.com/docs/CUSTOM_DOMAINS/6f35a23466ee4df0b19085c9c52f9c29/25ec7eaf439341e7bf52a280d3797c6e.html)

</td>
</tr>
<tr>
<td valign="top">

3

</td>
<td valign="top">

Create a server certificate using the Custom Domain Manager.

</td>
<td valign="top">

Make sure you have configured Transport Layer Security \(TLS\) and create a server certificate for your custom domains from a trusted certificate authority.

For more information, see the Custom Domain Manager documentation: [Manage TLS Configurations](https://help.sap.com/docs/custom-domain/custom-domain-manager/manage-tls-configurations?&version=Cloud) and [Manage Server Certificates](https://help.sap.com/docs/CUSTOM_DOMAINS/6f35a23466ee4df0b19085c9c52f9c29/1c4cbe695bed435f80a748a143a8351e.html).

</td>
</tr>
<tr>
<td valign="top">

4

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

5

</td>
<td valign="top">

Create a SaaS route for the mapping between your custom domain and the URL of your SAP Build Work Zone, advanced edition subscription.

</td>
<td valign="top">

For more information, see [Manage Saas Routes](https://help.sap.com/docs/CUSTOM_DOMAINS/6f35a23466ee4df0b19085c9c52f9c29/7ad1e85b1cc54366b98c69164731a54d.html).

In the procedure section of this topic, step **e**, you must manually edit the default route of your custom domain \(that you created in **step 2**\) above, and replace it with the subscription URL of SAP Build Work Zone, advanced edition .

</td>
</tr>
<tr>
<td valign="top">

6

</td>
<td valign="top">

Configure the redirect URI.

</td>
<td valign="top">

Open a ticket with component EP-WZ-DMN, and provide the following information:

-   Subaccount ID

-   Custom domain name

-   URL of the default site

-   Data center - for example, `CF-EU10`


> ### Note:  
> Please take into account that processing this ticket can take up to four weeks.



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

You can do this in the *Subaccount Settings* screen, under the *Custom Domains* tab.

For more information, see [Subaccount Settings](subaccount-settings-2d651c7.md).

</td>
</tr>
<tr>
<td valign="top">



</td>
<td valign="top">

Rerun the onboarding configurator with the custom domain details.

For more information, see [Rerunning the Configurator](rerunning-the-configurator-872b96a.md).

</td>
<td valign="top">

For new tenants - rerun the onboarding to SAP Build Work Zone, advanced edition configurator with the custom domain details \(previously you used the default domain\).

For tenants that were upgraded for SAP Jam, raise a support ticket requesting to update the upgraded tenant to the custom domain, and then rerun the configurator according to the “existing SAP Jam tenant” option.

</td>
</tr>
</table>

