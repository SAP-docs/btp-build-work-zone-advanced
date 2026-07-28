<!-- loio6bd5237dae344d60b39fa48b644cae87 -->

# Using the SCIM API

This topic provides the information you need about working with the SCIM API.



This guide is equally applicable to SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone. For convenience, we'll use the product name SAP Build Work Zone, advanced edition.

> ### Note:  
> SAP SuccessFactors Work Zone connected to HXM Core \(BizX\) is no longer supported, and since February 2022 all customers need to follow SAP note [0003111415](https://me.sap.com/notes/0003111415) - How to decouple SAP Jam or SAP SuccessFactors Work Zone from BizX, guidelines to switch to the new setup.



<a name="loio6bd5237dae344d60b39fa48b644cae87__section_sdy_nql_4tb"/>

## Introduction

SAP Build Work Zone, advanced edition provides a SCIM 2.0 compliant API, as documented here: [https://tools.ietf.org/wg/scim/](https://tools.ietf.org/wg/scim/). The specification has several optional details; hence the SAP Build Work Zone, advanced edition implementation doesn’t cover all possible optional elements.

When connecting to the SCIM API make sure you're using the Digital Workplace Service URL, not the SAP Build Work Zone, advanced edition subscription URL from SAP BTP. For details on this, see [Solution Architecture](solution-architecture-1fd9ea4.md). While the API endpoint \(/api/v1/scim\) is v1, it's still referring to the SCIM2.0 implementation on the SAP Build Work Zone, advanced edition side.

Querying the SCIM "Schemas" \(/api/v1/scim/Schemas\) endpoint, lists all the properties that SAP Build Work Zone, advanced edition supports. Also, for the Users endpoint the only filter currently supported by SAP Build Work Zone, advanced edition is '`SCIM.userName eq <value>`'.

Finally make sure that JSON strings are sent with double quotes around the strings and not single quotes. The SCIM API defines strings based on the JSON grammar specified here [https://www.json.org/json-en.html](https://www.json.org/json-en.html).

**API End Point examples:**

-   \[POST\] /api/v1/auth/token?grant\_type=client\_credentials - create the token required for the API calls \(must use the details from the specific SCIM OAuth client\)
-   \[GET\] /api/v1/scim/Users?filter=userName eq “ABC123” - retrieve users matching this filter
-   \[PUT\] /api/v1/scim/Users/Eg6CLqEQemJJiuUPPFUKtr - update the user record with a specific SCIM.id



<a name="loio6bd5237dae344d60b39fa48b644cae87__section_fnj_xsl_4tb"/>

## Identity Provisioning

SAP Build Work Zone, advanced edition is supported as a source, proxy, and target system in Identity Provisioning. This is the default and also the officially recommended mechanism to use the SCIM API. For more information, see [SAP Build Work Zone Bundle](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/930015d483a74ee8b68a132db7699825.html).



<a name="loio6bd5237dae344d60b39fa48b644cae87__section_thh_x5l_4tb"/>

## Identity Authentication

The authentication for the SAP Build Work Zone, advanced edition SCIM API is done using 2-legged OAuth. For this purpose, the automatically created OAuth client “Workzone API Client” is used. The client details are provided during the onboarding by the Configurator wizard and then in the Administration Console *External Integrations* \> *OAuth Clients*.

As an admin, you can select the OAuth client used for the SCIM API in the *Features* screen. Once selected, that OAuth client can't be removed or disabled, and you are required to rerun the *Trigger Setup* step in the onboarding Configurator.

The endpoint that should be used to get the OAuth JWT to authenticate to the SCIM API is the *DWS URL*, followed by `/api/v1/auth/token`. You can find the URL in the *Overview* screen of the Administration Console.

```
# OAuth client "Workzone API Client" credentials from WZ OAuth Clients screen in WZ administration console. Using "key" as clientid and "secret" as clientsecret
clientid='WORKZONE_API_CLIENT_KEY_HERE'
clientsecret='WORKZONE_API_CLIENT_SECRET_HERE'
# DWS URL from WZ Administration Console Overview screen
api_endpoint='DWS_SAMPLE URL'

# For the token server, use DWS URL from WZ Administration Console Overview screen followed by /api/v1/auth/token
token_server="$api_endpoint/api/v1/auth/token"

# Get token. Returns token in "access_token" field in JSON response
curl -L -X POST "$token_server" -H 'Content-Type: application/x-www-form-urlencoded' -u "$clientid:$clientsecret" -d 'grant_type=client_credentials'

# Read users 
curl $api_endpoint/api/v1/scim/Users -H 'Authorization: Bearer TOKEN_HERE'

# Read groups
curl $api_endpoint/api/v1/scim/Groups -H 'Authorization: Bearer TOKEN_HERE'
```



<a name="loio6bd5237dae344d60b39fa48b644cae87__section_rkg_gvl_4tb"/>

## Site Maintenance

When the site in under maintenance, the SCIM API will be unavailable. An HTTP 503, "Service Unavailable" will be returned during the maintenance period. Requests should be retried when the maintenance work is over.



<a name="loio6bd5237dae344d60b39fa48b644cae87__section_w5l_kwl_4tb"/>

## Rate and Burst Limits

The SCIM API uses rate limits to enforce throttling. When the rate limits are exceeded, a 429 response is returned. Each request against the API returns headers containing information about the current rate limit values.

-   `X-RateLimit-Limit` is the maximum usage per hour. The default is 12,000 per tenant per hour.
-   `X-RateLimit-Remaining` is the number of units left until reset.
-   `X-RateLimit-Reset` is the number of seconds until reset.

There is also a burst limit of 200 requests per minute. The burst limit is returned as headers with the following parameters:

-   `x-burstratelimit-limit` is the maximum usage per minute.
-   `x-burstratelimit-remaining` is the number of units left until reset.
-   `x-burstratelimit-reset` is the number of seconds until reset.



<a name="loio6bd5237dae344d60b39fa48b644cae87__section_arm_nwl_4tb"/>

## How to Enable and Disable a User

The `SCIM.active` property is used to control whether a user is enabled or disabled. When set to `true`, the user is enabled and `false` means that the user is disabled.



<a name="loio6bd5237dae344d60b39fa48b644cae87__section_z4b_xwl_4tb"/>

## Headers 

Consumers MUST specify the format in which the data is submitted. For all POST/PUT requests to `/api/v1/scim/Users` endpoint and POST/PUT requests to the `/api/v1/scim/Groups` endpoint of the SAP Build Work Zone, advanced edition SCIM API, the content type must be `application/json`.



<a name="loio6bd5237dae344d60b39fa48b644cae87__section_qtv_fh5_wtb"/>

## Profile Attributes

Below you can find a detailed explanation about SAP Build Work Zone, advanced edition profile attributes that can be used in the SCIM API:


<table>
<tr>
<th valign="top">

Profile Attribute

</th>
<th valign="top">

Example of a Value

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

id

</td>
<td valign="top">

Eg6CLqEQemJJiuUPPFUKtr

</td>
<td valign="top">

This is a 22-digit GUID of the SAP Build Work Zone, advanced edition user created automatically.

</td>
</tr>
<tr>
<td valign="top">

userUuid

</td>
<td valign="top">

044c3c7f-2eee-43da-a775-5c7c368aca3e

</td>
<td valign="top">

SCIM schema: "$\['urn:ietf:params:scim:schemas:extension:sap:2.0:User'\]\['userUuid'\]"

This must be the value maintained in the Identity Authentication profile, specifically the "Global User ID" field.

</td>
</tr>
<tr>
<td valign="top">

userName

</td>
<td valign="top">

MUSTER\_M

</td>
<td valign="top">

Used as the primary SCIM attribute, must be unique across SAP Build Work Zone, advanced edition.

</td>
</tr>
<tr>
<td valign="top">

name.firstName

</td>
<td valign="top">

Max

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

name.familyName

</td>
<td valign="top">

Mustermann

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

nickName

</td>
<td valign="top">

Maxi

</td>
<td valign="top">

This data is used for the user profile, if the *Feature Enablement* \> *Features* \> *Use profile information from the SCIM API* is enabled.

</td>
</tr>
<tr>
<td valign="top">

displayName

</td>
<td valign="top">

Max Mustermann \(HR\)

</td>
<td valign="top">

The SCIM API uses the first and last name. If a nickName is provided, it will overwrite the first name. If a displayName is provided, it will overwrite the entire name.

This logic applies to the entire system, like author information in widget, feed, profile page, etc. However, it doesn't apply to design time editors \(Content Manager, Channel Manager, etc.\) and also it doesn't apply to the shell header of the site.

This data is used for the user profile, if the *Feature Enablement* \> *Features* \> *Use profile information from the SCIM API* is enabled.

</td>
</tr>
<tr>
<td valign="top">

title

</td>
<td valign="top">

Inhouse Consultant

</td>
<td valign="top">

Controls the job title field across different elements in SAP Build Work Zone, advanced edition like the user profile and hover card.

</td>
</tr>
<tr>
<td valign="top">

userType

</td>
<td valign="top">

employee

</td>
<td valign="top">

If the user type = `public`, the user is treated as an external user \(if enabled\).

All other users should be of type `employee`.

</td>
</tr>
<tr>
<td valign="top">

roles

</td>
<td valign="top">

Administrator

</td>
<td valign="top">

This is an array and can receive multiple roles.

</td>
</tr>
<tr>
<td valign="top">

locale

</td>
<td valign="top">

de\_DE

</td>
<td valign="top">

Controls login language \(default value\) in profile settings.

</td>
</tr>
<tr>
<td valign="top">

timezone

</td>
<td valign="top">

Europe/Berlin

</td>
<td valign="top">

Controls time-zone \(default value\) in profile settings.

</td>
</tr>
<tr>
<td valign="top">

active

</td>
<td valign="top">

true

</td>
<td valign="top">

When set to `false`, the user will be de-activated and become an alumni.

</td>
</tr>
<tr>
<td valign="top">

emails.value & emails.primary

</td>
<td valign="top">

> ### Sample Code:  
> ```
> "emails": [{
> "value": mail@ondemand.com,
> "primary": true
> }]
> 
> ```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

-   phoneNumbers.value

-   phoneNumbers.type \(mobile, fax, work\)




</td>
<td valign="top">

 

</td>
<td valign="top">

Multiple phone numbers can be provided for a user \(type mobile, fax, or work\).

</td>
</tr>
<tr>
<td valign="top">

-   adresses.streetAddress

-   adresses.locality

-   adresses.region

-   adresses.postalCode

-   adresses.type \(home / work\)

-   adresses.primary




</td>
<td valign="top">

> ### Sample Code:  
> ```
> "addresses": [{
> "streetAddress": "Hasso-Plattner-Ring 7",
> "locality": "Walldorf",
> "region": "Baden-Württemberg",
> "postalCode": "69190",
> "country": "DE",
> "type": "work",
> "primary": true
> }]
> 
> ```



</td>
<td valign="top">

Multiple addresses can be provided for a user \(type home or work\).

The address set to `primary = true` populates the `country` field in SAP Build Work Zone, advanced edition reports run by administrators.

This data is used for the user profile, if the *Feature Enablement* \> *Features* \> *Use profile information from the SCIM API* is enabled.

</td>
</tr>
<tr>
<td valign="top">

employeeNumber

</td>
<td valign="top">

00024680

</td>
<td valign="top">

SCIM schema: "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User“

</td>
</tr>
<tr>
<td valign="top">

costCenter

</td>
<td valign="top">

2715

</td>
<td valign="top">

SCIM schema: "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User“

</td>
</tr>
<tr>
<td valign="top">

organization

</td>
<td valign="top">

SAP Deutschland SE & Co. KG

</td>
<td valign="top">

SCIM schema: "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User“

</td>
</tr>
<tr>
<td valign="top">

division

</td>
<td valign="top">

Services

</td>
<td valign="top">

SCIM schema: "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User“

</td>
</tr>
<tr>
<td valign="top">

department

</td>
<td valign="top">

Services DE

</td>
<td valign="top">

SCIM schema: "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User“

</td>
</tr>
<tr>
<td valign="top">

manager.value

</td>
<td valign="top">

<user ID of manager\>

</td>
<td valign="top">

SCIM schema: "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User“

Will show the SAP Build Work Zone, advanced edition-specific GUID of the manager‘s user.

</td>
</tr>
<tr>
<td valign="top">

externalId

</td>
<td valign="top">

000013579

</td>
<td valign="top">

This is not used for users or for user lists and can't be displayed in the profile.

This is used for:

-   User mapping in external integration scenarios like for instance SAP SuccessFactors Learning.

-   User mapping in the SAP UI5 cards for the HR content package of SAP SuccessFactors Work Zone \(with the SAP SuccessFactors User Id\).




</td>
</tr>
<tr>
<td valign="top">

username

</td>
<td valign="top">

musterm

</td>
<td valign="top">

SCIM schema: "urn:sap:cloud:scim:schemas:extension:custom:2.0:JamWorkforcePerson“

Created to store SAP SuccessFactors User Name from the Employee Profile.

</td>
</tr>
<tr>
<td valign="top">

jobcode

</td>
<td valign="top">

HR Professional \(50029122\)

</td>
<td valign="top">

SCIM schema: "urn:sap:cloud:scim:schemas:extension:custom:2.0:JamWorkforcePerson“

</td>
</tr>
<tr>
<td valign="top">

location

</td>
<td valign="top">

Corporate - DE-Walldorf \(1710-2001\)

</td>
<td valign="top">

SCIM schema: "urn:sap:cloud:scim:schemas:extension:custom:2.0:JamWorkforcePerson“

</td>
</tr>
<tr>
<td valign="top">

hiredate

</td>
<td valign="top">

2011-08-01T21:32:44.882Z

</td>
<td valign="top">

SCIM schema: "urn:sap:cloud:scim:schemas:extension:custom:2.0:JamWorkforcePerson“

</td>
</tr>
<tr>
<td valign="top">

gender

</td>
<td valign="top">

M

</td>
<td valign="top">

SCIM schema: "urn:sap:cloud:scim:schemas:extension:custom:2.0:JamWorkforcePerson“

</td>
</tr>
<tr>
<td valign="top">

-   customAttribute1-20.name

-   customAttribute1-20.value




</td>
<td valign="top">

> ### Sample Code:  
> ```
> "customAttribute5": {
> "name": "Initials",
> "value": “MM"
> },
> 
> ```



</td>
<td valign="top">

SCIM schema: "urn:sap:cloud:scim:schemas:extension:custom:2.0:JamCustomUser“

Up to 20 custom attributes can be populated in the user profile to display on the profile, use for search, and define dynamic user lists based on them.

Name and value can be modified, the name is used across all users \(for a given custom attribute\).

For more information, see [Managing Custom Profile Attributes](managing-custom-profile-attributes-796e3d9.md).

</td>
</tr>
</table>

