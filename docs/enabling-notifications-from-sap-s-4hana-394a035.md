<!-- loio394a035568854c61ad977808171e93b5 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Enabling Notifications From SAP S/4HANA

Enable publishing notifications from SAP S/4HANA. Users can access the notifications from the shell header of their site and they can act on these notifications.

> ### Note:  
> Email notifications are exclusively managed by SAP S/4HANA and currently they cannot be configured from SAP Build Work Zone, advanced edition.

**Prerequisites**

-   Your SAP S/4HANA system is running version SAP S/4HANA OP-1909 \(SAP\_GWFND-754 SP06\) or above.

-   A user with an assigned *Subaccount Administrator* role must assign the *Business\_Notifications\_Admin* role to the respective [User](https://help.sap.com/docs/btp/sap-business-technology-platform/assign-users-to-role-collections?version=Cloud) or [User Group](https://help.sap.com/docs/btp/sap-business-technology-platform/assign-user-groups-to-role-collections?version=Cloud) role collections. Since this role is not included in any predefined Role Collection, the*Subaccount Administrator* must do one of the following:

    -   [Define a new Role Collection](https://help.sap.com/docs/btp/sap-business-technology-platform/define-role-collection) and [add the Roles to it](https://help.sap.com/docs/btp/sap-business-technology-platform/add-roles-to-role-collection)

    -   [Add the Roles in already existing Role Collection](https://help.sap.com/docs/btp/sap-business-technology-platform/add-roles-to-role-collection?version=Cloud)


-   Notification Channel configuration is applied to your SAP S/4HANA system in the appropriate scenario \(embedded/hub/external\). For more information, see [Notification Channel Configuration](https://help.sap.com/docs/ABAP_PLATFORM_NEW/68bf513362174d54b58cddec28794093/624c610308344f0eb2452b544f969a20.html)


**End-to-End Process**

The following table describes the end-to-end process required to configure notifications from an SAP S/4HANA system:


<table>
<tr>
<th valign="top">

Step

</th>
<th valign="top">

Who?

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

Open the *Site Manager*

</td>
<td valign="top">

SAP Build Work Zone, advanced edition administrator

</td>
<td valign="top">

1.  Under your avatar, click *Administration Console*.

2.  Go to the *External Integrations* section, expand it, and click *Business Content*.

3.  In the screen that opens, click *Content Manager*.

    This takes you to the *Content Manager* screen in the *Site Manager*.




</td>
</tr>
<tr>
<td valign="top">

Select the authentication identifier.

</td>
<td valign="top">

SAP Build Work Zone, advanced edition administrator

</td>
<td valign="top">

Choose the authentication identifier that is relevant to your provider:

From the side panel of the *Site Manager*, click :gear: to open the subaccount settings.

Select the *Notifications* tab.

Under *Authentication Identifier*, either leave the default *Email* identifier or switch to *User ID*, depending on which is relevant for your provider.

Please check that the SAP S/4HANA version that you're using, supports the *User ID* authentication identifier.

For more information, see [Subaccount Settings](subaccount-settings-2d651c7.md) .

</td>
</tr>
<tr>
<td valign="top">

Generate credentials for your service in the subaccount settings screen.

These credentials will be passed to the SAP S/4HANA system to connect between the SAP S/4HANA system and . SAP Build Work Zone, advanced edition.

</td>
<td valign="top">

SAP Build Work Zone, advanced edition administrator

</td>
<td valign="top">

Generate the credentials required to configure the SAP S/4HANA system to push notifications to SAP BTP:

1.  From the *Site Manager* side panel, click :gear: to open the subaccount settings.

2.  Select the *Notifications* tab.

3.  Click *Generate* and copy the values of the generated credentials:

    -   *Host*

    -   *OAuth 2.0 Client ID*

    -   *Client Secret*

    -   *Authorization Endpoint*

    -   *Token Endpoint*



> ### Note:  
> For more information on how to create a OAuth with X509 Certificate authentication type credentials, see: SAP Note [3457591](https://me.sap.com/notes/3457591)

For more information, see [Subaccount Settings](subaccount-settings-2d651c7.md).

</td>
</tr>
<tr>
<td valign="top">

Use the generated credentials to connect between the SAP S/4HANA system and the .

</td>
<td valign="top">

SAP S/4HANA system administrator

</td>
<td valign="top">

Use the credentials as follows:

-   Configure an RFC destination that will enable access to SAP BTP, using the *Host* value. For example:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Connection Type
    
    </td>
    <td valign="top">
    
    G
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Host
    
    </td>
    <td valign="top">
    
    Use the value obtained in the previous step.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Path Prefix
    
    </td>
    <td valign="top">
    
    /v2
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SSL
    
    </td>
    <td valign="top">
    
    Active
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    HTTP Version
    
    </td>
    <td valign="top">
    
    HTTP 1.1
    
    </td>
    </tr>
    </table>
    
-   Configure an OAuth 2.0 client in the AS ABAP to ensure secure communication between the SAP S/4HANA system and SAP BTP, using the following values:

    -   *OAuth 2.0 Client ID*

    -   *Client Secret*

    -   *Authorization Endpoint*

    -   *Token Endpoint*



For more information, see [Configuring an OAuth 2.0 Client in the AS ABAP](https://help.sap.com/docs/SAP_NETWEAVER_750/3c4e8fc004cb4401a4fdd737f02ac2b9/2e5104fd87ff452b9acb247bd02b9f9e.html).

</td>
</tr>
<tr>
<td valign="top">

Configure the Notification Channel Hub for SAP BTP.

</td>
<td valign="top">

SAP S/4HANA system administrator

</td>
<td valign="top">

Configure the Notification Channel Hub for SAP BTP.

For more information, see [Add Push for SAP Business Technology Platform](https://help.sap.com/docs/ABAP_PLATFORM_NEW/68bf513362174d54b58cddec28794093/2012c0f73411425cbc662c27af7d443a.html?locale=en-US).

</td>
</tr>
<tr>
<td valign="top">

Activate sensitive data cache and data encryption

</td>
<td valign="top">

SAP S/4HANA system administrator

</td>
<td valign="top">

Store sensitive information encrypted.

For more information, see [Activate Sensitive Data Cache and Data Encryption](https://help.sap.com/docs/ABAP_PLATFORM_NEW/68bf513362174d54b58cddec28794093/531d796c8539439d9d6dd095209370a8.html?locale=en-US).

</td>
</tr>
<tr>
<td valign="top">

Activate notifications

</td>
<td valign="top">

SAP Build Work Zone, advanced edition administrator.

</td>
<td valign="top">

Activate the *Show Notifications* option in the site’s *Settings* screen.

</td>
</tr>
</table>

\(Optional\) To execute notification-related actions when calling the OData version 4 service in the SAP S/4HANA system, enable the SAP Notification service by performing the following steps:

****


<table>
<tr>
<th valign="top">

Step

</th>
<th valign="top">

Who?

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

Create a new destination towards the notification provider system

</td>
<td valign="top">

SAP BTP account administrator

</td>
<td valign="top">

Create a new destination towards the notification provider system with the following additional properties:

-   `sap-sysid` - system ID of SAP S/4HANA system

-   `sap-client` - client of SAP S/4HANA system

-   `NOTIF_SERVICEPATH` -

    `/sap/opu/odata4/iwngw/notification/default/iwngw/notification_srv/0001`




</td>
</tr>
<tr>
<td valign="top">

To grant access to the SAP S/4HANA system, add the OData version 4 path to the allow-list of the SAP Cloud Connector

</td>
<td valign="top">

SAP Cloud Connector administrator

</td>
<td valign="top">

Add the path `/sap/opu/odata4` to the allow-list of the virtual host configuration in SAP Cloud Connector.

For more information, see [Configure Access Control \(HTTP\)](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e7d4927dbb571014af7ef6ebd6cc3511.html#loioe7d4927dbb571014af7ef6ebd6cc3511__limit).

</td>
</tr>
</table>

