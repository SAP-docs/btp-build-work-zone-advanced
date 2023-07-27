<!-- loio4a90162810014b9396dd0edd00b9bc78 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Destination to the SAP Build Work Zone, Advanced Edition Content Repository

Create a destination to the SAP Build Work Zone, advanced edition content repository for deploying both Content Packages and UI Integration cards.



<a name="loio4a90162810014b9396dd0edd00b9bc78__prereq_xjz_ygj_fmb"/>

## Prerequisites

> ### Note:  
> Depending on the time you've onboarded to SAP Build Work Zone, advanced edition, it is possible that this configuration procedure has been already completed by the onboarding booster. Before proceeding, make sure that you don't already have a service instance, a service key, and a destination to the SAP Build Work Zone, advanced edition content repository.

-   Configure an entitlement in your subaccount to the SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone service plan, depending on your flow.

    1.  In the side menu of the SAP BTP cockpit, go to the *Entitlements* screen.
    2.  Click *Configure Entitlements* and then click *Add Service Plans* to open the list of service plans.
    3.  From the list of available plans \(what was previously assigned to your global account\), select the `advanced` service plan for SAP Build Work Zone, advanced edition or `standard` service plan for SAP SuccessFactors Work Zone and click *Add Service Plans*.

        > ### Note:  
        > Make sure you select the service plans from type "service" and not from type "application".


    After assigning the appropriate entitlement, the selected plan will be available in the *Service Marketplace* screen.




<a name="loio4a90162810014b9396dd0edd00b9bc78__context_s5n_j33_z4b"/>

## Context

Create a service instance, a service key, and a destination to the SAP Build Work Zone, advanced edition content repository.



<a name="loio4a90162810014b9396dd0edd00b9bc78__steps_t5n_j33_z4b"/>

## Procedure

1.  In the SAP BTP cockpit, go to the *Services* \> *Instances and Subscriptions*

2.  Select the relevant service \(SAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone\), and in the top right corner click *Create*. Fill all the details of the new service instance. Note that you must enable Cloud Foundry and create a space before you create a service instance. For more information, see [Creating Service Instances in Cloud Foundry](https://help.sap.com/viewer/09cc82baadc542a688176dce601398de/Cloud/en-US/6d6846def3c443aa9f83d127353147ce.html) 

3.  To create a service key, still in the*Instances and Subscriptions* screen, click the <span class="SAP-icons"></span> \(Actions\) next to the service instance entry in the table, and create a service key. For more information, see [Creating Service Keys in Cloud Foundry](https://help.sap.com/viewer/09cc82baadc542a688176dce601398de/Cloud/en-US/6fcac08409db4b0f9ad55a6acd4d31c5.html)

4.  In the SAP BTP cockpit, navigate to *Destinations* screen. Create a new destination with the following details:


    <table>
    <tr>
    <th valign="top">

    Attribute


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **Name**


    
    </td>
    <td valign="top">
    
    Provide a name


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Type**


    
    </td>
    <td valign="top">
    
    HTTP


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Description**


    
    </td>
    <td valign="top">
    
    Provide a description


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **URL**


    
    </td>
    <td valign="top">
    
    Enter the *<\{endpoints.portal-service\}\>* field value available in service key.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Proxy Type**


    
    </td>
    <td valign="top">
    
    Internet


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Authentication**


    
    </td>
    <td valign="top">
    
    OAuth2ClientCredentials


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Client ID**


    
    </td>
    <td valign="top">
    
    Enter the *<\{uaa.clientid\}\>* field value available in service key.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Client Secret**


    
    </td>
    <td valign="top">
    
    Enter the *<\{uaa.clientsecret\}\>* field value available in service key.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Token Service URL**


    
    </td>
    <td valign="top">
    
    Enter the *<\{uaa.url\}/oauth/token\>* field value available in service key.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Token Service URL Type**


    
    </td>
    <td valign="top">
    
    Dedicated


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Add the following additional properties:**


    
    </td>
    <td valign="top">
    
     


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **HTML5.DynamicDestination**


    
    </td>
    <td valign="top">
    
    true


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **HTML5.SetXForwardHeaders**


    
    </td>
    <td valign="top">
    
    false


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **WebIDEEnabled**


    
    </td>
    <td valign="top">
    
    true


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **WebIDEUsage**


    
    </td>
    <td valign="top">
    
    content\_repository


    
    </td>
    </tr>
    </table>
    
    A new destination is created and available for both content package and card deployment.


