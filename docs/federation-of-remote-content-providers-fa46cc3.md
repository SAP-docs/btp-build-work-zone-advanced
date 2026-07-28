<!-- loiofa46cc3ffdb048e9bbadafb2429480d9 -->

# Federation of Remote Content Providers

Learn how to integrate content from remote content providers.



<a name="loiofa46cc3ffdb048e9bbadafb2429480d9__section_pfdb_wml_xnc_cnb"/>

## Overview

A remote content provider is a solution that exposes content that can be integrated in SAP Build Work Zone, advanced edition.

The content provider is considered remote, as it requires its administrator to expose the desired content. In addition, the administrator also needs to configure a design-time destination that defines the location from which to fetch the design-time content that was exposed, and a runtime destination that defines the location from which to obtain the resources needed to run the federated apps in runtime..

> ### Note:  
> -   All content that is exposed on the provider's side is created on SAP Business Technology Platform at the time the content provider is created.
> -   For every content provider, a unique set of content is created, even if different content providers are pointing to the same remote system.



### Supported Content Providers

**Cloud Solutions**

-   SAP S/4HANA Cloud

-   SAP BTP ABAP environment

-   SAP Integrated Business Planning for Chain Supply \(SAP IBP\)


**On-Premise Solutions**

-   SAP S/4HANA \(on premise\)

-   SAP Business Suite

-   SAP Enterprise Portal


> ### Note:  
> In the Content Channel screen you might find content providers that were created automatically. These content providers are there to support different integration flows and can’t be changed or deleted. If the content from an automatically-created content provider contains definitions for app visualization \(tiles or cards\), the content can be added to a site. To find out whether the content contains visualization definitions, please contact the provider.

Each remote content provider uses a tool for exposing its content in a format that is suitable for integration in SAP Build Work Zone, advanced edition.

> ### Note:  
> The content exposure tool in the SAP Fiori Launchpad in ABAP platform provides two operation modes, referred to as version one \(V1\) and version two \(V2\), with some differences between them. For example, when using V2, all applications open in a new window. Therefore, although technically possible, we do not recommend using both versions in the same site because of the different user experience between the versions. For more information, see SAP Note [3345119](https://me.sap.com/notes/3345119).
> 
> Modifying the exposure version of an existing content provider in the Channel Manager is not supported. For instance, switching a design-time destination used for V1 to one used for V2 is not supported. If not already available, you need to create a new content provider specifically for V2.
> 
> In addition, when using V2, after creating the content provider, it is necessary to map the alias `FLP_STANDALONE` to the default runtime destination. For more information, see the section about mapping aliases in the following topic: [Manage Content Providers \(On Premise\)](manage-content-providers-on-premise-021bc11.md).

The integration of the exposed content is done at the role level. All content items related to these roles, including apps, groups, and catalogs, are also integrated and are all visible in the runtime. In the Content Manager, however, it is possible to see only the roles and the list of apps assigned to each role.

> ### Note:  
> Composite and derived roles \(PFCG roles\) are supported in runtime, as of S/4HANA 2021 FPS01. These roles are not visible in the Content Manager. The Content Manager displays only single roles assigned directly to content.
> 
> A single role should not be assigned more than 10,000 related roles \(composite and derived roles\), to avoid an impact on performance.
> 
> -   For more information about composite and derived roles, see [**Creating Composite Roles**](https://help.sap.com/docs/SAP_NETWEAVER_740/c6e6d078ab99452db94ed7b3b7bbcccf/42271d24d86211d2961a0000e82de14a.html), [**Creating Derived Roles and Copying Authorizations**](https://help.sap.com/docs/SAP_NETWEAVER_700/129affcf6c531014b28cae6d2a9cf86f/1cc38028816c11d396bc0000e82de14a.html).
> -   For more information about derived and composite role provisioning, see [Exploring Role Assignments](exploring-role-assignments-7eed569.md).
> -   For more information about an issue with derived roles when using transaction /UI2/CDM3\_EXP\_SCOPE, see [3038646](https://me.sap.com/notes/3038646).

**Related Information**  


[Supported Platforms/Products](supported-platforms-products-86bacc3.md "Supported platforms/products for SAP Build Work Zone, advanced edition.")

[Content Providers - Cloud Solutions](content-providers-cloud-solutions-d92cf2f.md "An end-to-end process for integrating content from cloud solutions. This process is composed of a content exposure flow and a content consumption flow. Some steps might be slightly different between different content providers.")

[Content Providers - On-Premise Solutions](content-providers-on-premise-solutions-a12a002.md "An overview of the end-to-end process for integrating content from on-premise solutions.")

