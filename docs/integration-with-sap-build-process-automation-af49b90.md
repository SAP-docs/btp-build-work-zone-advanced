<!-- loioaf49b904f1a54cb3a68be048b8ac26a1 -->

# Integration with SAP Build Process Automation

Complete the following steps to be able to use SAP Build Process Automation across different subaccounts.



## Prerequisites

SAP Build Process Automation is available on the following data centers: [Discovery Center - SAP Build Process Automation](https://discovery-center.cloud.sap/serviceCatalog/sap-build-process-automation?region=all).

If SAP Build Process Automation is not available in the same region as your the subaccount were you use SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone, complete the following steps to be able to use SAP Build Process Automation in a cross-region manner.



<a name="loioaf49b904f1a54cb3a68be048b8ac26a1__section_bvy_2rz_zxb"/>

## Procedure

1.  Manually integrate HTML5 apps from SAP Build Process Automation.
    1.  Configure trusted domains for SAP Authorization and Trust Management service, to prevent clickjacking or overlay attacks. For more information, see [Configure Trusted Domains for SAP Authorization and Trust Management Service \[Feature Set B\]](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/c5e997235f724ec686dc5dc101a1ccfb.html).
    2.  Configure trusted domains for Identity Authentication to be able to use overlays in your applications. For more information, see [Configure Trusted Domains](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/08fa1fe816704d99a6bcab245158ebca.html).
    3.  Add HTTP security headers to your site to protect against clickjacking, cross-site scripting, XSS, and other attacks. For more information, see [Using Security Headers](using-security-headers-da26650.md).

2.  Establish trust between subaccounts to consume SAP Build Process Automation APIs in your subaccount where you use SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone. For example when creating custom UI cards or dynamic KPI tiles. For more information, see [User Propagation between Cloud Foundry Applications](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/8ebf60c82a8e4cfc904f441c0c0acd6b.html).
3.  Use SAP Task Center to show SAP Build Process Automation approvals \(instead of My Inbox\). For more information, see [Work with SAP Build Process Automation Tasks from a Remote Subaccount](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/1d3e69d3bcd044b892e7c6e145de19e5.html).

    > ### Note:  
    > It is not possible to fully consume SAP Build Process Automation across different subaccounts in SAP Task Center. More specifically, launching of the SAP Build Process Automation UIs within SAP Task Center doesn’t work if SAP Build Work Zone, advanced edition is not configured on the same subaccount as the SAP Build Automation Process.


