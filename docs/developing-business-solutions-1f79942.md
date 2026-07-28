<!-- loio1f79942c867f4932ac7b1aa60fb3d04c -->

# Developing Business Solutions



## Starting Point - SAP BTP Developer Guide

The SAP BTP Developer’s Guide is the starting point for developing a business application on SAP BTP. It contains recommendations and best practices that give you an overview of what you should consider when working on development projects on SAP BTP. It also contains links to step-by-step instructions when required. For more information, see [SAP BTP Developer’s Guide](https://help.sap.com/docs/btp/btp-developers-guide/btp-developers-guide).

SAP BTP provides a multitenant functionality that allows application providers to own, deploy, and operate tenant-aware applications for multiple consumers, with reduced costs. For example, the application provider upgrades the application for all your consumers instead of performing each update individually, or share resources across multiple consumers. The application consumers launch the applications using consumer-specific URLs, and configure certain application features.

The following sections will explain how to create multitenant applications, AKA business solutions, and share it with consumers.



<a name="loio1f79942c867f4932ac7b1aa60fb3d04c__section_m2c_zfd_ncc"/>

## What Is a Business Solution?

A business solution is a complex SaaS application that consists of an MTA that typically contains UI modules, business logic, and a connection to a database. What makes a business solution more advanced compared to a standard HTML5 application, is that it contains a CDM file with the site design-time definitions. Upon deployment, the business solution site is created with the business content such as tiles, roles, spaces, and pages, which reduces the need for content configuration.

The business solution MTA is bound to a single SAP cloud service throughout the project. In this example, the defined cloud service is `managerproductcdm`. If the MTA includes multiple SAP cloud services, the deployment will fail.

```
 "sap.cloud": {
    "public": true,
    "service": "manageproductscdm"
  }
```



## Advantages of Developing a Business Solution

A business solution has the main advantages over an HTML5 app:

-   Supports cross-subaccount consumption.
-   Supports mutitenancy.
-   Auto-update - whenever a business solution provider makes changes to the solution, the changes are reflected on the consumers side with no need to redeployment.
-   No design-time configuration by admin. The business solution contains a CDM and optionally a site entity, and is ready to be consumed.



## Types of Business Solutions


<table>
<tr>
<td valign="top">

Scenario

</td>
<td valign="top">

Description

</td>
<td valign="top">

More information

</td>
</tr>
<tr>
<td valign="top">

HTML5 Business Solutions as Content Providers

</td>
<td valign="top">

-   A business solution that contains all CDM entities that are required for integration inSAP Build Work Zone - apps, roles, spaces and pages, and optionally also a site.
-   Supports multi tenancy and cross-subaccount consumption.
-   Automatically reflects any update made to the business solution with a simple channel refresh.
-   Requires subscription to SAP Build Work Zone and therefore can be consumed as a standalone site or within an existing site.
-   Can be locally deployed or consumed as a remote content provider.
-   The approuter is managed by



</td>
<td valign="top">

 

</td>
</tr>
</table>



## Overall Process

The overall process can be described as follows:

*HTML5 App Repository* \> *CDM Exposure Endpoint* \> *Content Federation* \> *Runtime Display*

The CDM exposure endpoint URL follows this pattern: `https://html5-apps-repo-rt.$(domain)/applications/cdm/$(sap.cloud.service)`, and the `sap.cloud.service` must match the value that is defined in the `manifest.json` or the app or card.



### Key Benefits

-   Automatic CDM conversion - application manifests are automatically converted to CDM \(business app\).
-   CDM creation - the system handles CDM business app entity creation automatically. Developers need to define roles, spaces and pages.
-   Unified deployment - a single MTA package contains regular SAPUI5 apps, component cards, declarative cards, and CDM.

