<!-- loiocbe83ddde516407ea58aeb0e5a22028b -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Enabling Notifications From Cloud Solutions and Services

Enable publishing notifications from cloud solutions. Users can access the notifications from the shell header of their site.



<a name="loiocbe83ddde516407ea58aeb0e5a22028b__section_ppt_1pp_dyb"/>

## Prerequisites

A user with an assigned *Subaccount Administrator* role must assign the *Business\_Notifications\_Admin* role to the respective [User](https://help.sap.com/docs/btp/sap-business-technology-platform/assign-users-to-role-collections?version=Cloud) or [User Group](https://help.sap.com/docs/btp/sap-business-technology-platform/assign-user-groups-to-role-collections?version=Cloud) role collections. Since this roles is not included in any predefined Role Collection, the*Subaccount Administrator* must do one of the following:

-   [Define a new Role Collection](https://help.sap.com/docs/btp/sap-business-technology-platform/define-role-collection) and [add the Roles to it](https://help.sap.com/docs/btp/sap-business-technology-platform/add-roles-to-role-collection)

-   [Add the Roles in already existing Role Collection](https://help.sap.com/docs/btp/sap-business-technology-platform/add-roles-to-role-collection?version=Cloud)




## Overview

The cloud solutions include:

-   SAP S/4HANA Cloud solution

-   SAP Integrated Business Planning for Supply Chain \(SAP IBP\)

-   SAP BTP, ABAP environment


The SAP BTP services include:

-   SAP Task Center


The overall process for enabling notifications is as follows:


<table>
<tr>
<th valign="top">

Step

</th>
<th valign="top">

Who does it?

</th>
<th valign="top">

More information

</th>
</tr>
<tr>
<td valign="top">

Open the *Site Manager*

</td>
<td valign="top">

Administrator

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

Choose the authentication identifier.

</td>
<td valign="top">

Administrator

</td>
<td valign="top">

Choose the authentication identifier that is relevant for your provider as follows:

1.  From the side panel of the *Site Manager*, click :gear: to open the subaccount settings.

2.  Select the *Notifications* tab.

3.  Under *Authentication Identifier*, either leave the default *Email* identifier or switch to *User ID*, depending on which is relevant for your provider.

For more information, see [Subaccount Settings](subaccount-settings-2d651c7.md).

</td>
</tr>
<tr>
<td valign="top">

Generate credentials for your service in the subaccount settings screen.

These credentials are used to connect between your system and SAP Build Work Zone, advanced edition.

</td>
<td valign="top">

Administrator

</td>
<td valign="top">

To generate the credentials, do the following:

1.  Open your SAP Build Work Zone, advanced edition.

2.  From the side panel, click :gear: to open the subaccount settings.

3.  Select the *Notifications* tab.

4.  Click *Generate* and copy the values of the generated credentials:

    -   *Host*

    -   *OAuth 2.0 Client ID*

    -   *Client Secret*

    -   *Authorization Endpoint*

    -   *Token Endpoint*



> ### Note:  
> If you regenerate these credentials, you must update them in the notifications destination, created in the next step.

> ### Note:  
> For more information on how to create a OAuth with X509 Certificate authentication type credentials, see: SAP Note [3457591](https://me.sap.com/notes/3457591)

For more information, see [Subaccount Settings](subaccount-settings-2d651c7.md).

</td>
</tr>
<tr>
<td valign="top">

Configure communication between your system and the SAP Build Work Zone, advanced edition using the credentials you've just generated.

</td>
<td valign="top">

Administrator

</td>
<td valign="top">

-   SAP S/4HANA Cloud system

    For more information, see [Enabling Notifications from SAP S/4HANA Cloud in Launchpads running on SAP BTP.](https://help.sap.com/docs/SAP_S4HANA_CLOUD/0f69f8fb28ac4bf48d2b57b9637e81fa/1c71f7476c854efc882d4d94514551fc.html)

-   SAP IBP system

    For more information, see [Enabling Notifications from SAP IBP in SAP Launchpad Service.](https://help.sap.com/docs/SAP_INTEGRATED_BUSINESS_PLANNING/da797ae2bf6246d58abd417f24915d55/431b95bc97204f25a4b62636723d5647.html)

-   SAP BTP, ABAP environment

    For more information, see [Enabling Notifications on SAP BTP, ABAP Environment in Launchpads Running on SAP BTP.](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/ba62b2a7a124454e8f4813137ac91639.html)

-   SAP Task Center

    For more information, see [Enable Notifications for End Users](https://help.sap.com/docs/task-center/sap-task-center/enable-notifications-for-end-users)




</td>
</tr>
<tr>
<td valign="top">

Enable the display of notifications in the *Site Settings* screen.

</td>
<td valign="top">

Administrator

</td>
<td valign="top">

Enable the display of the notifications as follows:

1.  From the Site Manager of your site, click :globe_with_meridians: to open the Site Directory.

2.  Click :gear: on the site's tile.

3.  Enable *Show Notifications* under the *Display* section of your settings screen.

4.  Click *Save*.




</td>
</tr>
<tr>
<td valign="top">

Select the notifications.

> ### Note:  
> Users select the notifications that they want to receive.



</td>
<td valign="top">

User

</td>
<td valign="top">

Open user *Settings* \> *Notifications*

![The notification options in the Settings dialog box.](images/User_Settings_notifications_d53363c.png)

</td>
</tr>
<tr>
<td valign="top">

Open the notifications

</td>
<td valign="top">

User

</td>
<td valign="top">

In the shell header of your site, click the notifications icon:

![The bell icon of the notifications on the right side of the header bar.](images/Notification_icon_in_site_header_8a022aa.png)

</td>
</tr>
</table>

> ### Note:  
> Performing actions for notifications is not supported.



<a name="loiocbe83ddde516407ea58aeb0e5a22028b__section_xms_yxy_sxb"/>

## Configure Email Notifications Using Custom SMTP Server

If you want to receive an email notification, you need to configure custom SMTP destination. Proceed as described in [Configuring an SMTP Mail Destination](configuring-an-smtp-mail-destination-e403f2c.md).

