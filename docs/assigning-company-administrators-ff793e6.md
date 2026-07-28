<!-- loioff793e6aa85d44dc86caa1281621f4a9 -->

# Assigning Company Administrators

You can manage the company administrator assignment using the SCIM API.



As part of the onboarding process, you configure the transformation code in the Identity Provisioning service. The transformation code includes also assignment of company administrators.





### SAP Build Work Zone, advanced edition

Users that are provisioned to SAP Build Work Zone, advanced edition by the Identity Provisioning service and are assigned to the group `Workzone_Admin` in Identity Authentication, will be provisioned with the `Administrator` attribute and can be assigned as company administrators.

The Identity Provisioning target transformation code includes this section:

> ### Sample Code:  
> ```
> {
>             "condition": "$.groups[?(@.display == 'Workzone_Admin')] EMPTY false",
>             "constant": "Administrator",
>             "targetPath": "$.roles[0].value"
>         }
> ```



### SAP SuccessFactors Work Zone

Users that their user ID is included in this Identity Provisioning target transformation code condition, are assigned as company administrators.

> ### Sample Code:  
> ```
>  { 
> 		   "condition": "$['urn:sap:cloud:scim:schemas:extension:sfsf:2.0:User']['userSysID'] == '<INSERT USER ID>'", 
> 		   "constant": "Administrator", 
> 		   "targetPath": "$.roles[0].value"
>           } 
> ```



The SCIM API expects the following attribute in the user profile/payload:

> ### Sample Code:  
> ```
>     "roles": [
>         {
>             "value": "Administrator"
>         }
>     ]
> 
> ```

> ### Note:  
> -   Managing the company administrator via the SCIM API is enabled by default for SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone. If you choose to assign the company admin role manually, in the Administrator Console *Users* \> *User Setup Options* section, the `Administrator` attribute in the transformation code is ignored.
> -   The SCIM API can only be used to assign company administrators. Other delegated admins, such as the Support admin or an Area admin can only be assigned manually.

