<!-- loiob1c760e3566e4d20a89d2ad8eddff838 -->

# Auditing and Logging Information

Here you can find a list of the security events that are logged by this service.



Security events written in audit logs:


<table>
<tr>
<th valign="top">

Event grouping



</th>
<th valign="top">

What events are logged



</th>
<th valign="top">

How to identify related log events



</th>
</tr>
<tr>
<td valign="top" rowspan="4">

Assets



</td>
<td valign="top">

Save asset



</td>
<td valign="top">

```
{
    "configurationChange":{
        "type":"Add asset",
        "id":{
            "key":"'${storeSaveArguments.context}:${storeSaveArguments.asset}`"
        }
    },
    "attribute":{
        "name":"`${storeSaveArguments.context}:${storeSaveArguments.asset}`",
        "locale":"storeSaveArguments.locale",
        "old":"Old",
        "new":"New"
    },
    "by":"storeSaveArguments.triggerUser",
    "tenant":"storeSaveArguments.tenant"
}
```



</td>
</tr>
<tr>
<td valign="top">

Delete asset



</td>
<td valign="top">

```
{
    configurationChange: {
        type: 'Delete asset',
        id: {
            key: asset
        }
    },
    attribute: {
        name: asset,
        old: "Old",
        new: "New"
    },
    by: triggerUser,
    tenant: tenant
};
```



</td>
</tr>
<tr>
<td valign="top">

Delete context



</td>
<td valign="top">

```
{
  configurationChange: {
    type: 'Delete context',
    id: { key: asset },
  },
  attribute: {
    name: asset,
    old: 'Old',
    new: 'New',
  },
  by: triggerUser,
  tenant: tenant,
}
```



</td>
</tr>
<tr>
<td valign="top">

Delete tenant



</td>
<td valign="top">

```
{
  configurationChange: {
    type: 'Delete tenant',
    id: { key: asset },
  },
  attribute: {
    name: asset,
    old: 'Old',
    new: 'New',
  },
  by: triggerUser,
  tenant: tenant,
}
```



</td>
</tr>
<tr>
<td valign="top" rowspan="5">

CDM store service



</td>
<td valign="top">

Batch operation



</td>
<td valign="top">

Operation: %s in global context. id: $\{id\}, type: $\{type\}



</td>
</tr>
<tr>
<td valign="top">

Delete all tenant data



</td>
<td valign="top">

Off-boarding completed



</td>
</tr>
<tr>
<td valign="top">

Delete entities by context \(delete context operation\)



</td>
<td valign="top">

CDM data changed



</td>
</tr>
<tr>
<td valign="top">

Transport in global context



</td>
<td valign="top">

Operation: $\{operation\}, flow name: $\{name\} in global context id: $\{id\}, context type: $\{type\}"



</td>
</tr>
<tr>
<td valign="top">

Import in global context



</td>
<td valign="top">

Operation: $\{operation\}, flow name: $\{name\} in global context id: $\{id\}, context type: $\{type\}"



</td>
</tr>
<tr>
<td valign="top" rowspan="16">

Content package manager service



</td>
<td valign="top">

Async upload content package



</td>
<td valign="top">

Async upload package response: $\{response\}



</td>
</tr>
<tr>
<td valign="top">

Clean orphan tenant data



</td>
<td valign="top">

Cleanup data for orphan tenant.



</td>
</tr>
<tr>
<td valign="top">

Clean unsubscribed tenant data



</td>
<td valign="top">

Cleanup data for unsubscribed tenant



</td>
</tr>
<tr>
<td valign="top">

Create installing deploy job



</td>
<td valign="top">

Installing WorkZone Content Package: $\{packageID\}, version: $\{version\}



</td>
</tr>
<tr>
<td valign="top">

Create uninstalling deploy job



</td>
<td valign="top">

Uninstalling WorkZone Content Package: $\{packageID\}, version: $\{version\}



</td>
</tr>
<tr>
<td valign="top">

Create upgrading deploy job



</td>
<td valign="top">

Upgrading WorkZone Content Package: $\{packageID\}, version: $\{version\}



</td>
</tr>
<tr>
<td valign="top">

Delete local package



</td>
<td valign="top">

Deleted Package: $\{packageID\}



</td>
</tr>
<tr>
<td valign="top">

Get local pacakge status



</td>
<td valign="top">

Get local package : $\{packageID\}, status: $\{status\}



</td>
</tr>
<tr>
<td valign="top">

Finish installing content pacakge



</td>
<td valign="top">

Installed WorkZone Content Package: $\{packageID\}, version: $\{version\}



</td>
</tr>
<tr>
<td valign="top">

Fail to install content pacakge



</td>
<td valign="top">

Failed to install WorkZone Content Package: $\{packageID\}, version: $\{version\}



</td>
</tr>
<tr>
<td valign="top">

Finish upgrading content pacakge



</td>
<td valign="top">

Upgraded WorkZone Content Package: $\{packageID\}, version: $\{version\}



</td>
</tr>
<tr>
<td valign="top">

Fail to upgrade content pacakge



</td>
<td valign="top">

Failed to upgrade WorkZone Content Package: $\{packageID\}, version: $\{version\}



</td>
</tr>
<tr>
<td valign="top">

Finish uninstalling content pacakge



</td>
<td valign="top">

Uninstalled WorkZone Content Package: $\{packageID\}, version: $\{version\}



</td>
</tr>
<tr>
<td valign="top">

Fail to uninstall content pacakge



</td>
<td valign="top">

Failed to uninstall WorkZone Content Package: $\{packageID\}, version: $\{version\}



</td>
</tr>
<tr>
<td valign="top">

Clean orphan tenant data



</td>
<td valign="top">

Cleanup data for orphan tenant.



</td>
</tr>
<tr>
<td valign="top">

Clean unsubscribed tenant data



</td>
<td valign="top">

Cleanup data for unsubscribed tenant.



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Content repository



</td>
<td valign="top">

Add asset



</td>
<td valign="top">

```
{
    "configurationChange":{
        "type":"Add asset",
        "id":{
            "key":"'${storeSaveArguments.context}:${storeSaveArguments.asset}`"
        }
    },
    "attribute":{
        "name":"`${storeSaveArguments.context}:${storeSaveArguments.asset}`",
        "locale":"storeSaveArguments.locale",
        "old":"Old",
        "new":"New"
    },
    "by":"storeSaveArguments.triggerUser",
    "tenant":"storeSaveArguments.tenant"
}
```



</td>
</tr>
<tr>
<td valign="top">

Delete asset



</td>
<td valign="top">

```
{
    configurationChange: {
        type: 'Delete asset',
        id: {
            key: asset
        }
    },
    attribute: {
        name: asset,
        old: "Old",
        new: "New"
    },
    by: triggerUser,
    tenant: tenant
};
```



</td>
</tr>
<tr>
<td valign="top">

OData service



</td>
<td valign="top">

Unauthorized access



</td>
<td valign="top">

An UnAuthorized access to the odata service has been performed. User: $\{userId\}, TenantId: $\{tenantId\}



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Provisioning service



</td>
<td valign="top">

Delete tenant



</td>
<td valign="top">

Off-Boarding completed



</td>
</tr>
<tr>
<td valign="top">

Unsubscribe CF provider



</td>
<td valign="top">

Off-Boarding completed



</td>
</tr>
<tr>
<td valign="top" rowspan="16">

Role mapping



</td>
<td valign="top">

Remove all roles for provider



</td>
<td valign="top">

All roles for providerId $\{providerId\} were deleted successfully



</td>
</tr>
<tr>
<td valign="top">

Remove all users for provider



</td>
<td valign="top">

All users for providerId $\{providerId\} were deleted successfully



</td>
</tr>
<tr>
<td valign="top">

Mark for deletion all roles for provider



</td>
<td valign="top">

All roles for providerId $\{providerId\} were marked for deletion and will be removed by periodic job



</td>
</tr>
<tr>
<td valign="top">

Delete unsubscribed service roles



</td>
<td valign="top">

All $\{entitiesToDelete.roles.length\} unsubscribed service roles were removed successfully



</td>
</tr>
<tr>
<td valign="top">

Delete unsubscribed service users



</td>
<td valign="top">

All $\{entitiesToDelete.users.length\} unsubscribed service users were removed successfully



</td>
</tr>
<tr>
<td valign="top">

Delete orphan roles



</td>
<td valign="top">

All $\{entitiesToDelete.roles.length\} orphan roles were removed successfully



</td>
</tr>
<tr>
<td valign="top">

Delete orphan users



</td>
<td valign="top">

All $\{entitiesToDelete.users.length\} orphan users were removed successfully



</td>
</tr>
<tr>
<td valign="top">

Create role



</td>
<td valign="top">

Role was created successfully with roleId '$\{roleEntity.externalRoleId\}' and providerId '$\{roleEntity.providerId\}



</td>
</tr>
<tr>
<td valign="top">

Delete role



</td>
<td valign="top">

Role with roleId $\{roleId\} was deleted



</td>
</tr>
<tr>
<td valign="top">

Remove user assignments from role



</td>
<td valign="top">

Existing user assignments were removed successfully from role with id $\{roleId\}. The removed user ids are:



</td>
</tr>
<tr>
<td valign="top">

Add user assignments to role



</td>
<td valign="top">

New user assignments were added successfully to role with id $\{roleId\}. The added user ids are:



</td>
</tr>
<tr>
<td valign="top">

Create user



</td>
<td valign="top">

User was created successfully with user email '$\{nonHashedMail\} and hashed email: $\{userEntity.email\}



</td>
</tr>
<tr>
<td valign="top">

Delete user and role assignments



</td>
<td valign="top">

User was deleted successfully with user id '$\{id\}' and hashed email '$\{userEntity.email\}. $\{msgRolesAssignments\}



</td>
</tr>
<tr>
<td valign="top">

Delete user and role assignments



</td>
<td valign="top">

User was deleted successfully with user id '$\{id\}' and externalId '$\{userEntity.email\}. $\{msgRolesAssignments\}



</td>
</tr>
<tr>
<td valign="top">

Remove role assignments from user



</td>
<td valign="top">

Existing role assignments were removed successfully from user with id $\{id\}. The removed role ids are:



</td>
</tr>
<tr>
<td valign="top">

Add role assignments to user



</td>
<td valign="top">

New role assignments were added successfully to user with id $\{id\}. The added role ids are: $\{roleIds.toString\(\)\}



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Site configuration



</td>
<td valign="top">

Save configuration



</td>
<td valign="top">

Save site diff '\[<<DIFF\>\>\]'



</td>
</tr>
<tr>
<td valign="top">

Delete site configuration



</td>
<td valign="top">

Delete site $\{instanceId\} $\{siteId\}



</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Site service storage



</td>
<td valign="top">

Save site



</td>
<td valign="top">

Save site $\{instanceId\} $\{siteId\}



</td>
</tr>
<tr>
<td valign="top">

Save site failed



</td>
<td valign="top">

Save site service failed $\{instanceId\} $\{siteId\}



</td>
</tr>
<tr>
<td valign="top">

Delete site



</td>
<td valign="top">

Delete site $\{instanceId\} $\{siteId\}



</td>
</tr>
<tr>
<td valign="top" rowspan="3">

SPC service



</td>
<td valign="top">

Create provisioning task



</td>
<td valign="top">

SPC registration task completed successfully for scenarioId:iasTenantName:status - '$\{scenarioId\}:$\{iasTenantName\}:$\{status\}'



</td>
</tr>
<tr>
<td valign="top">

Delete provisioning task



</td>
<td valign="top">

Deletion of SPC registration task completed successfully for scenarioId:iasTenantName - '$\{scenarioId\}:$\{iasTenantName\}'



</td>
</tr>
<tr>
<td valign="top">

Set provisioning status



</td>
<td valign="top">

Update of SPC registration task status completed successfully for executionId:status - '$\{executionId\}:$\{status\}'



</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Work Zone HR runtime approuter



</td>
<td valign="top">

Origin is not allowed



</td>
<td valign="top">

Origin $\{originValue\} is not allowed



</td>
</tr>
<tr>
<td valign="top">

Method is not allowed



</td>
<td valign="top">

Method $\{req.method\} is not allowed



</td>
</tr>
<tr>
<td valign="top">

Invalid origin header



</td>
<td valign="top">

Invalid origin header value $\{originURL\}



</td>
</tr>
</table>

