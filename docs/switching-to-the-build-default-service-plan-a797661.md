<!-- loioa797661bae7a432c9a45e4f19b866d25 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Switching to the build-default Service Plan

To take advantage of the SAP Build commercial model, you must subscribe to SAP Build Work Zone with the `build-default` service plan. The instructions below will guide you how to update the service plan.



## Overview

You can update SAP Build Work Zone, advanced edition from the `standard` plan or the `advanced` plan to the `build-default` service plan. Note that the `build-default` service plan is not available for SAP SuccessFactors Work Zone.

When switching to the `build-default` service plan, you can reuse all artifacts and configurations that were already created. However, the metering metrics will be changed according to the SAP Build commercial model.

For more information about the SAP Build commercial model, see [Service Plans and Metering \(SAP Build\)](https://help.sap.com/docs/build-service/build-service-guide/service-plans-and-metering?version=Cloud) and [SAP Build pricing information in the Discovery Center](https://discovery-center.cloud.sap/serviceCatalog/sap-build?region=all&tab=service_plan).



## Prerequisites

-   You're using SAP Cloud Identity Services - Identity Authentication. For more information, see [SAP Cloud Identity Services - Identity Authentication](https://help.sap.com/docs/identity-authentication).
-   You've created the Global User IDs. For more information, see [Global User ID in Integration Scenarios](https://help.sap.com/docs/cloud-identity/system-integration-guide/global-user-id-in-integration-scenarios?version=Cloud).



## Procedure

To update from one service plan to another, perform the following steps:

> ### Note:  
> It is not possible to switch back from the `build-default` service plan.

1.  Open your global account in the SAP BTP cockpit.

2.  Navigate to your subaccount.

3.  Navigate to *Services* \> *Instances and Subscriptions*.

4.  Under the *Subscriptions* tab, search for the SAP Build Work Zone, advanced edition application subscribed to the `standard` plan or the `advanced` plan.

5.  In the last column, from the <span class="SAP-icons-V5"></span> \(Actions\) menu, select *Update*.

6.  In the *Update Subscription* dialog box, change the *Plan* to `build-default`.

7.  Click *Update Subscriptions*.




## Results

You have updated the existing plan to `build-default` plan, which automatically migrates your data to the `build-default` plan.

> ### Note:  
> When switching from one plan to another, we recommend waiting for 30 minutes for the properties of the new plan to take effect.

**Related Information**  


[Service Plans and Metering](service-plans-and-metering-0b00752.md "This page explains the relationship between the service plans in the SAP Discovery Center and those in the SAP BTP cockpit, and provides information to help you understand how SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone are billed.")

[About SAP Build](about-sap-build-3d61413.md "SAP Build Work Zone is one of the components of SAP Build.")

