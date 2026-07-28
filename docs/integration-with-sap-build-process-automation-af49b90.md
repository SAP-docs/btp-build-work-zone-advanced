<!-- loioaf49b904f1a54cb3a68be048b8ac26a1 -->

# Integration with SAP Build Process Automation

Complete the following steps in order to use SAP Build Process Automation across different subaccounts.



<a name="loioaf49b904f1a54cb3a68be048b8ac26a1__section_uhj_wys_2dc"/>

## Consuming Apps from SAP Build Process Automation



### Prerequisites

SAP Build Process Automation is available on the following data centers: [Discovery Center - SAP Build Process Automation](https://discovery-center.cloud.sap/serviceCatalog/sap-build-process-automation?region=all).

If SAP Build Process Automation is not available in the same region as the subaccount where you use SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone, complete the following steps to use SAP Build Process Automation in a cross-region manner.



### Procedure

1.  Manually integrate HTML5 apps from SAP Build Process Automation.
    1.  Configure trusted domains for the SAP Authorization and Trust Management service, to prevent clickjacking or overlay attacks. For more information, see [Configure Trusted Domains for Multi-environment Subaccounts](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/c5e997235f724ec686dc5dc101a1ccfb.html).
    2.  Configure trusted domains for Identity Authentication to be able to use overlays in your applications. For more information, see [Configure Trusted Domains](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/08fa1fe816704d99a6bcab245158ebca.html).
    3.  Add HTTP security headers to your site to protect against clickjacking, cross-site scripting, XSS, and other attacks. For more information, see [Using Security Headers](using-security-headers-da26650.md).

2.  Establish trust between subaccounts to consume SAP Build Process Automation APIs in your subaccount where you use SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone. For example when creating custom UI cards or dynamic KPI tiles. For more information, see [User Propagation between Cloud Foundry Applications](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/8ebf60c82a8e4cfc904f441c0c0acd6b.html).
3.  Use SAP Task Center to show SAP Build Process Automation approvals \(instead of My Inbox\). For more information, see [Work with SAP Build Process Automation Tasks from a Remote Subaccount](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/1d3e69d3bcd044b892e7c6e145de19e5.html).

Cross-subaccount consumption of SAP Build Process Automation \(and related apps\) in SAP Build Work Zone, advanced edition is supported but requires manual setup \(listed above\).



<a name="loioaf49b904f1a54cb3a68be048b8ac26a1__section_bvy_2rz_zxb"/>

## Consuming a Guided Process from SAP Build Process Automation

Before users can choose a guided process when creating a wizard in a workpage, you need to set up SAP Build Process Automation as follows:

-   The integration steps with SAP Build Process Automation are complete. This is done during the onboarding process to SAP Build Work Zone, advanced edition. For more information, see [Run the Booster](run-the-booster-4679f1c.md).

-   Make sure that you're assigned to the `ProcessAutomationParticipant` role collection \(which is part of the booster\).

-   Make sure you have the *Execute* privilege in the shared environment where the guided process is deployed in order to launch forms, processes, and visibility scenarios. For more information, see [Share an Environment](https://help.sap.com/docs/build-process-automation/sap-build-process-automation/share-environment?version=Cloud).

-   To trigger and consume the guided process from SAP Build Process Automation directly in SAP Build Work Zone, advanced edition, the destination must include the `HTML5.DynamicDestination=true` property to the`sap_process_automation_service_user_access` destination. For more information, see [Integrate and Connect With Other Services](https://help.sap.com/docs/build-process-automation/sap-build-process-automation-ship-internal/integrate-and-connect-with-other-services?state=DRAFT) - see the last row in the table, *Guided Process*.

    > ### Caution:  
    > Adding an `HTML5.DynamicDestination` property and setting it to true, enables dynamic access to the destination to any logged-in user.
    > 
    > Therefore before adding this property to the destination, make sure that the underlying API is not public and requires the correct user credentials.


For more information about how a user adds the guided process wizard, see [How to Create a Wizard](how-to-create-a-wizard-061fb6b.md).

