<!-- loio713f2f8f22cd4952856529759ecd368f -->

# Launchpad Modules Content Providers

An overview of the launchpad modules content providers.



<a name="loio713f2f8f22cd4952856529759ecd368f__section_mxk_vnb_b1c"/>

## Introduction

Using SAP Cloud Portal service, developers can create apps that are part of a business flow solution. For this flow, they can also include a launchpad module to make it easier to access the apps in one place. They can then choose to expose this solution as a content provider.

Once the solution is deployed to the subaccount, administrators can subscribe to it and then access these apps from a dedicated content provider in the *Channel Manager*.

> ### Note:  
> You can't federate such applications using the *HTML5 Apps* content provider.



<a name="loio713f2f8f22cd4952856529759ecd368f__section_lkx_k1l_mjb"/>

## Prerequisites

To make a launchpad module visible in the *Channel Manager*, you need to make sure the following is in place:

-   The launchpad module is exposed as a content provider. For more information, see [Expose Your App as a Content Provider](https://help.sap.com/docs/cloud-portal-service/sap-cloud-portal-service-on-cloud-foundry/expose-your-app-as-content-provider).

-   In the SAP BTP cockpit, you are subscribed to one or more of the following types of solutions that are based on the launchpad module.

    > ### Note:  
    > To create the subscription, open the *Service Marketplace* of your subaccount, click the launchpad module tile, and click *Create* to create a subscription. Use the *default* application when subscribing.

    -   A custom solution developed in the SAP Cloud Portal service and deployed to your SAP Build Work Zone, advanced edition subaccount on SAP BTP.

        For more information, see [Developing a Launchpad Module](https://help.sap.com/docs/Portal_Service/ad4b9f0b14b0458cad9bd27bf435637d/4dec640b19da4245be64383be24be173.html)

    -   A solution provided by SAP, such as Real Estate or Excise Duty.


-   The subscription must be in the **same subaccount** as the SAP Build Work Zone, advanced edition.


> ### Note:  
> -   In the launchpad, apps that open in-place \(not in a new tab or new window\) run within an iFrame. To enable SSO \(single sign on\) and SLO \(single log out\), without compromising browser security by allowing third-party cookies, you must use a common super domain for all integrated parties – the launchpad, the IdP, and the integrated applications. A common super domain includes all subdomains belonging to the same second level domain. This approach supports SAP-hosted domains like `*.ondemand.com`.
> 
> -   Federated launchpad modules that were configured with a custom domain, will not open successfully in the default domain of the runtime site, but only in the custom domain of the runtime site.
> 
> -   Launchpad modules that are using a local approuter and not a SAP-managed approuter might be blocked when accessed from an iframe due to the third-party cookies restrictions imposed by many browser manufacturers. To prevent this from happening, the launchpad module approuter must include cookies definitions in its environment variable. This step is done when configuring the launchpad module as a content provider. For more information, see [Expose Your App as a Content Provider](https://help.sap.com/docs/Portal_Service/ad4b9f0b14b0458cad9bd27bf435637d/8a25fddb747f4ba992969049de96f836.html).

