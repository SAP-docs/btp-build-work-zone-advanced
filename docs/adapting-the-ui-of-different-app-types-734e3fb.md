<!-- loio734e3fba9ac7406ebed920082c2119a3 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Adapting the UI of Different App Types

Key user adaptation allows users to make changes at runtime to the user interface of apps directly without having to write new code.



## Prerequisites

Before key user adaptation can be used, the following prerequisites must be in place:

-   The app must be enabled for key user adaptation.

-   The app must be running on a desktop or laptop.

-   The user is assigned to the `FlexKeyUser` role.

    For more information about how to assign a user to this role, see the section below.




<a name="loio734e3fba9ac7406ebed920082c2119a3__section_fll_nxp_2tb"/>

## App types that can support key user adaptation

The following app types support this feature:


<table>
<tr>
<th valign="top">

App Type

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

HTML5 apps

</td>
<td valign="top">

Enable the *Key User Adaptation* setting in the *Site Settings* screen.

For more information, see [Site Settings](site-settings-ca74965.md).

</td>
</tr>
<tr>
<td valign="top">

Launchpad Module apps

</td>
<td valign="top">

For more details, see:

-   [Developing Applications Running Standalone](https://help.sap.com/viewer/0f8b49c4dfc94bc0bda25a19aa93d5b2/Cloud/en-US/7f1c8c8aa7e1487a9d79a0b001e8060b.html).

-   [Developing Applications Running in the SAP Cloud Portal Service](https://help.sap.com/viewer/0f8b49c4dfc94bc0bda25a19aa93d5b2/Cloud/en-US/55433c585c5a43ef96d9b8d4bc4bc464.html).




</td>
</tr>
<tr>
<td valign="top">

SAP S/4HANA apps

</td>
<td valign="top">

SAP S/4HANA apps support this feature if the apps are enabled for key user adaptation.

For more details, see the SAP S/4HANA documentation.

</td>
</tr>
</table>



<a name="loio734e3fba9ac7406ebed920082c2119a3__section_l2b_szp_2tb"/>

## How to assign users to the FlexKeyUser role

The `FlexKeyUser` role is an out-of-the-box role in SAP BTP. To assign this role to users, you need to do the following steps:


<table>
<tr>
<th valign="top">

Step No.

</th>
<th valign="top">

Step Description

</th>
<th valign="top">

Instructions

</th>
</tr>
<tr>
<td valign="top">

**1** 

</td>
<td valign="top">

Create a new role collection.

</td>
<td valign="top">

1.  In the SAP BTP cockpit, navigate to your subaccount.

2.  From the side menu, select *Security* \> *Role Collections*.

3.  Click :heavy_plus_sign: to create a new role collection.

4.  You can call it whatever you like - for example `Key User Adaptation`.




</td>
</tr>
<tr>
<td valign="top">

**2** 

</td>
<td valign="top">

Add the out-of-the-box `FlexKeyUser` role to your role collection.

</td>
<td valign="top">

1.  In the *Role Collections* screen, on the far-right side, click the <span class="SAP-icons-V5"></span> icon to open up the details pane of the role collection.

2.  Click *Edit* at the top right.

3.  In the *Roles* area, browse for the `FlexKeyUser` role, select it from the list, and click *Add*.




</td>
</tr>
<tr>
<td valign="top">

**3** 

</td>
<td valign="top">

Assign users to the `FlexKeyUser` role.

</td>
<td valign="top">

1.  In the *Users* tab, enter the user's ID or email in the *ID* field.

2.  Enter the email address of the user in the *E-Mail* field and click :heavy_plus_sign:.

3.  Save your settings.




</td>
</tr>
</table>

The user is now assigned to the role collection and has all the authorizations of the role collection.

**Related Information**  


[What is UI5 Flexibility for Key Users?](https://help.sap.com/docs/ui5-flexibility-for-key-users/ui5-flexibility-for-key-users/what-is-ui5-flexibility-for-key-users?version=Cloud)

[Adapting SAP Fiori UIs at Runtime - Key User Adaptation](https://help.sap.com/docs/ui5-flexibility-for-key-users/ui5-flexibility-for-key-users/adapting-sap-fiori-uis-at-runtime-key-user-adaptation?version=Cloud)

