<!-- loio627b9e36a3da430199133c6ca0db45d8 -->

# Getting Started

Step-by-step guides for onboarding to SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone.



<a name="loio627b9e36a3da430199133c6ca0db45d8__section_wgz_1vf_3qb"/>

## Setup Options

The SAP Build Work Zone, advanced edition/SAP SuccessFactors Work Zone onboarding guides describe the simplest approach for user authentication and provisioning, using SAP Cloud Identity Services - Identity Authentication as the primary IdP and SAP Cloud Identity Services - Identity Provisioning for user provisioning. However, you can adjust the process to meet the requirements of your own environment.

For example, instead of using Identity Authentication as the primary IdP, you can use an SAP or 3rd-party IdP as a source system for user data, and use Identity Authentication as a proxy between the source and SAP Build Work Zone, advanced edition. Another example is that in the onboarding guide you are instructed to use SAP SuccessFactors as a source system in Identity Provisioning when onboarding to SAP SuccessFactors Work Zone, however, there is no real restriction here. You can choose any source system from the supported list in Identity Provisioning.

> ### Note:  
> In China region, SAP Build Work Zone, advanced edition, which is based on the subscription commercial model, isn’t supported. You can only onboard to SAP SuccessFactors Work Zone.

For more information about different configuration options, see [User Authentication and Authorization](user-authentication-and-authorization-f04c185.md)



## Onboarding Guides

SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone offer the same functionality and content, however there are differences in the way the services are priced and packaged \(the first is a standalone service while the second is a bundled solution\). In addition, each service has a dedicated onboarding booster and some minor changes in the Identity Authentication setup. Therefore, the onboarding guides are very similar but not identical:

-   [Onboarding to SAP Build Work Zone, advanced edition](onboarding-to-sap-build-work-zone-advanced-edition-f8c6eab.md)
-   [Onboarding to SAP SuccessFactors Work Zone](onboarding-to-sap-successfactors-work-zone-edc62f9.md)



<a name="loio627b9e36a3da430199133c6ca0db45d8__section_j3q_mdj_5wb"/>

## Using a Custom Domain

If you already have a custom domain in place, you can use it when onboarding to SAP Build Work Zone, advanced edition/SAP SuccessFactors Work Zone. In the configurator step of the onboarding, you'll have the option to use your custom domain instead of the default ondemand.com domain.

If you set up a custom domain after you've already been onboarded \(more information about the setup here: [Overview of Custom Domains](overview-of-custom-domains-97a7ee5.md)\), you would need to run the configurator step again, this time with your custom domain.



<a name="loio627b9e36a3da430199133c6ca0db45d8__section_yrt_dfw_g4b"/>

## Information for SAP SuccessFactors Customers, Partners, and Consultants

If you are planning to use SAP SuccessFactors as your user source, read more about the essential architecture, migration and implementation concepts to be considered when onboarding to SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone. For more information, see [Implementation Design Principle](https://d.dam.sap.com/a/3nZVVDd).

> ### Note:  
> After customers complete the SAP SuccessFactors Work Zone migration process, some of the existing SAP Jam functionality will not be supported, including SAP Jam Mobile app functionality for feeds and groups. For customers with mobile requirements, it is recommended to deploy the SAP Build Work Zone, advanced edition Mobile app instead. For more information about unsupported features, see [Restrictions](restrictions-b259464.md)

