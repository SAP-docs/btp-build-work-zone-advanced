<!-- loio1c88797e768b456a83791fd2529fab25 -->

# Allow SAML Assertion-Based Creation of External Users

Administrators can enable the creation of external users using SAML assertion.



When enabled, allow SAML assertion-based creation of external users based on their initial login via the connected IdP in addition to creating them via the SCIM API.

You enable this option in the Administration Console *Feature Enablement* \> *Features* \> *Feature Management*. Select the option *Allow SAML assertion-based creation of external users*.

To create external users, use the following attributes:


<table>
<tr>
<th valign="top">

Assertion Attribute for BTP <\> Identity Authentication/IDS trust



</th>
<th valign="top">

Assertion Attribute \(sent to DWS\)



</th>
<th valign="top">

Mapped SCIM attribute DWS



</th>
<th valign="top">

Comments



</th>
</tr>
<tr>
<td valign="top">

```
<NameID Format="urn:oasis
:names:tc:SAML:1.1:
nameid-format:unspecified"
>ID2714</NameID>
```



</td>
<td valign="top">

```
<saml2:NameID Format="urn:oasis
:names:tc:SAML:1.1:
nameid-format:emailAddress"
>mail@ondemand.com</saml2:NameID>
```



</td>
<td valign="top">

`SCIM.userName`



</td>
<td valign="top">

Impacted by "userIdSource" property of "JAM" destination; should be used as the userName on DWS side as this is the unique attribute coming from the SAML assertion.

email = NameID:emailAddress - email

user\_uuid = NameID:unspecified - Identity Authentication/IDS User UUID

$\['user\_attributes'\]\['user\_name'\]\[0\] = NameID:unspecified - Identity Authentication/IDS Login Name \(configured as user\_name\)



</td>
</tr>
<tr>
<td valign="top">

`email`



</td>
<td valign="top">

`user_attributes.email`



</td>
<td valign="top">

`SCIM.emails.value`



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

`first_name`



</td>
<td valign="top">

`user_attributes.given_name`



</td>
<td valign="top">

`SCIM.name.firstName`



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

`last_name`



</td>
<td valign="top">

`user_attributes.family_name`



</td>
<td valign="top">

`SCIM.name.familyName`



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

`type`



</td>
<td valign="top">

`user_attributes.type`



</td>
<td valign="top">

`SCIM.userType`



</td>
<td valign="top">

Should always be public on DWS side to ensure user is external.



</td>
</tr>
<tr>
<td valign="top">

`/`



</td>
<td valign="top">

`xs.rolecollections`



</td>
<td valign="top">

`/`



</td>
<td valign="top">

Role collections mapped on different attributes from Identity Authentication, for example, type=public. There can be multiple \(non-SAP Build Work Zone\) role collections assigned to the user on the subaccount, for instance for accessing other applications. DWS will only create external users with \(at least\) role collection Workzone\_External\_User assigned!



</td>
</tr>
</table>

