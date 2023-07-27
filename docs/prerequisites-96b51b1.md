<!-- loio96b51b1aaf8349b5a053c56ec6d6fe19 -->

# Prerequisites

Complete the following steps before executing the SAP SuccessFactors Work Zone booster.



<a name="loio96b51b1aaf8349b5a053c56ec6d6fe19__section_kht_y4q_qlb"/>

## Create a Subaccount

In this step, you'll create a subaccount in SAP BTP, Cloud Foundry Environment \(if you don't have one already\).

> ### Note:  
> Before you create a subaccount, check if you're currently using cloud management tools feature set A or B. For more information, see [Cloud Management Tools — Feature Set Overview](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/caf4e4e23aef4666ad8f125af393dfb2.html)

> ### Note:  
> Having subscriptions on both SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone on the same subaccount isn't supported. If you are already using SAP Build Work Zone, advanced edition in your subaccount, you will need to either choose a different subaccount or unsubscribe before you on board to SAP SuccessFactors Work Zone.



### Create a subaccount

For optimal performance and to **avoid latency issues**, create the subaccount on the recommended data center according to this table. If your data center is not listed, select the closest location for optimal performance.

When subscribing to either SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone, the selection of the Cloud Foundry region is important.

-   When using an existing SAP Jam system that should be upgraded, column \[C / 3\] should be looked at to find the suggested data center mapping for the subscription \(column \[A / 1\]\).
-   When setting up SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone from scratch, the deployment of the DWS\*\* component in column \[D / 4\] should be considered in addition.


<table>
<tr>
<th valign="top">

\[A\] SAP BTP, Cloud Foundry Environment Data Center



</th>
<th valign="top">

\[B\] SAP BTP, Cloud Foundry Environment Infrastructure Provider



</th>
<th valign="top">

\[C\] Existing SAP Jam / SAP SuccessFactors Data Center\*



</th>
<th valign="top">

\[D\] New customers setup for DWS\*\* component Data Center



</th>
</tr>
<tr>
<td valign="top">

cf-eu20 - Europe \(Netherlands\)



</td>
<td valign="top">

Azure



</td>
<td valign="top">

-   DC02 \(DC57\) – Eemshaven
-   DC12 \(DC33\) – Frankfurt
-   DC22 – Dubai
-   DC23 – Riyadh
-   DC55 – Frankfurt



</td>
<td valign="top">

DC02 \(DC57\) - Eemshaven



</td>
</tr>
<tr>
<td valign="top">

cf-us20 - US West \(WA\)



</td>
<td valign="top">

Azure



</td>
<td valign="top">

DC04 \(DC68\) - Virginia



</td>
<td valign="top">

DC04 \(DC68\) - Virginia



</td>
</tr>
<tr>
<td valign="top">

cf-us21 - US East \(VA\)



</td>
<td valign="top">

Azure



</td>
<td valign="top">

-   DC47 - Canada
-   DC41 - East US



</td>
<td valign="top">

DC41 - East US



</td>
</tr>
<tr>
<td valign="top">

cf-jp20 – Japan \(Tokyo\)



</td>
<td valign="top">

Azure



</td>
<td valign="top">

DC50 – GCP Tokyo



</td>
<td valign="top">

DC50 – GCP Tokyo



</td>
</tr>
<tr>
<td valign="top">

cf-us10 - US East \(VA\)

**Includes SAP Build Process Automation**



</td>
<td valign="top">

AWS



</td>
<td valign="top">

-   DC08 \(DC70\) – Virginia
-   DC60 – Canada Central



</td>
<td valign="top">

-   Setup prior to November 28th, 2022:

    DC08 \(DC70\) – Virginia

-   Setup after November 28th, 2022:

    AWS deployment us10




</td>
</tr>
<tr>
<td valign="top">

cf-ap10 - Australia \(Sydney\)

**Includes SAP Build Process Automation**



</td>
<td valign="top">

AWS



</td>
<td valign="top">

DC10 \(DC66\) - Sydney



</td>
<td valign="top">

-   Setup prior to January 3rd, 2023:

    DC10 \(DC66\) - Sydney

-   Setup after January 3rd, 2023:

    AWS deployment ap10




</td>
</tr>
<tr>
<td valign="top">

cf-eu10 - Europe \(Frankfurt\)

**Includes SAP Build Process Automation**



</td>
<td valign="top">

AWS



</td>
<td valign="top">

-   DC02 \(DC57\) - Eemshaven
-   DC12 \(DC33\) – Frankfurt
-   DC22 – Dubai
-   DC23 – Riyadh
-   DC55 – Frankfurt



