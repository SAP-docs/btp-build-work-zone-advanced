<!-- loioa4c772894ec74602ab4f0810ad48993a -->

# Integration of HTML5 Applications from Multiple Subaccounts

Required steps for integrating HTML5 apps from multiple SAP BTP subaccounts.



<a name="loioa4c772894ec74602ab4f0810ad48993a__section_bvy_2rz_zxb"/>

## Procedure

> ### Note:  
> This procedure is a relevant to the following development flow: [Developing HTML5 Applications \(Legacy Flow\)](developing-html5-applications-legacy-flow-c1b9d6f.md), and it serves as a workaround for consuming HTML5 applications across subaccounts.
> 
> The recommended way of consuming HTML5 application across subaccounts is developing HTML5 business solutions and consuming them as content providers. For more information, see [Developing Business Solutions](developing-business-solutions-1f79942.md).

To be able to integrate HTML5 apps across different subaccounts, complete the following steps.

1.  Configure the authentication settings across the subaccounts:
    1.  Configure trusted domains for SAP Authorization and Trust Management service, to prevent clickjacking or overlay attacks. For more information, see [Configure Trusted Domains for Multi-environment Subaccounts](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/c5e997235f724ec686dc5dc101a1ccfb.html).
    2.  Configure trusted domains for Identity Authentication to be able to use overlays in your applications. For more information, see [Configure Trusted Domains](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/08fa1fe816704d99a6bcab245158ebca.html).
    3.  Add HTTP security headers to your site to protect against clickjacking, cross-site scripting, XSS, and other attacks. For more information, see [Using Security Headers](using-security-headers-da26650.md).
    4.  Propagate the identity of a user between applications to consume APIs from applications in different subaccounts. For example when creating custom UI cards or dynamic KPI tiles. For more information, see [User Propagation between Cloud Foundry Applications](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/8ebf60c82a8e4cfc904f441c0c0acd6b.html).

2.  Manually add the apps to the site. For more information, see [Manual Integration of Apps](manual-integration-of-apps-ddb655a.md).

