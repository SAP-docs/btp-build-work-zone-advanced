<!-- loio07b0a265ef4a41b8a1413005bc3c5e31 -->

# Run the Configurator

This is the final step of onboarding to SAP SuccessFactors Work Zone.



<a name="loio07b0a265ef4a41b8a1413005bc3c5e31__section_qsz_cgb_hlb"/>

## Launch the Configurator Wizard

After completing all previous steps, follow the configurator wizard to complete the onboarding process. You can access the configurator directly from the booster, or you can access it from the Site Manager as follows:

-   In the SAP BTP cockpit, *Services* \> *Instances and Subscriptions*, click the in the SAP SuccessFactors Work Zone link in the *Subscriptions* table to access the application. Log on with your SuccessFactors user credentials.
-   Open the *Configurator* screen from the left-side menu.



<a name="loio07b0a265ef4a41b8a1413005bc3c5e31__section_gkw_k2q_lsb"/>

## Option 1: Create a new tenant



### Step 1: Prerequisites

Confirm that you've created the necessary user groups and assigned them to role collections. For more information, see [Prerequisites](prerequisites-96b51b1.md)

Once you've confirmed the above, click the *Verify Active Identity Authentication* button to verify you have an active trust configuration before you proceed.



### Step 2: Create a Destination to SAP SuccessFactors

This is required to install the content package that contains HR Content from SAP SuccessFactors. Some of the content in this package requires setting up SAP Build Process Automation when running the booster. For more information, see [Run the Booster](run-the-booster-77be32c.md).

-   Select the SAP SuccessFactors API URL from the dropdown list.
-   Enter your company ID.
-   Enter API key.

    > ### Note:  
    > For a detailed explanation about how to obtain the API key, see [Create an OAuth Client in SAP SuccessFactors](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/69130a77dd12431ca5e0c41c2d5fbecb.html)




### Step 3: Set Up Environment

In this step, a series of configuration steps takes place in your subaccount to allow connectivity and authentication of different components in SAP SuccessFactors Work Zone .

Select the type of domain that you're using and enter the required details:

