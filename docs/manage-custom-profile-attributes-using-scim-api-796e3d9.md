<!-- loio796e3d9809d54c18b8f527f17b4128fd -->

# Manage Custom Profile Attributes using SCIM API

Information about using custom attributes in the user profile.



This guide is equally applicable to SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone. For convenience, we will use the product name SAP Build Work Zone, advanced edition.

> ### Note:  
> SAP SuccessFactors Work Zone connected to HXM Core \(BizX\) is no longer supported, and since February 2022 all customers need to follow SAP note [0003111415](https://launchpad.support.sap.com/#/notes/0003111415) - How to decouple SAP Jam or SAP SuccessFactors Work Zone from BizX, guidelines to switch to the new setup.



<a name="loio796e3d9809d54c18b8f527f17b4128fd__section_cb1_xmr_4tb"/>

## Introduction

SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone provide a SCIM API to provision user profiles as well as imported user lists. In the context of user profiles, next to several standard profile attributes like name, department, or e-mail, it is also possible to provision up to 20 custom attributes into the user profile. For more information, see [User and User List Provisioning Using SCIM API](user-and-user-list-provisioning-using-scim-api-6bd5237.md), and [Manage Administrators Using SCIM API](manage-administrators-using-scim-api-ff793e6.md) 

The data in these custom fields is then available for display on the user profile, but also for building dynamic user list rules and for assigning homepages, workspaces, and other elements dynamically based on custom fields data.

> ### Note:  
> If SAP SuccessFactors Work Zone is still connected to HXM Core \(BizX\), the SAP Build Work Zone, advanced edition SCIM API is not used and hence there are only 15 custom attributes mapped to the employee profile from HXM Core. This is no longer supported and customers are required to switch to the new setup as mentioned above.



<a name="loio796e3d9809d54c18b8f527f17b4128fd__section_agb_tnr_4tb"/>

## SCIM User Profile Data Model

The SAP Build Work Zone, advanced edition user record is based on SCIM - an industry standard for cross-domain identity management. For the custom fields specifically, SAP Build Work Zone, advanced edition leverages a custom schema in the user data model: "urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser". 

The custom attributes are structured as follows:

```
 "urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser": { 
                "customAttribute1": { 
                    "name": "Label for Custom 1", 
   			  "value": "Value for Custom 1" 
                }, 
             […] 
            } 
```



<a name="loio796e3d9809d54c18b8f527f17b4128fd__section_trq_c4r_4tb"/>

## Manage Custom Attributes via SAP Cloud Identity Services - Identity Provisioning

You can populate these custom attributes with basically any data from the selected source system in Identity Provisioning. The code samples below are an extract from the standard SAP Build Work Zone, advanced edition target system transformation code.

**Example 1: Identity Authentication as source system**

```
 { 

            "condition": "$.['urn:sap:cloud:scim:schemas:extension:custom:2.0:User']['attributes'][?(@.name == 'customAttribute1')]['value'] EMPTY false", 

            "sourcePath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:User']['attributes'][?(@.name == 'customAttribute1')]['value']", 

            "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute1']['value']" 

        }, 

        { 

            "condition": "$.['urn:sap:cloud:scim:schemas:extension:custom:2.0:User']['attributes'][?(@.name == 'customAttribute1')]['value'] EMPTY false", 

            "constant": "Custom 1", 

            "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute1']['name']" 

        } 
```

**Example 2: SAP SuccessFactors as a source system**

```
 { 

             "sourcePath": "$.custom01", 

             "optional": true, 

             "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute1']['value']" 

         }, 

         { 

             "condition": "$.custom01 EMPTY false", 

             "constant": "Custom Attribute 1", 

             "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute1']['name']" 

         }, 
```

The desired value/data is provisioned into the custom schema \(see above\), specifically into the value attribute of the `customAttribute1` section of the `urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser` schema. While the value attribute is different for each user profile, the name is fixed for the SAP Build Work Zone, advanced edition tenant – hence it is recommended to set them as a “constant” via the Identity Provisioning target system transformation.



<a name="loio796e3d9809d54c18b8f527f17b4128fd__section_rjq_gqr_4tb"/>

## Using user profile custom attributes

The custom attributes are available to be added to the user profile, displaying additional information on the SAP Build Work Zone, advanced edition/SAP SuccessFactors Work Zone user profile, and ensuring they get included in the site \(people\) search. This can be configured in the Admin Panel *Area & Workspace Configuration* \> *Profiles*. The changed name attribute in the SCIM schema will also be visible in the profile section if enabled.

Even more powerful is the option of leveraging these custom attributes for dynamic user lists. For example, automatically assigning users to regional or department-focused workspaces without any continuous / manual effort. For more information, see [User Lists](user-lists-8d23bc7.md)