</td>
<td valign="top">

-   Setup prior to January 3rd, 2023:

    DC12 \(DC33\) – Frankfurt

-   Setup after January 3rd, 2023:

    AWS deployment eu10




</td>
</tr>
<tr>
<td valign="top">

**cf-eu11 - Europe \(Frankfurt\)**

**Includes SAP Build Process Automation**



</td>
<td valign="top">

AWS

> ### Note:  
> For EU Access, you must use the data centers DC02 \(DC57\) /DC12 \(DC33\) for SAP SuccessFactors and EU11 for Cloud Foundry.
> 
> For more information about EU Access, see [Enterprise Accounts](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/171511cc425c4e079d0684936486eee6.html)



</td>
<td valign="top">

-   DC02 \(DC57\) - Eemshaven
-   DC12 \(DC33\) – Frankfurt

> ### Note:  
> For EU Access, you must use the data centers DC02 \(DC57\) /DC12 \(DC33\) for SAP SuccessFactors and EU11 for Cloud Foundry.
> 
> For more information about EU Access, see [Enterprise Accounts](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/171511cc425c4e079d0684936486eee6.html)



</td>
<td valign="top">

DC12 \(DC33\) – Frankfurt



</td>
</tr>
<tr>
<td valign="top">

cf-br10 - Brazil \(São Paulo\)



</td>
<td valign="top">

AWS



</td>
<td valign="top">

DC19 - São Paulo



</td>
<td valign="top">

-   Setup prior to January 3rd, 2023:

    DC19 - São Paulo

-   Setup after January 3rd, 2023:

    AWS deployment br10




</td>
</tr>
<tr>
<td valign="top">

cf-ap11 - Asia Pacific \(Singapore\)



</td>
<td valign="top">

AWS



</td>
<td valign="top">

DC44 - Singapore



</td>
<td valign="top">

-   Setup prior to January 3rd, 2023:

    DC44 - Singapore

-   Setup after January 3rd, 2023:

    AWS deployment ap11




</td>
</tr>
<tr>
<td valign="top">

cf-ca10 - Canada \(Montreal\)



</td>
<td valign="top">

AWS



</td>
<td valign="top">

DC60 – Canada Central



</td>
<td valign="top">

DC60 – Canada Central



</td>
</tr>
<tr>
<td valign="top">

cf-jp10 – Japan \(Tokyo\)

**Includes SAP Build Process Automation**



</td>
<td valign="top">

AWS



</td>
<td valign="top">

DC50 – GCP Tokyo



</td>
<td valign="top">

DC50 – GCP Tokyo



</td>
</tr>
</table>

