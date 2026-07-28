<!-- loioddb655ae45e44d499f2fa0ce503a46d9 -->

# Manual Integration of Apps

Learn how to integrate apps manually.



<a name="loioddb655ae45e44d499f2fa0ce503a46d9__section_s3j_ndp_11c"/>

## Introduction

In this flow, you create local apps by configuring them in the App editor in the*Content Manager* and adding them individually to your subaccount. These apps do not originate from content providers.



<a name="loioddb655ae45e44d499f2fa0ce503a46d9__section_b4r_5n4_sjb"/>

## App Types

The following app types are supported. Note that these apps may include different UI technologies.


<table>
<tr>
<th valign="top">

App Type

</th>
<th valign="top">

Description

</th>
<th valign="top">

Supported UI App Technology

</th>
</tr>
<tr>
<td valign="top">

SAP S/4HANA apps

</td>
<td valign="top">

Apps deployed on SAP S/4HANA on premise.

</td>
<td valign="top">

-   SAPUI5 apps

-   SAP GUI for HTML apps

-   Web Dynpro ABAP apps

-   WebClient UI apps




</td>
</tr>
<tr>
<td valign="top">

Cloud apps

</td>
<td valign="top">

Apps deployed on SAP BTP, Cloud Foundry environment or SAP BTP, ABAP environment.

</td>
<td valign="top">

SAPUI5 apps

</td>
</tr>
<tr>
<td valign="top">

SAP SuccessFactors deep links

</td>
<td valign="top">

A deep link is a hyperlink that links directly to a specific page in the SAP SuccessFactors system, rather than the start page.

</td>
<td valign="top">

SAPUI5 apps

</td>
</tr>
</table>



<a name="loioddb655ae45e44d499f2fa0ce503a46d9__section_kpm_drw_q3b"/>

## How to manually integrate the different app types

The following table describes the high-level procedure of manually integrating the different app types in the SAP Build Work Zone, advanced edition.


<table>
<tr>
<th valign="top">

Step

</th>
<th valign="top">

SAP S/4HANA Apps

</th>
<th valign="top">

Cloud Apps

</th>
<th valign="top">

SAP SuccessFactors Deep Links

</th>
</tr>
<tr>
<td valign="top">

0. Prerequisite

To run apps in an iFrame, you need to configure an allowlist.

In this way you define secure applications by adding trusted hosts to the protection allowlist.

</td>
<td valign="top">

For more information, see [Using an Allowlist for Clickjacking Framing Protection](https://help.sap.com/viewer/864321b9b3dd487d94c70f6a007b0397/7.51.8/en-US/966b6233e5404ebe80513ae082131132.html) 

</td>
<td valign="top">

For more information, see

-   SAP S/4HANA Cloud: [Maintain Protection Allowlists](https://help.sap.com/viewer/55a7cb346519450cb9e6d21c1ecd6ec1/latest/en-US/81aed02afbdb41379fe0eb4b23f7756a.html).
-   HTML5 apps: [Application Router Configuration](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/c19f165084d742e096c5d1625cecd2d4.html)
-   For SAP BTP ABAP Environment Apps: [Maintain Protection Allowlists](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/81aed02afbdb41379fe0eb4b23f7756a.html)



</td>
<td valign="top">

Not applicable.

</td>
</tr>
<tr>
<td valign="top">

1. Create a destination.

</td>
<td valign="top">

[Direct Access to On-Premise Apps](direct-access-to-on-premise-apps-0743653.md) or [Tunneled Access to On-Premise Apps](tunneled-access-to-on-premise-apps-f41f67f.md)

When the back-end system defined in the destination has aliases, it is also necessary to [Map Back-End System Aliases to Runtime Destinations](map-back-end-system-aliases-to-runtime-destinations-0a7f9ac.md).

</td>
<td valign="top">

[Direct Access to Cloud Apps](direct-access-to-cloud-apps-b695a24.md)

> ### Note:  
> If you want to add a dynamic app launcher to your SAPUI5 app deployed to the SAP BTP ABAP environment, you need to create another HTTP destination with authentication type `OAuth2UserTokenExchange`.



</td>
<td valign="top">

For more information, see [Direct Access to SAP SuccessFactors Deep Links](direct-access-to-sap-successfactors-deep-links-e62af55.md) 

</td>
</tr>
<tr>
<td valign="top">

2. Configure an app.

</td>
<td valign="top">

Configure an app manually. For general information, see [Configure Apps](configure-apps-4ba745b.md).

For app-specific information, see:

-   [SAPUI5 Apps](sapui5-apps-d430ae7.md)

-   [SAP GUI for HTML Apps](sap-gui-for-html-apps-e2e52a5.md)

-   [Web Dynpro ABAP Apps](web-dynpro-abap-apps-35a2b71.md)

-   [WebClient UI Apps](webclient-ui-apps-7255021.md)




</td>
<td valign="top">

Configure an app manually. For general information, see [Configure Apps](configure-apps-4ba745b.md).

For SAPUI5 app-specific information, see [SAPUI5 Apps](sapui5-apps-d430ae7.md).

> ### Note:  
> The information provided by the SAP Fiori apps reference library for SAP S/4HANA apps regarding the SAPUI5 component name, semantic object, and semantic action of SAP-provided apps, also applies to ABAP apps. See SAP Fiori Apps Reference Library.



</td>
<td valign="top">

For general information, see [Configure Apps](configure-apps-4ba745b.md).

For app-specific information, see [App Configuration Properties for SAP SuccessFactors Deep Links](app-configuration-properties-for-sap-successfactors-deep-links-1ed7861.md).

</td>
</tr>
<tr>
<td valign="top">

3. Create a page and assign your app to it. Then create a space and assign the page to the space to see the app in the site.

> ### Note:  
> Groups view mode is still supported if you're not using spaces and pages.



</td>
<td valign="top" colspan="3">

[Assignment of Spaces and Pages](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/spaces-and-pages)

[Assign Apps to Groups](assign-apps-to-groups-6f60d52.md)

</td>
</tr>
<tr>
<td valign="top">

4. Create a catalog and assign your app to it, to see the app in the App Finder at runtime. \(Optional\)

</td>
<td valign="top" colspan="3">

[Assign Apps to a Catalog \(Optional\)](assign-apps-to-a-catalog-optional-f63e4b5.md)

For more information, see [App Finder](https://help.sap.com/viewer/3d99fdeadde04524bdd33d35f1e13777/Cloud/en-US/48a5dbb0308b47d8969485845d5966ae.html).

</td>
</tr>
<tr>
<td valign="top">

5. Create a role and assign your app to it to enable users with the role to access the app.

</td>
<td valign="top" colspan="3">

[Assign Content to a Role](assign-content-to-a-role-baeaf6e.md) 

</td>
</tr>
<tr>
<td valign="top">

6. Assign the role to the site.

</td>
<td valign="top" colspan="3">

[Assign Roles to Your Site](assign-roles-to-your-site-7afe670.md)

</td>
</tr>
<tr>
<td valign="top">

7. Assign role to user

</td>
<td valign="top" colspan="3">

[Assign Users to a Role](assign-users-to-a-role-77f09c0.md)

</td>
</tr>
</table>

**Related Information**  


[Supported Platforms/Products](supported-platforms-products-86bacc3.md "Supported platforms/products for SAP Build Work Zone, advanced edition.")

[Supported Browsers and Languages](supported-browsers-and-languages-99a0a18.md "")

[Restrictions](restrictions-b259464.md "This topic describes the current restrictions that you should be aware of when working with SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone.")

