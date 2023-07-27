<!-- loioe7966a5a167f4f539e3fc8b1b8977b5f -->

# Creating Imported User Lists

Instruction for how to create an imported user list using the SAP Build Work Zone, advanced edition SCIM API.



Imported user lists are uploaded from another system using SAP Cloud Identity Services - Identity Authentication.

Once the import is complete, the list of users from the source system appears in the *User List* screen under the *Imported User Lists* tab. These lists can be used to invite internal and external users to an external workspace.



<a name="loioe7966a5a167f4f539e3fc8b1b8977b5f__section_wnq_1wp_stb"/>

## How to create an imported user list

Perform a POST request against the SAP Build Work Zone, advanced edition SCIM API **`/api/v1/scim/Groups`** endpoint with the following payload:

```
{
    "schemas": [
        "urn:ietf:params:scim:schemas:core:2.0:Group",
        "urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomGroup"
    ],
    "displayName": "<name>",
    "members": [
        {
            "value": "<id>",
            "type": "user"
        },
        {
            "value": "<id>",
            "type": "user"
        }
        [...]
    ],
    "urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomGroup": {
        "type": "<type>"
    }
}

```

<code><b>&lt;name&gt;</b></code> is the display name of user list shown in the SAP Build Work Zone, advanced edition UI. It can be modified later on, but has to be unique within your environment.

<code><b>&lt;id&gt;</b></code> is the SAP Build Work Zone, advanced edition ID of the user profile that gets generated upon user creation via the SAP Build Work Zone, advanced edition SCIM API & can also be found in the profile URL of each user.

<code><b>&lt;type&gt;</b></code> can be either ‘internal’ \(for internal users\) or ‘external’ \(for external users\).

> ### Note:  
> All this is handled automatically when using the SAP Cloud Identity Services - Identity Provisioning target system configuration for SAP Build Work Zone, advanced edition.

> ### Restriction:  
> Once a user list is created, you can't modify its type – it will then remain either external or internal. In case you try to change it via the SCIM API, the following error will be shown:
> 
> ```
> {
>     "schemas": [
>         "urn:ietf:params:scim:api:messages:2.0:Error"
>     ],
>     "detail": "Changes to property urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomGroup[\"type\"] are not allowed",
>     "status": "400",
>     "scimType": "mutability"
> }
> 
> ```

In order to retrieve the assigned users or other details of a user list via the SAP Build Work Zone, advanced edition SCIM API, simply perform a GET request against <code><b>/api/v1/scim/Groups/&lt;user list id&gt;?attributes=members</b></code>

If the ‘members’ parameter is not provided, the API will return only the metadata of the user list.

For more information about how to manage an imported user list, see [Managing Imported User Lists](managing-imported-user-lists-098d889.md).

