<!-- loio7c9f1030955f491484435b2933aa7316 -->

# Integrating Business Records



Content from business-critical applications can be integrated into SAP Build Work Zone, advanced edition for viewing and interactive use. There are two main types of content that can be integrated: **Business Records** and **Document Repositories**. You can integrate each type of content using the particular technologies that are appropriate for the specific selected application.

-   **Business Records**: Data from a variety of business applications displays when getting the data from that application's OData API, or from an intermediary platform that supplies an OData API for that application, and using an OData annotations file to specify how each type of data displays in a specified UI element.
-   **Document Repositories**: Documents from an external document repository or library.



<a name="loio7c9f1030955f491484435b2933aa7316__section_rkn_zkg_4wb"/>

## Overview

You can develop new or custom integrations by leveraging the OData API and OData Annotations from the external solution. This approach requires some programming work. The mechanisms through which you can develop new or custom integrations are:

-   SAP NetWeaver Gateway: can supply OData and user identity services for on-premise applications.
-   SAP BTP: can supply OData and user identity services for cloud-hosted applications \[SaaS\].
-   By directly accessing the existing OData API and annotations of the external solution.



<a name="loio7c9f1030955f491484435b2933aa7316__section_ycj_5lg_4wb"/>

## Configure Access and Authorization for Integrated Applications

To enable access between SAP Build Work Zone, advanced edition and these various external solutions, one or more of the following access and authorization mechanisms must be configured:

-   Add a Trusted Certificate Authority for external solutions if your organization requires the use of unrecognized or self-signed certificates. It allows your browser to use the HTTPS or TLS connection to access the external solution data without obstruction. For more information, see [Add a Trusted Certificate Authority](add-a-trusted-certificate-authority-0f5c6b2.md)
-   Add an OAuth Client to configure an entry point used by external solutions to request authorizations from SAP Build Work Zone, advanced edition, which is required for the external solution to initiate requests to the API. For more information, see [Add an OAuth Client](add-an-oauth-client-b3c804e.md)
-   Add a SAML Trusted IdP to set up a relationship thatSAP Build Work Zone, advanced edition trusts to make authenticated per-user requests, for example to display data from SAP Build Work Zone, advanced edition by using the API. For more information, see [SAML Trusted IDPs](saml-trusted-idps-c2f81fd.md)
-   Configure SAP Build Work Zone, advanced edition as a SAML Local Identity Provider. This is required for SAP Build Work Zone, advanced edition to act as the trusted SAML identity provider for external solutions seeking single sign-on \(SSO\) user identity confirmation, and to make per-user requests of external solutions APIs. For more information, see [SAML Local Identity Provider](saml-local-identity-provider-176e87b.md) 



<a name="loio7c9f1030955f491484435b2933aa7316__section_cbd_4fg_4wb"/>

## Procedure

1.  Perform any required preparations on the external solution or the intermediary platform. For example, establishing trusted data communications with SAP Build Work Zone, advanced edition.
2.  Add a Trusted Certificate Authority.
3.  Optionally, you can also allow the external solution to open a connection to SAP Build Work Zone, advanced edition, which allows updates and feed events to be forwarded to SAP Build Work Zone, advanced edition. To configure, depending on the requirements of your external solution:
    1.  Add an OAuth Client.
    2.  Add a SAML Trusted IdP.
    3.  Configure SAP Build Work Zone, advanced edition as a SAML Local Identity Provider.

4.  Register the external business application in SAP Build Work Zone, advanced edition. For example, establishing trusted data communications with the external solution.
5.  Develop an OData Annotations file to display the business records if you are integrating business records via the SAP BTP, or you are doing a new or custom integration via SAP NetWeaver Gateway, or integrating a business application directly from a Third Party OData Source.
6.  Register the business records that you want to enable for viewing in SAP Build Work Zone, advanced edition.
7.  You can modify the data exposed in business records in two ways:
    -   Add a filter to any business record to narrow the range of results displayed in a particular business record, allowing data for multiple business records to display in different workspaces.
    -   Set a sort order for any business record, which determines the order in which the rows of information display in the business record. Note that for SuccessFactors Learning, filters are pre-configured and cannot be modified, and a sort order is not relevant.

8.  Add the business records to a workspace so that members can view and discuss the external data.



After the required configuration is done on the external application or intermediary platform, the external business application must be registered in the Admin console , *External Integration* \> *External Solutions* , in the *Add Application* menu.

**Related Information**  


[Integrating SAP Cloud for Customer](integrating-sap-cloud-for-customer-25d475b.md "You can integrate SAP Build Work Zone, advanced edition with SAP Cloud for Customer.")

[Integrating SAP SuccessFactors Learning](integrating-sap-successfactors-learning-acd784c.md "You can integrate SAP SuccessFactors Learning with SAP Build Work Zone, advanced edition.")

[Integrating Microsoft Office 365 SharePoint Sites](integrating-microsoft-office-365-sharepoint-sites-cd4cefc.md "You can integrate sites from your Microsoft Office 365 SharePoint so that the users can access them in SAP Build Work Zone, advanced edition.")

[Integrating Google Drive](integrating-google-drive-8288cd2.md "You can provide access to your organization's Google Drive account as a document repository.")

