<!-- loio439431592b8e465c834e64741746e013 -->

# Build and Deploy Content

Build and deploy content to the HTML5 Application Repository using the Generic Application Content Deployer \(GACD\).



<a name="loio439431592b8e465c834e64741746e013__prereq_k5h_2st_wlb"/>

## Prerequisites

-   The MultiApps plug-in for the `cf CLI` to deploy MTAs is installed locally, see [Install the MultiApps Plug-in in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/27f3af39c2584d4ea8c15ba8c282fd75.html).

-   The Cloud MTA Build Tool \(MBT\) is installed, see [Cloud MTA Build Tool: Download](https://sap.github.io/cloud-mta-build-tool/download/)




<a name="loio439431592b8e465c834e64741746e013__context_bqj_b4j_43b"/>

## Context

You can deploy your content to the HTML5 Application Repository using the GACD \(Generic Application Content Deployer\) module. The GACD module has the module type `com.sap.application.content`. This module type enables the deploy plug-in generic application content deploy support. It means that when a module is processed in the cf deploy flow, the deploy service locates the service resource that is required as a target for the deploy and deploys the corresponding `content.zip` file.

> ### Note:  
> The HTML5 application repository service does not provide the technical capabilities to support the collection, processing, and storage of personal data. The file names used for deploying the HTML5 applications are not intended for personal data.

You use a service instance of the app-host service plan to deploy your applications to the HTML5 Application Repository.

> ### Note:  
> If you delete an app-host service instance, the apps that are deployed with this app-host service instance are deleted from the HTML5 Application Repository.

> ### Note:  
> Delta deployments are not supported. If you deploy new application content using an existing app-host service instance, the new application content will completely replace the old application content that had been previously deployed with this service instance in the HTML5 Application Repository.
> 
> For example, if you have already deployed the applications a, b, and c with the instance 123 and now want to deploy the new applications d and e, you can do one of the following to avoid overwriting the applications a, b, and c:
> 
> -   Redeploy instance 123 with applications a, b, c, d, and e \(with the new and the old applications\).
> 
> -   Create a new instance 456 and use this instance to deploy the applications d and e.



<a name="loio439431592b8e465c834e64741746e013__steps_nxt_t4j_43b"/>

## Procedure

1.  Build your project to create a Multi-Target Application Resource \(`mtar`\) file.

    To build your project with the MTA Build Tool \(MBT\), run the following command:

    ```
    mbt build
    ```

    For more information on MBT build options, see: [How to build an MTA archive from the project sources](https://sap.github.io/cloud-mta-build-tool/usage/#how-to-build-an-mta-archive-from-the-project-sources)

2.  Deploy your project to SAP BTP

    Run the following command:

    ```
    cf deploy <path-to-mtar-file>
    ```

    For example: `cf deploy mta_archives/myapp_0.0.1.mtar`

3.  Go to SAP BTP cockpit to check the deployed content.


**Related Information**  


[Download and Install the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/4ef907afb1254e8286882a2bdef0edf4.html)

