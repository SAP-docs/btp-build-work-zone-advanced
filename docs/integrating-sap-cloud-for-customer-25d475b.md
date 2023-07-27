<!-- loio25d475be44504a6fb9a4350b93af220b -->

# Integrating SAP Cloud for Customer

You can integrate SAP Build Work Zone, advanced edition with SAP Cloud for Customer.



When integrating SAP Build Work Zone, advanced edition with your SAP Cloud for Customer solution, you enable cross-application interaction using the feed. Users can then feature SAP Cloud for Customer accounts, opportunities, products, and service tickets in workspaces.



### Prerequisites

-   SAP Build Work Zone, advanced edition: A tenant has been provisioned for your company, and you have been given administrator access. You know how your users were provisioned for your SAP Build Work Zone, advanced edition system.

-   SAP Cloud for Customer: Initial setup and configuration have been performed in the tenant. You have administrator access and know how your users were provisioned for your SAP Cloud for Customer system.

-   Cross-system authentication: If user IDs or email addresses are identical in SAP Build Work Zone, advanced edition and SAP Cloud for Customer, you can use dynamic onboarding without explicit user mapping. If not, explicit user mapping is required.

    While the SAP Cloud for Customer user ID is used as the logon user ID, the SAP Build Work Zone, advanced edition user ID is not. The SAP Build Work Zone, advanced edition user ID must be in uppercase and fewer than 40 characters for this integration to work without explicit user mapping.

    With the user email address as the key identifier, SAP Cloud for Customer and SAP Build Work Zone, advanced edition use it for back-end authentication during API calls. Users aren't actually logging in with their email addresses.




### Integration Steps

To integrate SAP Build Work Zone, advanced edition with SAP Cloud for Customer, on the SAP Cloud for Customer product page, see [Integrate with SAP Jam](https://help.sap.com/viewer/908c545d8c224add8d17d7bcd3047242/2002/en-US).

