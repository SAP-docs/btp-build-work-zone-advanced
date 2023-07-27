<!-- loioa4c772894ec74602ab4f0810ad48993a -->

# Integration of HTML5 applications from multiple SAP BTP subaccounts

Complete the following steps to integrate HTML5 apps from multiple SAP BTP subaccounts.



<a name="loioa4c772894ec74602ab4f0810ad48993a__section_bvy_2rz_zxb"/>

## Procedure

To be able to integrate apps across different subaccount, complete the following steps.

1.  Manually integrate HTML5 apps from another subaccount.
    1.  Configure trusted domains for SAP Authorization and Trust Management service, to prevent clickjacking or overlay attacks. For more information, see [Configure Trusted Domains for SAP Authorization and Trust Management Service \[Feature Set B\]](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/c5e997235f724ec686dc5dc101a1ccfb.html).
    2.  Configure trusted domains for Identity Authentication to be able to use overlays in your applications. For more information, see [Configure Trusted Domains](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/08fa1fe816704d99a6bcab245158ebca.html).
    3.  Add HTTP security headers to your site to protect against clickjacking, cross-site scripting, XSS, and other attacks. For more information, see [Using Security Headers](using-security-headers-da26650.md).

2.  Propagate the identity of a user between applications to consume APIs from applications in different subaccounts. For example when creating custom UI cards or dynamic KPI tiles. For more information, see [User Propagation between Cloud Foundry Applications](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/8ebf60c82a8e4cfc904f441c0c0acd6b.html).

