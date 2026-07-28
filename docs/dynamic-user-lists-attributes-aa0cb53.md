<!-- loioaa0cb53e25c044ada2e6d7957eef770e -->

# Dynamic User Lists Attributes

You can configure dynamic user lists based on specific attributes.



## Dynamic User List based on ‘Has Direct Report’

The `Has Direct Report` attribute in the dynamic user list configuration, is based on the employee- manager relationship maintained in the SAP Build Work Zone, advanced edition user profile. This data can be provisioned using Identity Provisioning.

Below you can find two example setups, based on two different source systems. This data \(org chart\) can be enabled in the user profile as per [Profiles](profiles-5c61b54.md)



### Example 1: Identity Authentication as a source system

Identity Authentication source system transformation code:

```
{
            "sourcePath": "$['urn:ietf:params:scim:schemas:extension:enterprise:2.0:User']['manager']['value']",
            "targetPath": "$['urn:ietf:params:scim:schemas:extension:enterprise:2.0:User']['manager']['value']",
            "optional": true
        },
        {
            "sourcePath": "$['urn:ietf:params:scim:schemas:extension:enterprise:2.0:User']['manager']['displayName']",
            "targetPath": "$['urn:ietf:params:scim:schemas:extension:enterprise:2.0:User']['manager']['displayName']",
            "optional": true
        },

```

SAP Build Work Zone, advanced edition target system transformation code:

```
{
                "sourcePath": "$['urn:ietf:params:scim:schemas:extension:enterprise:2.0:User']['manager']['value']",
                "optional": true,
                "targetPath": "$['urn:ietf:params:scim:schemas:extension:enterprise:2.0:User']['manager']['value']",
                "functions": [
                    {+
                        "function": "resolveEntityIds"
                    }
                ]
         }

```



### Example 2: SAP SuccessFactors as a source system

When using SAP SuccessFactors as a source system in Identity Provisioning, there are additional mandatory parameters. For more information, see [SAP SuccessFactors](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/f29b5c6d7edd4f358548233c875ddefd.html?version=Cloud).

For the following parameters:

-   `sf.user.attributes = manager/personKeyNav/perPersonUuid`
-   `sf.user.attributes.expand = manager/personKeyNav`

SAP SuccessFactors source system transformation code is as follows:

```
{
"sourcePath": "$.manager.personKeyNav.perPersonUuid",
  "optional": true,
  "targetPath": "$['urn:ietf:params:scim:schemas:extension:enterprise:2.0:User']['manager']['value']"
}

```

SAP Build Work Zone, advanced edition target system transformation code:

```
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

```



<a name="loioaa0cb53e25c044ada2e6d7957eef770e__section_q2b_r35_wtb"/>

## Dynamic User List based on ‘Hire Date’

You can configure dynamic user lists based on the `hiredate` attribute that is maintained in the user profile in SAP Build Work Zone, advanced edition. The dynamic user list can be configured to look for users with a hire date ‘less than \_ days ago’ or ‘between \_ and \_’. This data can be provisioned using the Identity Provisioning service. The value of this attribute needs to match the ‘DateTime’ format according to [System for Cross-domain Identity Management: Core Schema](https://datatracker.ietf.org/doc/html/rfc7643), when providing the date:

```
"urn:sap:cloud:scim:schemas:extension:custom:2.0:JamWorkforcePerson": {
[…]
"hiredate": "<date>"
}

```

Example <date\>: 2021-01-23T04:56:22Z

**Related Information**  


[Managing Dynamic User Lists](managing-dynamic-user-lists-476b62b.md "A dynamic user list is based on rules that consist of various profile attributes.")

