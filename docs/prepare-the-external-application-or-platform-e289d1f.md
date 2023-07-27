<!-- loioe289d1f965114176a906f15356130714 -->

# Prepare the External Application or Platform

Once you've decided which application type your integration will use, you must configure the external application, and/or its intermediary enabling platform, to allow SAP Build Work Zone, advanced edition to access the business application's data using secure authorization mechanisms. While this configuration depends on which application type you've selected for your integration, there are some basic requirements that these configurations must meet.

The external application must be configured to enable the following:

-   It must allow SAP Build Work Zone, advanced edition to access its OData API $metadata file.
-   It must allow SAP Build Work Zone, advanced edition to access its OData API calls.
-   All of the external application's OData API must:
    -   Be public
    -   Return a valid XML
    -   Support `$filter` query operations
    -   Be compatible with the different caching periods that SAP Build Work Zone, advanced edition provides:
        -   Results from metadata are cached for 15 minutes
        -   Annotation files are cached for 15 minutes
        -   XML documents are cached for 3 minutes



For more information on these requirements, see [OData Assumptions](odata-assumptions-9e66b96.md).



<a name="loioe289d1f965114176a906f15356130714__section_dvf_yf5_4wb"/>

## Configuring Integration

**SAP BTP**: SAP BTP offers a wide array of options for accessing an application's data via an OData API. To select and configure the option that works best for you and your organization, please refer to SAP BTP documentation [SAP Business Technology Platform \(SAP BTP\)](https://help.sap.com/docs/btp?version=Cloud).

**SAP NetWeaver Gateway**: for more information about integrating social media on the SAP NetWeaver Application Server for ABAP, see [Social Media Integration](https://help.sap.com/docs/SAP_NETWEAVER_AS_ABAP_752/7259d88d94bb48c7b80b7928b7977ac6/abca91ec9b82493d822291476c043753.html)



**Next**: You have now dealt with preparing the external application for integration with SAP Build Work Zone, advanced edition. You must also perform the required access and authorization configuration procedures required:

-   If your organization's network requires the use of self-signed or unrecognized TLS or SSL certificates, you must [Add a Trusted Certificate Authority](add-a-trusted-certificate-authority-f8d9305.md).
-   If you want to display the external application's business records in SAP Build Work Zone, advanced edition, you must [Configure SAP Build Work Zone, advanced edition as a SAML Local Identity Provider](configure-sap-build-work-zone-advanced-edition-as-a-saml-local-identity-provider-39a4f6b.md). This step ensures that users can view only the content from the external application that they have been authorized to view when that material is displayed.
-   If you want to display SAP Build Work Zone, advanced edition content in the external application, you must:
    -   [Add an OAuth Client](add-an-oauth-client-5310092.md). This configuration provides the external application with authorized access to the SAP Build Work Zone, advanced edition API.
    -   [Add a SAML Trusted IDP](add-a-saml-trusted-idp-dad776e.md). This step ensures that users can view only the content from SAP Build Work Zone, advanced editionthat they have been authorized to view when that material is displayed in the external application.


