<!-- loioff793e6aa85d44dc86caa1281621f4a9 -->

# Manage Administrators Using SCIM API

In SAP Build Work Zone, advanced edition, you can manage the Company Administrator permissions using SCIM APIs.



<a name="loioff793e6aa85d44dc86caa1281621f4a9__section_ahw_ywl_trb"/>

## Managing administrators locally \(manually\)

In this setup, the first internal user to log in to SAP Build Work Zone, advanced edition, will automatically become the first Company Administrator. This user can then grant the company administrator or other administator permissions, to additional users as follows:

1.  Open the Administration Console.

2.  Expand the *Users* section and click *Internal Users*.

3.  Select a user and under *Actions*, click *Edit*.

4.  In the *Edit Profile* screen, select the *User Type*.




<a name="loioff793e6aa85d44dc86caa1281621f4a9__section_zxk_hxl_trb"/>

## Managing administrators using a SCIM provisioning



### SAP Build Work Zone, advanced edition

In this option, only users with the SCIM role `Administrator` can be a Company Administrator in SAP Build Work Zone, advanced edition.

Instead of managing the Company Administrator permission locally, this permission is assigned based on a specific attribute that is provisioned into the SAP Build Work Zone, advanced edition user profile using SAP Cloud Identity Services - Identity Provisioning. The default transformation code includes the relevant section in the target transformation that adds the required attribute to the user profile if the `Workzone_Admin` group is assigned in SAP Cloud Identity Services - Identity Authentication:

> ### Sample Code:  
> ```
> {
>             "condition": "$.groups[?(@.display == 'Workzone_Admin')] EMPTY false",
>             "constant": "Administrator",
>             "targetPath": "$.roles[0].value"
>         }
> ```



### SAP SuccessFactors Work Zone

Instead of managing the Company Administrator permission locally, this permission is assigned based on a specific condition. Users that are included in the target system condition – specifically their User ID - are assigned as company administrators.

> ### Sample Code:  
> ```
>  { 
> 		   "condition": "$['urn:sap:cloud:scim:schemas:extension:sfsf:2.0:User']['userSysID'] == '<INSERT USER ID>'", 
> 		   "constant": "Administrator", 
> 		   "targetPath": "$.roles[0].value"
>           } 
> ```



The SAP Build Work Zone, advanced edition SCIM API expects the following attribute in the user profile/payload:

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
> This option is enabled by default for SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone. If you switch to the manual setup as described above, the `Administrator` attribute is ignored.

> ### Note:  
> The Support Administrator as well as other admin roles can't be managed via a SCIM attribute, but only locally.

