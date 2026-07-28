<!-- loio0e1c52b572df4fb593f781b5694994dc -->

# What is the HTML5 Application Repository?

The HTML5 Application Repository centrally stores the applications' static content on the SAP BTP.

HTML5 Applications consist of static content such as HTML, CSS, JavaScript, and other files, that run on a browser. For more information, see [Basic Template](https://openui5.hana.ondemand.com/#/topic/7a4d93c0b0bb439b9d889ffc5b02eac9) and [openui5-basic-template-app](https://github.com/SAP/openui5-basic-template-app).

In addition, each HTML5 application contains a configuration file, which is used during runtime. It defines the authentication method, the required authorizations, and routing configurations to backend systems. For more information see [Configure Application Routing \(xs-app.json\)](configure-application-routing-xs-app-json-a0c76f4.md).

The HTML5 Application Repository allows application developers to manage the lifecycle of their applications. In runtime, the static content is served in a secure and efficient manner.



<a name="loio0e1c52b572df4fb593f781b5694994dc__section_ocr_rl1_1cb"/>

## Features



### Zero Down-Time Enablement

-   The HTML5 Applications are decoupled from the consuming application. Thus you can update the static content of HTML5 Applications without causing downtimes to running sessions.




### Versioning and Authorization

-   Exploration of application content by version.

-   Access control that is based on private or public authorization.

    When the application is public, the service enables sharing this content with consuming applications from different subaccounts.




### Availability and Performance

-   During runtime, the application content is cached and optimized to provide high performance with minimal network load.

-   The service provides several instances for a runtime to serve a high load of application requests.




<a name="loio0e1c52b572df4fb593f781b5694994dc__section_rsn_fzt_5lb"/>

## Service Plan *app-host*

Use this service plan to deploy HTML5 applications to the repository. For more information, see [Build and Deploy Content](build-and-deploy-content-4394315.md).



<a name="loio0e1c52b572df4fb593f781b5694994dc__section_khv_jv5_5lb"/>

## Metering

The HTML5 Application Repository meters and reports the actual storage size of each application that is deployed to the repository.

In the *Usage Analytics* view of the SAP BTP cockpit, the admin can see the largest total storage size, in megabytes, of all the applications in the repository during the selected period of time.



<a name="loio0e1c52b572df4fb593f781b5694994dc__section_jjv_12v_1cb"/>

## Restrictions

-   The size of an application deployed to the repository is limited to 100 MB per service instance of the *app-host* service plan.

-   Since the applications stored in HTML5 Application Repository can be shared, we recommend that you do not add personal data to them.




<a name="loio0e1c52b572df4fb593f781b5694994dc__section_mqn_54b_kdb"/>

## See Also

If you want to learn more about services in the SAP BTP Cloud Foundry environment, see [Using Services in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f22029f0e7404448ab65f71ff5b0804d.html).

