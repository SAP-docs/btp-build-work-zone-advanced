<!-- loioac16ecafb863488eb0f7c9c6056e6626 -->

# Transporting Content

Administrators can transport content between different environments and different services. You can also transport certain site content items between subaccounts and data centers.



<a name="loioac16ecafb863488eb0f7c9c6056e6626__section_lf2_b5s_21c"/>

## Overview

There are times when you want to transport content between sites. The transport process is straight forward. In general, you export the content from the source system and import the exported file back into the target system.

**Use Cases:**

-   You can transport content between environments – for example, Dev, Test, and Production environments.

-   You can transport content between services – for example, between the SAP Cloud Portal service, SAP Build Work Zone, standard edition, SAP Build Work Zone, advanced edition, and SAP SuccessFactors Work Zone services.

-   You can also transport various types of content items from one subaccount to another subaccount - for example, home pages, workspaces, and workspace templates.




<a name="loioac16ecafb863488eb0f7c9c6056e6626__section_tk1_lt4_5qb"/>

## Transport Options

The transport of content can be done in one of the following ways:

-   Via the SAP Cloud Transport Management service.

-   Manually by exporting \(downloading\) content from the source environment and then importing \(uploading\) this content into the target environment.




<a name="loioac16ecafb863488eb0f7c9c6056e6626__section_qgm_x2g_rrb"/>

## Transported Content

You can export selected content items in the Content Manager.

> ### Note:  
> Transporting HTML5 apps from local providers or manual integration is possible only if you deploy the same HTML5 repo to both source and target subaccounts. The name and ID of the HTML5 repo and its apps must be identical on both subaccounts.



<a name="loioac16ecafb863488eb0f7c9c6056e6626__section_hxw_crz_x5b"/>

## Best Practices

It is recommended to create at least three subaccounts to set up a staged development environment, including one subaccount each for development, testing, and production.

For more information, see [**Using Subaccounts to Create a Staged Development Environment**](https://help.sap.com/docs/BTP/df50977d8bfa4c9a8a063ddb37113c43/74eb32ef49804e6e8107338c4ed44d49.html)

**Related Information**  


[Before Transporting Content - Important Rules and Guidelines](before-transporting-content-important-rules-and-guidelines-4d3f192.md "The rules and guidelines regarding transporting content and the related content that is also exported when exporting content items.")

[Transporting Content via SAP Cloud Transport Management Service](transporting-content-via-sap-cloud-transport-management-service-3d644a1.md "An administrator can use the SAP Cloud Transport Management service to transport content from one system to another. This includes transporting content between landscapes, such as from DEV to TEST, or between data centers.")

[Transporting Content Manually](transporting-content-manually-b2a3a47.md "Administrators can transport content between Dev, Test, and Production environments.")

[Tracking the Progress of Your Imports](tracking-the-progress-of-your-imports-0443a41.md "Track the progress of your imports in the Import Monitor.")

[Transporting Workspace Content Items](transporting-workspace-content-items-0a5c641.md "You can transport content items such as home pages, workspaces, workspace content, and workspace templates.")

[Transporting Content Between Services](transporting-content-between-services-72ea185.md "The content that is transported from SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone when they are the source system, and the content that is transported to SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone when they are the target system.")

