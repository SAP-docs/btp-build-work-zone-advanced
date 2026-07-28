<!-- loiob1c760e3566e4d20a89d2ad8eddff838 -->

# Auditing and Logging Information

Here you can find a list of the security events that are logged by this service.



> ### Note:  
> Use the audit log viewer to display the audit logs.
> 
> For more information, see [Audit Log Viewer for Cloud Foundry Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/audit-log-viewer-for-cloud-foundry-environment?&version=Cloud).

The following table describes the security events written to the audit log:


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
<td valign="top">

Admin backend administration

</td>
<td valign="top">

Switch from SAP Authorization and Trust Management service \(XSUAA\) to Identity Authentication

</td>
<td valign="top">

Configuration modification message.

Attribute with name "Authentication Method" was changed from "SAP Authorization and Trust Management service \(XSUAA\)" to "Identity Authentication".

The attribute is a part of an object with type "Authentication" and id consisting of: key "Tenant: $\{tenant\}.

</td>
</tr>
<tr>
<td valign="top">

Alias mapping \(semantic\)

</td>
<td valign="top">

Map system aliases

</td>
<td valign="top">

Set local system aliases: $\{system alias object\}

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

CDM export service

</td>
<td valign="top">

Export entities – zip

</td>
<td valign="top">

Exported entities were saved to file $\{filename\}

</td>
</tr>
<tr>
<td valign="top">

Export Site – zip

</td>
<td valign="top">

Content of site with siteId $\{siteId\} was saved to file $\{filename\}

</td>
</tr>
<tr>
<td valign="top">

Export entities – ctms

</td>
<td valign="top">

Exported entities were saved to file $\{filename\}

</td>
</tr>
<tr>
<td valign="top">

Export Site – ctms

</td>
<td valign="top">

Content of site with siteId $\{siteId\} was saved to file $\{filename\}

</td>
</tr>
<tr>
<td valign="top" rowspan="6">

CDM store service

</td>
<td valign="top">

Batch operation

</td>
<td valign="top">

\{0\} Operation: \{1\}, entity id: \{2\}, entity type: \{3\}, context id: \{4\}, context type: \{5\}

</td>
</tr>
<tr>
<td valign="top">

Delete all tenant data

</td>
<td valign="top">

All tenant data was deleted. Off boarding the tenant is complete.

</td>
</tr>
<tr>
<td valign="top">

Delete entities by context \(delete context operation\)

</td>
<td valign="top">

Entities were deleted from context.

</td>
</tr>
<tr>
<td valign="top">

Transport in global context

</td>
<td valign="top">

Operation: \{operationName\}, flow name: \{flowName\} in global context id: \{contextId\}, context type: \{contextType\}

</td>
</tr>
<tr>
<td valign="top">

Import in global context

</td>
<td valign="top">

Operation: \{operationName\}, flow name: \{flowName\} in global context id: \{contextId\}, context type: \{contextType\}

</td>
</tr>
<tr>
<td valign="top">

Automatic assignment of roles to sites

</td>
<td valign="top">

Relation added \{counter\}

</td>
</tr>
<tr>
<td valign="top" rowspan="10">

Content API

</td>
<td valign="top">

Create a workPage

</td>
<td valign="top">

Created workPage with ID: \{id\}

</td>
</tr>
<tr>
<td valign="top">

Update a workPage

</td>
<td valign="top">

Updated workPage with ID: \{id\}

</td>
</tr>
<tr>
<td valign="top">

Delete a workPage

</td>
<td valign="top">

Deleted workPage with ID: \{id\}

</td>
</tr>
<tr>
<td valign="top">

Create a space

</td>
<td valign="top">

Created space with ID: \{id\}

</td>
</tr>
<tr>
<td valign="top">

Update a space

</td>
<td valign="top">

Updated space with ID: \{id\}

</td>
</tr>
<tr>
<td valign="top">

Delete a space

</td>
<td valign="top">

Deleted space with ID: \{id\}

</td>
</tr>
<tr>
<td valign="top">

assignWorkPagesToSpaces

</td>
<td valign="top">

workPages with IDs: \{workPageIds\} were assigned from spaces with IDs: \{spaceIds\}

</td>
</tr>
<tr>
<td valign="top">

unAssignWorkPagesFromSpaces

</td>
<td valign="top">