\* For more information about SAP Jam / SAP SuccessFactors Data Centers, see [SAP SuccessFactors Data Centers](https://apps.support.sap.com/sap/support/knowledge/public/en/2089448).

\*\* For more information about the role of Digital Workplace Service \(DWS\) component, see [Solution Architecture and Authentication Details](solution-architecture-and-authentication-details-1fd9ea4.md) 

> ### Note:  
> After creating a subaccount in the Cloud Foundry environment, your user automatically has the administration role. If the subaccount was created by someone else, make sure you're assigned as a Security Administrator or to an SAP BTP cockpit member role on the global account. For more information, see [Managing Security Administrators in Your Subaccount \[Feature Set A\]](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6752c4b8435c456ebf67a97ddbbcb267.html), [Add Members to Your Subaccount \[Feature Set B\]](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/1e1b7b60bb1b4764a2d4bb96bd73182d.html)



<a name="loio96b51b1aaf8349b5a053c56ec6d6fe19__section_zxs_kzf_3qb"/>

## Configure Trust Between SAP Cloud Identity - Identity Authentication and SAP BTP, Cloud Foundry Environment

In this step, you'll configure a trust between SAP BTP, Cloud Foundry Environment and the Identity Authentication service to enable user authentication. The trust is required to connect the Identity Authentication service as the user management system with the SAP BTP role management mechanism.

1.  In the SAP BTP cockpit, go to *Security* \> *Trust Configuration*.
2.  Choose the option that is applicable to you:

    -   **Subaccounts running on Feature Set A:** Set all active trust configurations to inactive, including the default trust configuration to SAP ID Service.
    -   **Subaccounts running on Feature Set B:** You can't deactivate the default identity provider. Instead, edit this entry and disable the options *Available for User Logon* and *Create Shadow Users During Logon*.

    > ### Note:  
    > The SAP SuccessFactors Work Zone Configurator expects only a single trust with the Identity Authentication service for the subaccount. Adding multiple trust configurations might cause an error when running the Configurator.
    > 
    > The trust configuration should be based on the OpenID Connect \(OIDC\) protocol. Using a SAML2 protocol is supported by not recommended. If you are using a custom domain, you must use OIDC protocol.

3.  Establish trust using the method that is relevant to your use case:
    1.  If you are using the default domain \(ondemand.com\) and OIDC protocol, use the *Establish Trust* button in *Security* \> *Trust Configuration* screen. For more information, see [Establish Trust and Federation Between UAA and Identity Authentication](https://help.sap.com/docs/btp/sap-business-technology-platform/establish-trust-and-federation-between-uaa-and-identity-authentication).
    2.  If you are using a custom domain or you have an existing trust configuration which is based on SAML2, refer to [Setting Up a Custom Domain](setting-up-a-custom-domain-97a7ee5.md), step 7 \(Establish a trust to the Identity Authentication tenant and choose the desired domain\).

4.  Access the Identity Authentication service admin environment from the link in the *Trust Configuration* screen, and go to *Applications & Resources* \> *Applications*, and select your subaccount with the SAP SuccessFactors Work Zone subscription..
5.  Open the *Subject Name Identifier* editor of the application, and change the basic configuration attribute from `User ID` to `Global User ID`.
6.  Click *Assertion Attributes*.
    -   Click *\+Add*.
    -   Add the user attribute *Groups* from the list.
    -   In the *Assertion Attribute* column, change the value `groups` to `Groups` \(must start with an upper case letter\), and save.
    -   Add another *Assertion Attribute*.
        -   Click *\+Add*.
        -   Add the user attribute `Global User ID` with the value `User UUID`.


7.  Click *Default Attributes*.
    -   Click *\+Add*.
    -   Add a new attribute `Groups` \(must start with an upper case letter\) with the value `Workzone_User_Type_${type}`.

    -   Add another *Default Attribute*.
        -   Click *\+Add*
        -   Add a new attribute **`sfsf_userid`** with the value **`${customAttribute2}`**

            > ### Note:  
            > In addition to this attribute, customers must modify their Identity Provisioning transformation code to ensure that the SAP SuccessFactors User ID value is assigned to the Identity Authentication service `${customAttribute2}` field. For more information, see [Configuring Identity Provisioning Service](https://help.sap.com/viewer/04877e17a5da4908a6fea94949e160b5/Cloud/en-US/47edc5afeb6e4d56a1c34e9fdbbc998b.html)






<a name="loio96b51b1aaf8349b5a053c56ec6d6fe19__section_t1q_vhh_3qb"/>

## Create Groups in the Identity Authentication Service and Assign Users

In this step, you'll create SAP SuccessFactors Work Zone default user groups in the Identity Authentication service and assign users to them.

You can use other methods to assign users to role collections. For more information, see [https://help.sap.com/docs/WZ/b03c84105ff74f809631e494bd612e83/f04c185d689846908fb11d9a228392a2.html](https://help.sap.com/docs/WZ/b03c84105ff74f809631e494bd612e83/f04c185d689846908fb11d9a228392a2.html)

> ### Note:  
> Only Identity Authentication user type **`Employee`** \(for internal users\) or **`Public`** \(for Identity Authentication-managed externals\) are supported. <code><b>Partner</b></code>/<code><b>Customer</b></code> user type on the Identity Authentication service, won't work.

1.  Open your Identity Authentication admin environment.
2.  Choose the *User Groups* tile.
3.  Click *\+ Add* to add the following groups:

    In the *Name* field enter the exact name listed below, and in the *Display name* field enter a name of your choice such as "Admin user for WZ".

    -   Workzone\_Admin
    -   Workzone\_Area\_Admin
    -   Workzone\_Support\_Admin
    -   Workzone\_Page\_Content\_Admin
    -   Workzone\_End\_User
    -   Workzone\_User\_Type\_public

    For a detailed explanation, see [Create a New User Group](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/b1b638d6724e4dc48ee3e116263f567c.html) 

4.  Choose the *User Management* tile.
5.  Assign yourself to the Workzone\_Admin group.
6.  Assign users to one of the Identity Authentication groups. For example, it's enough to assign an admin user to an admin group as the admin role includes also permissions of an end user. For a detailed explanation, see [Assign Groups to a User](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/bfdeb9c00bf14f6d9f5dbd9603c96996.html)

