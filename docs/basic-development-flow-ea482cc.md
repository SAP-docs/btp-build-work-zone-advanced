<!-- loioea482cc0edda43438d0b255424e2a10f -->

# Basic Development Flow

After subscribing to SAP Build Work Zone, advanced edition, you receive a single point-of-entry for your applications running on SAP BTP. You develop and build HTML5 Applications in an IDE, and deploy them to the HTML5 Application Repository, so that you can access and launch them during runtime.



<a name="loioea482cc0edda43438d0b255424e2a10f__prereq_ix2_4yv_jlb"/>

## Prerequisites

-   You have a subscription toSAP Build Work Zone, advanced edition.

    > ### Note:  
    > As a result of the subscription, an empty *HTML5 Apps* content provider is created in the Channel Manager of SAP Build Work Zone, advanced edition.

-   You need to be assigned as an administrator of a subaccount. If this is not the case, you need to create a subaccount in your global account on SAP BTP, Cloud Foundry environment.

    To create a subaccount, your global account administrator can use the *Prepare an account for HTML5 application development* booster:

    1.  Log on to the SAP BTP cockpit and open your global account.

    2.  In the navigation menu of the SAP BTP cockpit, choose*Boosters*.

    3.  Choose the booster *Prepare an account for HTML5 application development*.

    4.  Choose *Start* and follow the steps in the booster.





<a name="loioea482cc0edda43438d0b255424e2a10f__context_pzc_ml4_5lb"/>

## Context

You can develop your applications with SAP Business Application Studio \(minimal configuration effort and all necessary tools up and running\) or your own IDE. If you choose your own IDE, you'll find instructions on creating and configuring the application configuration files.

Service plan *app-host* enables the SAP BTP Deploy service to upload the HTML5 applications' static content to the HTML5 Application Repository.

During runtime, static content is served from the repository to the browser. Using the application configuration files, the application supports authentication, authorization and access to backend applications.

> ### Note:  
> The development flow of URL apps is slightly different and not all steps are necessary. For more information, see [Create an HTML5 URL App](create-an-html5-url-app-48d579e.md)

> ### Note:  
> When developing the HTML5 applications, note that within a single subaccount, the IDs of the applications must be unique.



<a name="loioea482cc0edda43438d0b255424e2a10f__steps_zrp_km4_5lb"/>

## Procedure

1.  Set up your development environment.

    1.  Create a development project.

    2.  Set up the mandatory configuration files \(generated automatically by SAP Business Application Studio\).


2.  Develop the HTML5 application content. Make sure to include translation files \(i18n files\) for the locales you use at runtime.

3.  **Optional:** Integrate business services.

4.  Configure the destinations to connect the application to the backend systems.

5.  Expose your application to SAP Build Work Zone, advanced edition.

6.  Build and deploy the application to SAP BTP.


**Related Information**  


[Set Up Your Development Environment](set-up-your-development-environment-3db887a.md "You need an IDE (integrated development environment) to develop your applications.")

[Configure Destinations \(HTML5\)](configure-destinations-html5-fab4035.md "A destination defines the back-end connectivity. In its simplest form, a destination is a URL to which requests are forwarded. There must be a destination for every single app (microservice) that is a part of the business application.")

[Integrate Business Services](integrate-business-services-1b80373.md "")

[Expose HTML5 Applications in SAP Build Work Zone, advanced edition](expose-html5-applications-in-sap-build-work-zone-advanced-edition-3a0e6d6.md "To expose an HTML5 Application in SAP Build Work Zone, advanced edition , you need to add some information to the manifest.json file of the application.")

[Build and Deploy Content](build-and-deploy-content-4394315.md "Build and deploy content to the HTML5 Application Repository using the Generic Application Content Deployer (GACD).")