workPages with IDs: \{workPageIds\} were unassigned from spaces with IDs: \{spaceIds\}

</td>
</tr>
<tr>
<td valign="top">

Configure site

</td>
<td valign="top">

Created site configuration for site with ID: \{id\}

</td>
</tr>
<tr>
<td valign="top">

Configure theme

</td>
<td valign="top">

Configure theme for site with ID: \{id\}

</td>
</tr>
<tr>
<td valign="top" rowspan="10">

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

Upload content package

</td>
<td valign="top">

Uploaded Package: $\{packageID\}, version: $\{version\}

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

Get local package status

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

Finish upgrading content package

</td>
<td valign="top">

Upgraded WorkZone Content Package: $\{packageID\}, version: $\{version\}

</td>
</tr>
<tr>
<td valign="top">

Finish uninstalling content package

</td>
<td valign="top">

Uninstalled WorkZone Content Package: $\{packageID\}, version: $\{version\}

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Content package store

</td>
<td valign="top">

Upload content package

</td>
<td valign="top">

Uploaded content package package:sap.start.cpkg.test

</td>
</tr>
<tr>
<td valign="top">

Delete content package

</td>
<td valign="top">

Deleted content package package:sap.start.cpkg.test

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Content repository

</td>
<td valign="top">

Add card

</td>
<td valign="top">

Data Modification message. Attribute with name $\{ context \}:$\{ asset \} was changed from "Old" to "New". The attribute is a part of an object with type "Add card" and id consisting of: key $\{ context \}:$\{ asset \}. It belongs to a subject with type "Add card", and id consisting of: key $\{ context \}:$\{ asset \}.

</td>
</tr>
<tr>
<td valign="top">

Delete card

</td>
<td valign="top">

Data Modification message. Attribute with name $\{ asset \} was changed from "Old" to "New". The attribute is a part of an object with type "Delete card" and id consisting of: key $\{ asset \}. It belongs to a subject with type "Delete card", and id consisting of: key $\{ asset \}.

</td>
</tr>
<tr>
<td valign="top" rowspan="6">

Menu options

</td>
<td valign="top">

Publish config

</td>
<td valign="top">

Data Modification message. Attribute with name "menu\_config" and value "publish" was added. The attribute is a part of an object with type "MenuConfig" and id consisting of: company\_uuid "$\{company\_uuid\}". It belongs to a subject with type "company", and id consisting of: company\_uuid "$\{company\_uuid\}”.

</td>
</tr>
<tr>
<td valign="top">

Discard draft

</td>
<td valign="top">

Data Modification message. Attribute with name "menu\_config" and value "discard\_draft" was added. The attribute is a part of an object with type "MenuConfig" and id consisting of: company\_uuid "$\{company\_uuid\}". It belongs to a subject with type "company", and id consisting of: company\_uuid "$\{company\_uuid\}”.

</td>
</tr>
<tr>
<td valign="top">

Save draft

</td>
<td valign="top">

Data Modification message. Attribute with name "menu\_config" and value "save\_draft" was added. The attribute is a part of an object with type "MenuConfig" and id consisting of: company\_uuid "$\{company\_uuid\}". It belongs to a subject with type "company", and id consisting of: company\_uuid "$\{company\_uuid\}”.

</td>
</tr>
<tr>
<td valign="top">

Revert version

</td>
<td valign="top">

Data Modification message. Attribute with name "menu\_config" and value "revert" was added. The attribute is a part of an object with type "MenuConfig" and id consisting of: company\_uuid "$\{company\_uuid\}". It belongs to a subject with type "company", and id consisting of: company\_uuid "$\{company\_uuid\}”.

</td>
</tr>
<tr>
<td valign="top">

Export menu config

</td>
<td valign="top">

Data Modification message. Attribute with name "menu\_config" and value "export" was added. The attribute is a part of an object with type "MenuConfig" and id consisting of: company\_uuid "$\{company\_uuid\}". It belongs to a subject with type "company", and id consisting of: company\_uuid "$\{company\_uuid\}”.

</td>
</tr>
<tr>
<td valign="top">

Import menu config

</td>
<td valign="top">

Data Modification message. Attribute with name "menu\_config" and value "import" was added. The attribute is a part of an object with type "MenuConfig" and id consisting of: company\_uuid "$\{company\_uuid\}". It belongs to a subject with type "company", and id consisting of: company\_uuid "$\{company\_uuid\}”.

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