-   Default domain \(ondemand.com\): no addition input is required.
-   Custom domain: enter the following details: \(detailed instructions are listed here: [0002920494](https://me.sap.com/notes/0002920494)\)
    -   DWS custom domain
    -   Upload the certificate
    -   Upload the private key


> ### Note:  
> In China region, you can't select a domain other than the default one, therefore this option is not displayed in the configurator.

Click *Trigger Setup*.



### Step 4: Configure the Identity Authentication service and the Identity Provisioning service

In this step, you'll need to manually configure the Identity Authentication service and the Identity Provisioning service to enable user authentication and user provisioning.

1.  **Create an application in the Identity Authentication service** 

    1.  Open the administration console for SAP Cloud Identity Services. To do so, in SAP BTP cockpit, go to *Security* \> *Trust Configuration*, click the link pointing to your active Identity Authentication and add `/admin` to the URL.
    2.  Go to *Applications & Resources* \> *Applications* and click *\+Add* to add a new application from type *SAP BTP Solution*. Provide a meaningful name such as SAP SuccessFactors Work Zone. Select the protocol type `SAML 2.0`.
    3.  Open the *SAML 2.0 Configuration* editor of the application you've created, and paste the service provider metadata file that you’ve downloaded from the configurator. Save your changes. For more information, see [Create SAML 2.0 Application](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/fe3102ad92d94baa955ffa06b86d2cfa.html) 
    4.  Open the *Subject Name Identifier* editor of the application, and change the basic configuration attribute from `User ID` to `Global User ID`.

2.  **Configure the Identity Provisioning source and target systems**

    A source system is the connector used for reading entities \(users, groups, roles\). A target system is the connector used for writing \(provisioning\) entities. To learn more about this concept, see [Source Systems](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/58033bec92124ef2a7905b37d0f50704.html), [Target Systems](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/ab3f641552464c79b94d10b9205fd721.html)

    1.  In the administration console for SAP Cloud Identity Services, go to the *Administrators* tile and create a technical user \(of type System\) with a password and a generated client ID for authentication between the Identity Authentication service and the Identity Provisioning service. For more information, see [Add System as Administrator](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/bbbdbdd3899942ce874f3aae9ba9e21d.html#loiocefb742a36754b18bbe5c3503ac6d87c)

        > ### Note:  
        > When you configure a method of authentication \(step 6\), make sure to assign the roles *Manage Users* and *Manage Groups*.

    2.  Set up SAP SuccessFactors as a source system. Reminder: this is a suggested setup. You can choose the source system that matches your setup. For more details, see [SAP SuccessFactors](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/f29b5c6d7edd4f358548233c875ddefd.html). For more information about each property, see [List of Properties](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/d6f3577f30ec4af98e734b0126a60e37.html).

        > ### Note:  
        > If you're using the `sf.api.version` property, you must choose **v1** to sync the users from SuccessFactors to SAP SuccessFactors Work Zone.
        > 
        > There are 2 user syncs, one between SuccessFactors and Identity Authentication service \(see details in [Configuring Identity Authentication Service](https://help.sap.com/docs/SAP_SUCCESSFACTORS_WORK_ZONE/04877e17a5da4908a6fea94949e160b5/cc0aae759f3f460f9d244a5acfb7fee4.html)\), and another one between SuccessFactors and SAP SuccessFactors Work Zone \(done in this step\). For the first user sync, it is possible to use **v2** API, however for the sync with SAP SuccessFactors Work Zone, **v1** is mandatory because it's the only version that retrieves the SuccessFactors User ID property, which is required to run SuccessFactors content in SAP SuccessFactors Work Zone.

    3.  Configure the transformation of the source system. Transformations are used to map the user attributes from the data model of the source system to the data model of the target system, and the other way around. In this step, you'll replace the default transformation \(displayed under the *Transformations* tab after saving its initial configuration\), with the transformation that matches SAP SuccessFactors Work Zone

        **SAP SuccessFactors source system transformation**

        ```
        {
            "user":
            {
                "mappings": [
                {
                    "sourcePath": "$.personKeyNav.perPersonUuid",
                    "targetPath": "$.id",
                    "targetVariable": "entityIdSourceSystem"
                },
                {
                    "constant": false,
                    "targetPath": "$.active"
                },
                {
                    "condition": "$.personKeyNav.userAccountNav.accountStatus =='ACTIVE'",
                    "constant": true,
                    "targetPath": "$.active"
                },
                {
                    "sourcePath": "$.personKeyNav.userAccountNav.username",
                    "targetPath": "$.userName"
                },
                {
                    "sourcePath": "$.firstName",
                    "optional": true,
                    "targetPath": "$.name.givenName"
                },
                {
                    "sourcePath": "$.lastName",
                    "targetPath": "$.name.familyName"
                },
                {
                    "sourcePath": "$.email",
                    "targetPath": "$.emails[0].value"
                },
                {
                    "constant": "urn:ietf:params:scim:schemas:core:2.0:User",
                    "targetPath": "$.schemas[0]"
                },
                {
                    "constant": "urn:sap:cloud:scim:schemas:extension:sfsf:2.0:User",
                    "targetPath": "$.schemas[1]"
                },
                {
                    "constant": "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User",
                    "targetPath": "$.schemas[2]"
                },
                {
                    "sourcePath": "$.personKeyNav.perPersonUuid",
                    "targetPath": "$['urn:sap:cloud:scim:schemas:extension:sfsf:2.0:User']['personGUID']"
                },
                {
                    "sourcePath": "$.userId",
                    "targetPath": "$['urn:sap:cloud:scim:schemas:extension:sfsf:2.0:User']['userSysID']"
                },
                {
                    "sourcePath": "$.personKeyNav.userAccountNav.sapGlobalUserId",
                    "optional": true,
                    "targetPath": "$['urn:ietf:params:scim:schemas:extension:sap:2.0:User']['userUuid']"
                },
                {
                    "sourcePath": "$.personKeyNav.personIdExternal",
                    "optional": true,
                    "targetPath": "$['urn:ietf:params:scim:schemas:extension:enterprise:2.0:User']['employeeNumber']"
                },
                {
                    "sourcePath": "$.addressLine1",
                    "optional": true,
                    "targetPath": "$.addressLine1"
                },
                {
                    "sourcePath": "$.addressLine2",
                    "optional": true,
                    "targetPath": "$.addressLine2"
                },
                {
                    "sourcePath": "$.businessPhone",
                    "optional": true,
                    "targetPath": "$.businessPhone"
                },
                {
                    "sourcePath": "$.city",
                    "optional": true,
                    "targetPath": "$.city"
                },
                {
                    "sourcePath": "$.country",
                    "optional": true,
                    "targetPath": "$.country"
                },
                {
                    "sourcePath": "$.department",
                    "optional": true,
                    "targetPath": "$.department"
                },
                {
                    "sourcePath": "$.division",
                    "optional": true,
                    "targetPath": "$.division"
                },
                {
                    "sourcePath": "$.fax",
                    "optional": true,
                    "targetPath": "$.fax"
                },
                {
                    "sourcePath": "$.jobCode",
                    "optional": true,
                    "targetPath": "$.jobCode"
                },
                {
                    "sourcePath": "$.title",
                    "optional": true,
                    "targetPath": "$.title"
                },
                {
                    "sourcePath": "$.defaultLocale",
                    "optional": true,
                    "targetPath": "$.defaultLocale"
                },
                {
                    "sourcePath": "$.state",
                    "optional": true,
                    "targetPath": "$.state"
                },
                {
                    "sourcePath": "$.hireDate",
                    "optional": true,
                    "targetPath": "$.hireDate"
                },
                {
                    "sourcePath": "$.location",
                    "optional": true,
                    "targetPath": "$.location"
                },
                {
                    "sourcePath": "$.division",
                    "optional": true,
                    "targetPath": "$.division"
                },
                {
                    "sourcePath": "$.suffix",
                    "optional": true,
                    "targetPath": "$.suffix"
                },
                {
                    "sourcePath": "$.timeZone",
                    "optional": true,
                    "targetPath": "$.timeZone"
                },
                {
                    "sourcePath": "$.zipCode",
                    "optional": true,
                    "targetPath": "$.zipCode"
                },
                {
                    "sourcePath": "$.custom01",
                    "optional": true,
                    "targetPath": "$.custom01"
                },
                {
                    "sourcePath": "$.custom02",
                    "optional": true,
                    "targetPath": "$.custom02"
                },
                {
                    "sourcePath": "$.custom03",
                    "optional": true,
                    "targetPath": "$.custom03"
                },
                {
                    "sourcePath": "$.custom04",
                    "optional": true,
                    "targetPath": "$.custom04"
                },
                {
                    "sourcePath": "$.custom05",
                    "optional": true,
                    "targetPath": "$.custom05"
                },
                {
                    "sourcePath": "$.custom06",
                    "optional": true,
                    "targetPath": "$.custom06"
                },
                {
                    "sourcePath": "$.custom07",
                    "optional": true,
                    "targetPath": "$.custom07"
                },
                {
                    "sourcePath": "$.custom08",
                    "optional": true,
                    "targetPath": "$.custom08"
                },
                {
                    "sourcePath": "$.custom09",
                    "optional": true,
                    "targetPath": "$.custom09"
                },
                {
                    "sourcePath": "$.custom10",
                    "optional": true,
                    "targetPath": "$.custom10"
                },
                {
                    "sourcePath": "$.custom11",
                    "optional": true,
                    "targetPath": "$.custom11"
                },
                {
                    "sourcePath": "$.custom12",
                    "optional": true,
                    "targetPath": "$.custom12"
                },
                {
                    "sourcePath": "$.custom13",
                    "optional": true,
                    "targetPath": "$.custom13"
                },
                {
                    "sourcePath": "$.custom14",
                    "optional": true,
                    "targetPath": "$.custom14"
                },
                {
                    "sourcePath": "$.custom15",
                    "optional": true,
                    "targetPath": "$.custom15"
                },
                {
                    "sourcePath": "$.manager.personKeyNav.perPersonUuid",
                    "optional": true,
                    "targetPath": "$['urn:ietf:params:scim:schemas:extension:enterprise:2.0:User']['manager']['value']"
                }
               ]
            },
            "group":
            {
                "mappings": [
                {
                    "sourcePath": "$.groupID",
                    "targetVariable": "entityIdSourceSystem"
                },
                {
                    "sourcePath": "$.groupName",
                    "targetPath": "$.displayName"
                },
                {
                    "constant": "urn:ietf:params:scim:schemas:core:2.0:Group",
                    "targetPath": "$.schemas[0]"
                },
                {
                    "sourcePath": "$.users[*].personGUID",
                    "preserveArrayWithSingleElement": true,
                    "optional": true,
                    "targetPath": "$.members[?(@.value)]"
                }]
            }
        }
        ```

    4.  Set up SAP Build Work Zone, advanced edition as a target system. For more details, see [SAP Build Work Zone, advanced edition](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/787502df6ce14225b0e7cf7821e785eb.html) 

        For improved logging and error investigation, please use the following values:


        <table>
        <tr>
        <th valign="top">

        IPS Property Name
        
        </th>
        <th valign="top">

        Value
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        Type
        
        </td>
        <td valign="top">
        
        HTTP
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        URL
        
        </td>
        <td valign="top">
        
        Copy this value from the wizard - *Integration URL* field
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        ProxyType
        
        </td>
        <td valign="top">
        
        Internet
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Authentication
        
        </td>
        <td valign="top">
        
        BasicAuthentication
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        User
        
        </td>
        <td valign="top">
        
        Copy this value from the wizard - *OAuth Client Key* field
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Password
        
        </td>
        <td valign="top">
        
        Copy this value from the wizard - *OAuth Client Secret* field
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        OAuth2TokenServiceURL
        
        </td>
        <td valign="top">
        
        Copy this value from the wizard - *Token URL* field
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        ips.failed.request.retry.attempts
        
        </td>
        <td valign="top">
        
        3
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        ips.failed.request.retry.attempts.interval
        
        </td>
        <td valign="top">
        
        60
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        ips.delete.existedbefore.entities
        
        </td>
        <td valign="top">
        
        true
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        ips.trace.failed.entity.content
        
        </td>
        <td valign="top">
        
        true
        
        </td>
        </tr>
        </table>
        
    5.  Configure the transformation code of the target system. Replace the default transformation code \(displayed under the *Transformations* tab after saving its initial configuration\), with the following.

        **SAP SuccessFactors Work Zone target system transformation**

        ```
         {
             "user":
             {
                [
                 {
                     "targetPath": "$.id",
                     "type": "remove"
                 },
                 {
                     "sourceVariable": "entityIdTargetSystem",
                     "targetPath": "$.id"
                 },
                 {
                     "sourceVariable": "entityIdTargetSystem",
                     "targetPath": "$.id",
                     "scope": "deleteEntity"
                 },
                 {
                     "constant": false,
                     "targetPath": "$.active",
                     "scope": "deleteEntity"
                 },
                 {
                     "sourcePath": "$.active",
                     "targetPath": "$.active"
                 },
                 {
                     "constant": "employee",
                     "targetPath": "$.userType"
                 },
                 {
                     "sourcePath": "$['urn:ietf:params:scim:schemas:extension:sap:2.0:User']['userUuid']",
                     "targetPath": "$.userName"
                 },
                 {
                    "sourcePath": "$['urn:ietf:params:scim:schemas:extension:sap:2.0:User']['userUuid']",
                    "targetPath": "$['urn:ietf:params:scim:schemas:extension:sap:2.0:User']['userUuid']"
                 },
                 {
                     "sourcePath": "$.emails[0].value",
                     "targetPath": "$.emails[0].value"
                 },
                 {
                     "condition": "$.emails[0].length() > 0",
                     "constant": true,
                     "targetPath": "$.emails[0].primary"
                 },
                 {
                     "sourcePath": "$.title",
                     "optional": true,
                     "targetPath": "$.title"
                 },
                 {
                     "sourcePath": "$.defaultLocale",
                     "optional": true,
                     "targetPath": "$.locale"
                 },
                 {
                     "sourcePath": "$.timeZone",
                     "optional": true,
                     "targetPath": "$.timezone"
                 },
                 {
                     "sourcePath": "$.name.givenName",
                     "optional": true,
                     "targetPath": "$.name.givenName"
                 },
                 {
                     "sourcePath": "$.name.familyName",
                     "targetPath": "$.name.familyName"
                 },
                 {
                     "sourcePath": "$.name.middleName",
                     "optional": true,
                     "targetPath": "$.name.middleName"
                 },
                 {
                     "sourcePath": "$.suffix",
                     "optional": true,
                     "targetPath": "$.name.honorificSuffix"
                 },
                 {
                     "sourcePath": "$.salutation",
                     "optional": true,
                     "targetPath": "$.name.honorificPrefix"
                 },
                 {
                     "sourcePath": "$.gender",
                     "optional": true,
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamWorkforcePerson']['gender']"
                 },
                 {
                     "sourcePath": "$.userName",
                     "optional": true,
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamWorkforcePerson']['username']"
                 },
                 {
                     "sourcePath": "$.jobCode",
                     "optional": true,
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamWorkforcePerson']['jobcode']"
                 },
                 {
                     "sourcePath": "hireDate",
                     "optional": true,
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamWorkforcePerson']['hiredate']",
                     "functions": [
                         {
                             "function": "manipulateDate",
                             "sourceDateFormat": "Date(milliseconds)",
                             "targetDateFormat": "yyyy-MM-dd'T'HH:mm:ss'Z'"
                         }
                     ]
                 },
                 {
                     "sourcePath": "$.location",
                     "optional": true,
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamWorkforcePerson']['location']"
                 },
                 {
                     "sourcePath": "$.division",
                     "optional": true,
                     "targetPath": "$['urn:ietf:params:scim:schemas:extension:enterprise:2.0:User']['division']"
                 },
                 {
                     "sourcePath": "$.department",
                     "optional": true,
                     "targetPath": "$['urn:ietf:params:scim:schemas:extension:enterprise:2.0:User']['department']"
                 },
                 {
                     "sourcePath": "$.zipCode",
                     "optional": true,
                     "targetPath": "$.addresses[0].postalCode"
                 },
                 {
                     "sourcePath": "$.state",
                     "optional": true,
                     "targetPath": "$.addresses[0].region"
                 },
                 {
                     "sourcePath": "$.addressLine1",
                     "optional": true,
                     "targetPath": "$.addresses[0].streetAddress"
                 },
                 {
                     "condition": "$.addressLine1 EMPTY false",
                     "sourcePath": "$.addressLine1",
                     "targetPath": "$.addresses[0].streetAddress"
                 },
                 {
                     "condition": "($.addressLine1 EMPTY false) && ($.addressLine2 EMPTY false)",
                     "sourcePath": "$.addressLine1",
                     "targetPath": "$.addresses[0].streetAddress",
                     "functions": [
                     {
                         "function": "concatString",
                         "suffix": "$.addressLine2"
                     }]
                 },
                 {
                     "sourcePath": "$.city",
                     "optional": true,
                     "targetPath": "$.addresses[0].city"
                 },
                 {
                     "constant": true,
                     "targetPath": "$.addresses[0].primary"
                 },
                 {
                     "constant": "work",
                     "targetPath": "$.addresses[0].type"
                 },
                 {
                     "condition": "$.businessPhone EMPTY false",
                     "sourcePath": "$.businessPhone",
                     "targetPath": "$.phoneNumbers[0].value"
                 },
                 {
                     "condition": "$.businessPhone EMPTY false",
                     "constant": "work",
                     "targetPath": "$.phoneNumbers[0].type"
                 },
                 {
                     "condition": "$.fax EMPTY false",
                     "sourcePath": "$.fax",
                     "targetPath": "$.phoneNumbers[1].value"
                 },
                 {
                     "condition": "$.fax EMPTY false",
                     "constant": "fax",
                     "targetPath": "$.phoneNumbers[1].type"
                 },
                 {
                     "sourcePath": "$['urn:sap:cloud:scim:schemas:extension:sfsf:2.0:User']['userSysID']",
                     "targetPath": "$.externalId"
                 },
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
                 {
                     "sourcePath": "$.custom02",
                     "optional": true,
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute2']['value']"
                 },
                 {
                     "condition": "$.custom02 EMPTY false",
                     "constant": "Custom Attribute 2",
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute2']['name']"
                 },
                 {
                     "sourcePath": "$.custom03",
                     "optional": true,
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute3']['value']"
                 },
                 {
                     "condition": "$.custom03 EMPTY false",
                     "constant": "Custom Attribute 3",
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute3']['name']"
                 },
                 {
                     "sourcePath": "$.custom04",
                     "optional": true,
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute4']['value']"
                 },
                 {
                     "condition": "$.custom04 EMPTY false",
                     "constant": "Custom Attribute 4",
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute4']['name']"
                 },
                 {
                     "sourcePath": "$.custom05",
                     "optional": true,
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute5']['value']"
                 },
                 {
                     "condition": "$.custom05 EMPTY false",
                     "constant": "Custom Attribute 5",
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute5']['name']"
                 },
                 {
                     "sourcePath": "$.custom06",
                     "optional": true,
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute6']['value']"
                 },
                 {
                     "condition": "$.custom06 EMPTY false",
                     "constant": "Custom Attribute 6",
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute6']['name']"
                 },
                 {
                     "sourcePath": "$.custom07",
                     "optional": true,
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute7']['value']"
                 },
                 {
                     "condition": "$.custom07 EMPTY false",
                     "constant": "Custom Attribute 7",
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute7']['name']"
                 },
                 {
                     "sourcePath": "$.custom08",
                     "optional": true,
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute8']['value']"
                 },
                 {
                     "condition": "$.custom08 EMPTY false",
                     "constant": "Custom Attribute 8",
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute8']['name']"
                 },
                 {
                     "sourcePath": "$.custom09",
                     "optional": true,
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute9']['value']"
                 },
                 {
                     "condition": "$.custom09 EMPTY false",
                     "constant": "Custom Attribute 9",
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute9']['name']"
                 },
                 {
                     "sourcePath": "$.custom10",
                     "optional": true,
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute10']['value']"
                 },
                 {
                     "condition": "$.custom10 EMPTY false",
                     "constant": "Custom Attribute 10",
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute10']['name']"
                 },
                 {
                     "sourcePath": "$.custom11",
                     "optional": true,
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute11']['value']"
                 },
                 {
                     "condition": "$.custom11 EMPTY false",
                     "constant": "Custom Attribute 11",
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute11']['name']"
                 },
                 {
                     "sourcePath": "$.custom12",
                     "optional": true,
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute12']['value']"
                 },
                 {
                     "condition": "$.custom12 EMPTY false",
                     "constant": "Custom Attribute 12",
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute12']['name']"
                 },
                 {
                     "sourcePath": "$.custom13",
                     "optional": true,
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute13']['value']"
                 },
                 {
                     "condition": "$.custom13 EMPTY false",
                     "constant": "Custom Attribute 13",
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute13']['name']"
                 },
                 {
                     "sourcePath": "$.custom14",
                     "optional": true,
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute14']['value']"
                 },
                 {
                     "condition": "$.custom14 EMPTY false",
                     "constant": "Custom Attribute 14",
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute14']['name']"
                 },
                 {
                     "sourcePath": "$.custom15",
                     "optional": true,
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute15']['value']"
                 },
                 {
                     "condition": "$.custom15 EMPTY false",
                     "constant": "Custom Attribute 15",
                     "targetPath": "$['urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser']['customAttribute15']['name']"
                 },
                 {
                     "condition": "$['urn:sap:cloud:scim:schemas:extension:sfsf:2.0:User']['userSysID'] == '<INSERT USER ID>'",
                     "constant": "Administrator",
                     "targetPath": "$.roles[0].value"
                 },
                 {
                    "sourcePath": "$['urn:ietf:params:scim:schemas:extension:enterprise:2.0:User']['manager']['value']",
                    "optional": true,
                    "targetPath": "$['urn:ietf:params:scim:schemas:extension:enterprise:2.0:User']['manager']['value']",
                    "functions": [
                        {
                            "function": "resolveEntityIds"
                        }
                    ]
                 }
        
                ]
             },
            "group":
            {
                "ignore": true,
                 "mappings": [
                 {
                     "sourcePath": "$",
                     "targetPath": "$"
                 },
                 {
                     "targetPath": "$.id",
                     "type": "remove"
                 },
                 {
                     "sourceVariable": "entityIdTargetSystem",
                     "targetPath": "$.id"
                 },
                 {
                     "targetPath": "$.members",
                     "type": "remove"
                 },
                 {
                     "sourcePath": "$.members[*].value",
                     "preserveArrayWithSingleElement": true,
                     "optional": true,
                     "targetPath": "$.members[?(@.value)]",
                     "functions": [
                     {
                         "type": "resolveEntityIds"
                     }]
                 }]
             }
        }
        ```

        > ### Tip:  
        > 
        > <table>
        > <tr>
        > <th valign="top">
        > 
        > Section
        > 
        > </th>
        > <th valign="top">
        > 
        > Hint
        > 
        > </th>
        > </tr>
        > <tr>
        > <td valign="top">
        > 
        > ```
        > "sourcePath": "$['urn:ietf:params:scim:schemas:extension:sap:2.0:User']['userUuid']",
        >              "targetPath": "$.userName"
        > ```
        > 
        > 
        > 
        > </td>
        > <td valign="top">
        > 
        > When choosing a different source for the userName attribute, remember to adjust the userIdSource property in the 'JAM' destination accordingly. For more information, see [Solution Architecture](solution-architecture-1fd9ea4.md).
        > 
        > </td>
        > </tr>
        > <tr>
        > <td valign="top">
        > 
        > ```
        >  { 
        > 		   "condition": "$['urn:sap:cloud:scim:schemas:extension:sfsf:2.0:User']['userSysID'] == '<INSERT USER ID>'", 
        > 		   "constant": "Administrator", 
        > 		   "targetPath": "$.roles[0].value"
        >           } 
        > ```
        > 
        > 
        > 
        > </td>
        > <td valign="top">
        > 
        > Required to assign the 'Company Administrator' role in addition to the role collection.
        > 
        > Users that are assigned to the `Workzone_Admin` group in Identity Authentication are company administrators.
        > 
        > For more information, see [Assigning Company Administrators](assigning-company-administrators-ff793e6.md).
        > 
        > </td>
        > </tr>
        > <tr>
        > <td valign="top">
        > 
        > ```
        > "group":
        >     {
        >         "ignore": true,
        >         "mappings": [
        >         {
        >             ...
        >         },
        > ```
        > 
        > 
        > 
        > </td>
        > <td valign="top">
        > 
        > By default, the group mapping is inactive \(ignored\) but groups are supported. To start provisioning groups, either delete the statement "ignore": true, or set its value to false.
        > 
        > </td>
        > </tr>
        > </table>

        > ### Note:  
        > -   **User Types in SAP SuccessFactors Work Zone:**
        >     -   employee = internal user
        >     -   public = external users
        >     -   By default, all users from SAP SuccessFactors are created as internal users. This is done by setting the userType ‘employee’ as a constant in the target system. When using the provided transformation from the wizard during the decoupling process from HXM Core \(BizX\), there is a condition to check for SAP SuccessFactors-managed external users – for which the userType will be set to ‘public’ instead. For more information, see [0003111415](https://me.sap.com/notes/0003111415)
        > 
        > -   **Job Title**
        > 
        >     The job title is not provided as an attribute in the Identity Authentication Admin UI. If needed, the mapping for this field can be adjusted to read the value from another attribute.
        > 
        > -   **Company Administrators in SAP SuccessFactors Work Zone**
        > 
        >     Users that are included in the target system condition – specifically their User ID - are assigned as company administrators.
        > 
        >     For more information, see [Assigning Company Administrators](assigning-company-administrators-ff793e6.md)
        > 
        > -   **Custom Attributes**
        > 
        >     The transformation code includes example mappings for 1-15 custom attributes.
        > 
        >     The same approach can be used for the remaining custom attributes. SAP SuccessFactors Work Zone supports up to 20 custom attributes.

    6.  **\[Optional\]: Use X.509 Certificate-Based Authentication**

        To use an x.509 certificate-based authentication between the Identity Provisioning service and SAP Build Work Zone, advanced edition, configure the following steps:

        1.  In the SAP Build Work Zone, advanced edition target system *Properties* tab, make the following changes to the previously defined properties:


            <table>
            <tr>
            <th valign="top">

            Name
            
            </th>
            <th valign="top">

            Value
            
            </th>
            </tr>
            <tr>
            <td valign="top">
            
            Authentication
            
            </td>
            <td valign="top">
            
            `ClientCertificateAuthentication`
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            OAuth2TokenServiceURL
            
            </td>
            <td valign="top">
            
            `https: /<company_uuid>.api-<region_host>.dws.workzone.ondemand.com/api/v2/auth/token`

            > ### Note:  
            > The `api-` prefix before `<region_host>` is necessary for using `ClientCertificateAuthentication` authentication.


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            `client_id`
            
            </td>
            <td valign="top">
            
            Take this value from the *OAuth Client ID*.

            > ### Note:  
            > This value is different from the User property.


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            `User`, `Password`
            
            </td>
            <td valign="top">
            
            In this authentication type, the properties `User` and `Password` are obsolete.
            
            </td>
            </tr>
            </table>
            
        2.  In the *Outbound Certificate* tab, click *Generate* to create a `.crt` file.

            ![Outbound certificate tab in the target system](images/Outbound_certificate_2b2a78e.png)

        3.  Open the SAP Build Work Zone, advanced edition Admin Console, *External Integrations* \> *OAuth Clients*. Edit the *Workzone API Client* oAuth client, and copy the content of the `.crt` file into the *X509 Certificate \(Base64\)* input field. Click *Save*.

            ![x509 certificate field in oAuth client](images/X509_certificate_ecc61c2.png).


    7.  Trigger a **Read Job** in the source system. When done, check the job status and verify that the write action to the target system was executed successfully. For more information, see [Start and Stop Provisioning Jobs](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/start-and-stop-provisioning-jobs?version=Cloud) and [Monitor Provisioning Job Logs](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/monitor-provisioning-job-logs?version=Cloud).





### \[Before launching\] Configure trusted domain

Add the runtime domain \(default domain or custom domain\) as a trusted domain to Identity Authentication. Using the *Integration URL* information that is displayed in the wizard, complete the following procedure: [Configured Trusted Domain](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/08fa1fe816704d99a6bcab245158ebca.html).



### Step 5: Launch

Congratulations - you've successfully completed the onboarding steps and you can now launch SAP SuccessFactors Work Zone.



<a name="loio07b0a265ef4a41b8a1413005bc3c5e31__section_tt5_5gb_hlb"/>

## Option 2: Create a tenant based on an existing SAP Jam tenant



### Step 1: Prerequisites

Confirm that you've completed the following steps. For more information, see [Prerequisites](prerequisites-96b51b1.md)

-   Confirm that your SAP Jam tenant has been converted to use the Identity Authentication service and the Identity Provisioning service instead of SAP SuccessFactors HXM Core \('BizX'\).
-   Confirm that your SAP Jam tenant has been migrated to the ondemand.com domain or a custom domain.
-   Confirm that you have mapped the Identity Authentication groups to the SAP SuccessFactors Work Zone role collections.

Once you've confirmed the above, click the *Verify Active Identity Authentication* button to verify you have an active trust configuration before you proceed.



### Step 2: Create a Destination to SAP SuccessFactors

This is required to install the content package that contains HR Content from SAP SuccessFactors. Some of the content in this package requires setting up SAP Build Process Automation when running the booster. For more information, see [Run the Booster](run-the-booster-77be32c.md).

-   Select the SAP SuccessFactors API URL from the dropdown list.
-   Enter your company ID.
-   Enter API key.

    > ### Note:  
    > For a detailed explanation about how to obtain the API key, see [Create an OAuth Client in SAP SuccessFactors](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/69130a77dd12431ca5e0c41c2d5fbecb.html)




### Step 3: Create a Destination to SAP SuccessFactors Work Zone

In this step, you'll enable connectivity between SAP SuccessFactors Work Zone and SAP BTP, Cloud Foundry Environment.

1.  Select the type of domain you're using and enter the required details:
    -   Default domain \(ondemand.com\): enter the SAP Jam URL \(after the migration to ondemand.com\). The SAP Jam URL has the following convention: `https://[company ID in lower case].core[HCM/DWS data center number].workzone.ondemand.com`.
    -   Custom domain: enter the SAP Jam data center and the SAP Jam URL \(after the migration to custom domain\).

2.  Generate an OAuth client. As input, it's enough to enter the client name and an identifier URL \(can be any URL\). Once generated, add the key and secret information in the configurator. For more information see [OAuth Clients](oauth-clients-b3c804e.md).



### Step 4: Set Up Environment

In this step, a series of configuration steps takes place in your subaccount to allow connectivity and authentication of different components in SAP SuccessFactors Work Zone.

Click *Trigger Setup*.



### \[Before launching\] Configure trusted domain

Add the runtime domain \(default domain or custom domain\) as a trusted domain to Identity Authentication. For more information, see [Configured Trusted Domain](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/08fa1fe816704d99a6bcab245158ebca.html).



### Step 5: Launch

Congratulations - you've successfully completed the onboarding steps and you can now launch SAP SuccessFactors Work Zone.



<a name="loio07b0a265ef4a41b8a1413005bc3c5e31__section_hln_kl4_fsb"/>

## Additional Information

-   [Before Using SAP SuccessFactors Work Zone](https://help.sap.com/viewer/04877e17a5da4908a6fea94949e160b5/Cloud/en-US/d57107b6090746bca8658687b2cb49c8.html)
-   [Deploying a Content Package with Workflow Content to SAP SuccessFactors Work Zone](https://help.sap.com/docs/WZ/7d3b9c7211ca4d7a9630b524205ee836/304a2187bf6e449a87e857ee843dec23.html?q=Deploying%20a%20Content%20Package%20with%20Workflow%20Content%20to%20SAP%20SuccessFactors%20Work%20Zone)
-   [Creating a Destination to the SAP Build Work Zone, Advanced Edition Content Repository](https://help.sap.com/docs/WZ/7d3b9c7211ca4d7a9630b524205ee836/4a90162810014b9396dd0edd00b9bc78.html?q=Creating%20a%20Destination%20to%20the%20)
-   [Upgrade from ODATA IPS Connector to SCIM IPS Connector with SAP SuccessFactors HXM Suite](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/568fdf1f14f14fd089a3cd15194d19cc/80d3d1d92fdd414c873ee9420ada1078.html)
-   [Mapping Between SCIM Users and ODATA User](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/534356acc0ab4b0e8977ebfb2eb432f7/00df9b8134d04fe496a7144c18c0d4a4.html)

