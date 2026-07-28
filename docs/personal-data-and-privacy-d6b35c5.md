<!-- loiod6b35c55d91a4231b3f9b390ae89c0d8 -->

# Personal Data and Privacy

The features and functions for data protection and privacy of SAP Business Technology Platform also apply to SAP Build Work Zone, advanced edition. For more information about the features and functions for data protection and privacy in SAP BTP, see [Data Protection and Privacy](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/7e513d31704a4a87831191e504ca850a.html) in the SAP BTP documentation in the **Security** section.

In addition to the features and functions for data protection and privacy in SAP BTP, SAP Build Work Zone, advanced edition also provides the following functionality to help adhere to data privacy standards:



## Consent and Personal Data Collection: Company Terms of Service and Workspace Terms of Use

As a user, you may be required to accept a company's custom Terms of Service and custom external Terms of Service before you’re permitted to access SAP Build Work Zone, advanced edition. When you accept the custom Terms of Service, the acceptance details - including the time stamp of when you accepted the terms, and the version of the accepted Terms of Service - are logged in a compliance report. Company administrators can view and specify the date range for the "Terms of Service" report.

Before you join a workspace, you may be required to accept the workspace's Terms of Use in order to participate in workflows and information sharing within this workspace. When you accept a workspace's Terms of Use, the acceptance details - including the timestamp of when you accepted the terms, and the version of the accepted Terms of Use - are logged in a compliance report. Workspace administrators can view and specify the date range for the "Terms of Use" report.



## External User Profiles

Until you, as an external user , have accepted a workspace invitation and the workspace's Terms of Use, your profile won’t be visible to or accessible by non-administrator workspace members. Only workspace administrators can access a profile and engage an external user in workspace activities before you’ve officially joined the workspace.



## Logged Changes for Personal Data

Any profile changes made by you as a user are logged in product audit logs. Data changes to the core profile data that is synchronized into SAP Build Work Zone, advanced edition from your provisioning system are logged by those systems respectively.



## Personal Data Erasure: Alumni Profile Page Access

When you leave the company, in the *Administration Console* \> *Feature Enablement* \> *Features* page, the company administrator can restrict viewing access to your information, now as an alumnus:

-   **Show profile pages for alumni:** 

    If this option is selected, your profile page is still visible. Your profile contributions \(for example, wiki pages, photos, any content you’ve created and uploaded to your profile, or content that you’re tagged in\) are still available for others to reference.

    The company administrator can deselect this option to block access to, and the visibility of, your alumni profile page.

-   **Clear profile info for alumni:** 

    If selected, this option allows the administrator to remove your avatar images, office location information, and personal contact information from the site, although your manager and job title information is retained. Your profile contributions, for example, wiki pages, photos, or any content you’ve created and uploaded to your user profile page are still available for others to reference.


When either option is enabled, your alumni personal information is removed from all underlying database tables. All posts, uploads, and activity performed by you is now attributed to the text string, 'Alumni' or its corresponding localized strings in languages other than English.

> ### Note:  
> When a user's status is 'alumni' and their 30-day retention period has expired, all of their profile's change logs \(for example, change logs for email, telephone, custom fields, etc.\), will be deleted.



<a name="loiod6b35c55d91a4231b3f9b390ae89c0d8__section_cng_stp_m1c"/>

## Retention period

If the *Clear profile info for alumni* option is enabled, the retention period for alumni data is 30 days.



## Profile Data Disclosure

In the User Action menu, under *Settings* \> *Advanced Settings* \> *Profile Data Disclosure*, you can view a list of your personal data. Disclosure details satisfy the compliance requirements for national and regional data privacy standards. Personal data from your provisioning system \(for example, e-mail addresses, phone numbers, location addresses\) can also display on this page.



<a name="loiod6b35c55d91a4231b3f9b390ae89c0d8__section_yy2_z12_ldc"/>

## Downloading Personal Data

Users can request administrators to download their personal data.

As an administrator, you can do this from the *Administration Console* \> *Users* by clicking *Export User Data* from the *Actions* menu. If the export is successful, a ZIP file is added to your user profile under *My Exports*. You can then download the extracted ZIP file and send it to the user.