Unauthorized access to the oData service has been performed by user $\{userId\} in tenant $\{tenantId\}

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Provisioning

</td>
<td valign="top">

Set tenant property

</td>
<td valign="top">

Configuration modification message.

Attribute with name <key\> was changed from "Old" to "New".

The attribute is part of an object with type <operation\> item and id consisting of key <key\>.

</td>
</tr>
<tr>
<td valign="top">

Delete tenant property

</td>
<td valign="top">

Configuration modification message.

Attribute with name <key\> was changed from "Old" to "New".

The attribute is part of an object with type <operation\> item and id consisting of key <key\>.

</td>
</tr>
<tr>
<td valign="top">

Task writing to audit log

</td>
<td valign="top">

\`\[$\{taskName\}\] - writing to audit log before starting flow\`

</td>
</tr>
<tr>
<td valign="top" rowspan="23">

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

Delete unsubscribed service cdm roles

</td>
<td valign="top">

All $\{entitiesToDelete.cdmRoles.length\} unsubscribed service cdm roles were removed successfully

</td>
</tr>
<tr>
<td valign="top">

Create role

</td>
<td valign="top">

Role was created successfully with roleId $\{roleEntity.externalRoleId\} and providerId $\{roleEntity.providerId\}

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

Existing user assignments were removed successfully from role with id $\{roleId\}. The removed user ids are: $\{userIds.toString\(\)\}

</td>
</tr>
<tr>
<td valign="top">

Add user assignments to role

</td>
<td valign="top">

New user assignments were added successfully to role with id $\{roleId\}. The added user ids are: $\{userIds.toString\(\)\}

</td>
</tr>
<tr>
<td valign="top">

Create user with email

</td>
<td valign="top">

User was created successfully with user email $\{nonHashedMail\} and hashed email $\{userEntity.email\}

</td>
</tr>
<tr>
<td valign="top">

Create user with external ID

</td>
<td valign="top">

User was created successfully with user externalId $\{userEntity.externalUserId\}

</td>
</tr>
<tr>
<td valign="top">

Delete user and role assignments

</td>
<td valign="top">

User was deleted successfully with user id $\{id\} and hashed email $\{userEntity.email\}. $\{msgRolesAssignments\}

</td>
</tr>
<tr>
<td valign="top">

Delete user and role assignments

</td>
<td valign="top">

User was deleted successfully with user id $\{id\} and externalId $\{userEntity.email\}. $\{msgRolesAssignments\}

</td>
</tr>
<tr>
<td valign="top">

Remove role assignments from user

</td>
<td valign="top">

Existing role assignments were removed successfully from user with id $\{id\}. The removed role ids are: $\{roleIds.toString\(\)\}

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
<td valign="top">

Update user

</td>
<td valign="top">

User was updated successfully with user email $\{nonHashedMail\}, hashed email $\{userEntity.email\} and user externalId $\{userEntity.externalUserId\}

</td>
</tr>
<tr>
<td valign="top">

Create all snapshot roles for provider in "cdm-roles" table

</td>
<td valign="top">

All snapshot roles for providerId $\{providerId\} were created successfully from "cdm-roles" table

</td>
</tr>
<tr>
<td valign="top">

Delete all snapshot roles for provider from "cdm-roles" table

</td>
<td valign="top">

All snapshot roles for providerId $\{providerId\} were deleted successfully from "cdm-roles" table

</td>
</tr>
<tr>
<td valign="top">

Remove all snapshot roles for provider from "cdm-roles" table

</td>
<td valign="top">

All snapshot roles for providerId $\{providerId\} were deleted successfully from "cdm-roles" table

</td>
</tr>
<tr>
<td valign="top">

Remove all roles for provider from "roles" table

</td>
<td valign="top">

All roles for providerId $\{providerId\} were deleted successfully from "roles" table

</td>
</tr>
<tr>
<td valign="top">

Remove all users from "users" table for provider

</td>
<td valign="top">

All users for providerId $\{providerId\} were deleted successfully from "users" table

</td>
</tr>
<tr>
<td valign="top">

Mark for deletion all roles from "roles" table for provider

</td>
<td valign="top">

All roles for providerId $\{providerId\} were marked for deletion and will be removed from "roles" table by periodic job

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Runtime approuter

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
<tr>
<td valign="top" rowspan="4">

Service broker

</td>
<td valign="top">

Create instance

</td>
<td valign="top">

Service $\{serviceId\} with plan $\{planId\} is being provisioned

</td>
</tr>
<tr>
<td valign="top">

Delete instance

</td>
<td valign="top">

Service $\{serviceId\} with plan $\{planId\} is being deprovisioned

</td>
</tr>
<tr>
<td valign="top">

Bind instance

</td>
<td valign="top">

Service $\{serviceId\} with plan $\{planId\} is being bound

</td>
</tr>
<tr>
<td valign="top">

Unbind instance

</td>
<td valign="top">

Service $\{serviceId\} with plan $\{planId\} is being unbound

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Site configuration

</td>
<td valign="top">

Save site configuration

</td>
<td valign="top">

Data Modification message.

Attribute with name "Save Site Configuration" was changed.

The attribute is a part of an object with type "Site" and id consisting of: key $\{siteId\}.

It belongs to a subject with type "Instance", and id consisting of: key $\{instanceId\}

See changes: $\{siteDiff\}.

</td>
</tr>
<tr>
<td valign="top">

Delete site configuration

</td>
<td valign="top">

Data Modification message.

Attribute with name "Delete Site Configuration" was changed.

The attribute is a part of an object with type "Site" and id consisting of: key $\{siteId\}.

It belongs to a subject with type "Instance", and id consisting of: key $\{instanceId\}.

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Site service storage

</td>
<td valign="top">

Save site data

</td>
<td valign="top">

Data Modification message.

Attribute with name "Save Site Data" was changed.

The attribute is a part of an object with type "Site" and id consisting of: key $\{siteId\}.

It belongs to a subject with type "Instance", and id consisting of: key $\{instanceId\}.

</td>
</tr>
<tr>
<td valign="top">

Delete site data

</td>
<td valign="top">

Data Modification message.

Attribute with name "Delete Site Data" was changed.

The attribute is a part of an object with type "Site" and id consisting of: key $\{siteId\}.

It belongs to a subject with type "Instance", and id consisting of: key $\{instanceId\}.

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

SPC service

</td>
<td valign="top">

Create SPC registration task

</td>
<td valign="top">

SPC registration task completed successfully for scenarioId:iasTenantName:status - '$\{scenarioId\}:$\{iasTenantName\}:$\{status\}'

</td>
</tr>
<tr>
<td valign="top">

Delete SPC registration task

</td>
<td valign="top">

Deletion of SPC registration task completed successfully for scenarioId:iasTenantName - '$\{scenarioId\}:$\{iasTenantName\}'

</td>
</tr>
<tr>
<td valign="top">

Update SPC registration task status

</td>
<td valign="top">

Update of SPC registration task status completed successfully for executionId:status - '$\{executionId\}:$\{status\}'

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

User Profile

</td>
<td valign="top">

Add profile fields

</td>
<td valign="top">

Data Modification message.

Attribute with name $\{name\} and value $\{value1\} was added.

The attributes are a part of an object with type $\{type\_name\} and id consisting of: company\_id $\{id\}, member\_id $\{id\}.

They belong to a subject with type $\{data\_type\}, role $\{role\}, and id consisting of: member\_uuid $\{uuid\}, first name $\{first\_name\}, last name $\{last\_name\}.

</td>
</tr>
<tr>
<td valign="top">

Change profile fields

</td>
<td valign="top">

Data Modification message.

Attribute with name $\{name\} was changed from $\{value1\} to $\{value2\}.

The attributes are a part of an object with type $\{type\_name\} and id consisting of: uuid $\{uuid\}.

They belong to a subject with type $\{data\_type\}, role $\{role\}, and id consisting of: member\_id $\{uuid\}, first name $\{first\_name\}, last name $\{last\_name\}.

</td>
</tr>
<tr>
<td valign="top">

Remove profile fields

</td>
<td valign="top">

Data Modification message.

Attribute with name $\{name\} and value $\{value1\} was deleted.

The attribute is a part of an object with type $\{type\_name\} and id consisting of: uuid $\{uuid\}.

It belongs to a subject with type $\{type\_name\}, role $\{role\}, and id consisting of: member\_id $\{uuid\}, first name $\{first\_name\}, last name $\{last\_name\}.

</td>
</tr>
</table>

