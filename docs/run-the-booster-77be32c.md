<!-- loio77be32c76314481eacb93ccf86daed92 -->

# Run the Booster

The SAP SuccessFactors Work Zone booster assists you by performing configuration steps automatically in your subaccount.



<a name="loio77be32c76314481eacb93ccf86daed92__section_dwc_1gy_jmb"/>

## Running the Booster

**Previous Step:** [Prerequisites](prerequisites-96b51b1.md)

To run the booster:

1.  In the SAP BTP cockpit, use the breadcrumbs to access your global account.
2.  In the side menu, open the *Boosters* screen and click the *Get Started with SAP SuccessFactors Work Zone* tile.
3.  SAP SuccessFactors Work Zone contains integration with SAP Build Process Automation service. SAP Build Process Automation is a citizen developer solution to adapt, improve, and innovate business processes with no-code workflow management and robotic process automation capabilities. If you are not planning to use SAP Build Process Automation, you can remove the service when you run the booster. If you decide later on that you do want to use it, see below instructions for how to add it.



<a name="loio77be32c76314481eacb93ccf86daed92__section_s5q_kwh_zqb"/>

## Manual Execution of the Booster

If you encounter technical issues in running the booster, here are the steps that the booster performs for you:

1.  In the SAP BTP cockpit, select a subaccount and perform the following configuration steps:
    1.  In the *Overview* screen, enable Cloud Foundry and create an org and a space. For more information, see [Administration and Operations in the Cloud Foundry Environment](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/a6b3b81f29e64574b64723cf0ff82fc5.html).
    2.  In the *Entitlements* screen, assign entitlements to all the services that are listed in the **Components** table here [Solution Architecture](solution-architecture-1fd9ea4.md).
    3.  In the *Services* \> *Instances and Subscriptions* screen, subscribe and create service instances to the service plans that are listed in the **Service plan configuration** table here [Solution Architecture](solution-architecture-1fd9ea4.md). For detailed instructions, see [Creating Service Instances in Cloud Foundry](https://help.sap.com/viewer/09cc82baadc542a688176dce601398de/Cloud/en-US/6d6846def3c443aa9f83d127353147ce.html), [Creating Service Keys in Cloud Foundry](https://help.sap.com/viewer/09cc82baadc542a688176dce601398de/Cloud/en-US/6fcac08409db4b0f9ad55a6acd4d31c5.html).

        > ### Note:  
        > When creating a service instance for SAP SuccessFactors Work Zone, uploading configuration parameters is not supported.

    4.  Create a destination to the content repository. For more information, see step 4 in [Development Tools for SAP Build Work Zone](development-tools-for-sap-build-work-zone-2464862.md) \(Prerequisites, step 4\).

2.  Create a role collection for accessing XSUAA, which is required for setting a trust.
    1.  Go to *Security* \> *Role Collections*.
    2.  Click *New Role Collection*.
    3.  Specify a name such as **`XSUAA_Access_RoleCollection`**, and click *Save*.
    4.  Edit the new role collection, and in the *Roles* section, select the role name **`XSUAA_Access`** from the list.
    5.  Click *Save*.

3.  Map the following role collections to the Identity Authentication groups. In the *Security* \> *Trust Configuration* screen, click the active trust configuration link and go to *Role Collection Mapping*. Add the following role collection mapping, using the attribute `Groups`:


    <table>
    <tr>
    <th valign="top">

    Identity Authentication Group
    
    </th>
    <th valign="top">

    Role Collection
    
    </th>
    <th valign="top">

    SAP SuccessFactors Work Zone Persona
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Workzone\_Admin
    
    </td>
    <td valign="top">
    
    HR\_Workzone\_Admin, ProcessAutomationAdmin, ProcessAutomationDeveloper, ProcessAutomationParticipant, HR\_Workzone\_Advanced\_Theming

    \* your XSUAA role collection, such as `XSUAA_Access_RoleCollection` 
    
    </td>
    <td valign="top">
    
    Company Admin
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Workzone\_Area\_Admin
    
    </td>
    <td valign="top">
    
    HR\_Workzone\_Area\_Admin, ProcessAutomationParticipant
    
    </td>
    <td valign="top">
    
    Area Admin
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Workzone\_Support\_Admin
    
    </td>
    <td valign="top">
    
    HR\_Workzone\_Admin , ProcessAutomationParticipant
    
    </td>
    <td valign="top">
    
    Support Admin
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Workzone\_Page\_Content\_Admin
    
    </td>
    <td valign="top">
    
    HR\_Workzone\_End\_User, ProcessAutomationParticipant
    
    </td>
    <td valign="top">
    
    Page Content Admin
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Workzone\_End\_User
    
    </td>
    <td valign="top">
    
    HR\_Workzone\_End\_User, ProcessAutomationParticipant
    
    </td>
    <td valign="top">
    
    Internal user
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Workzone\_User\_Type\_public
    
    </td>
    <td valign="top">
    
    HR\_Workzone\_External\_User
    
    </td>
    <td valign="top">
    
    External user
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > -   To learn more about which roles are included in each role collection, click the role collection and view the list of roles.
    > -   The HR\_Workzone\_Admin role collection includes all the necessary admin roles for accessing the Site Manager screens, the UI Theme Designer \(excluding the `Publisher` and `CustomCssEditor` roles\), and Mobile Services.

4.  Launch the SAP SuccessFactors Work Zone Configurator.



<a name="loio77be32c76314481eacb93ccf86daed92__section_vqw_dxy_lyb"/>

## Replacement of SAP Workflow Service with SAP Build Process Automation

On July 17th 2023, the SAP Workflow service was replaced with SAP Build Process Automation in SAP SuccessFactors Work Zone.

-   Existing service instances of the SAP Workflow service \(incl. destinations\) continue to work as before.
-   Deleting the \(last\) service instance of SAP Workflow service in the subaccount also deletes all the deployed content.
-   Customers that completed the onboarding process after this date are automatically using SAP Build Process Automation.



<a name="loio77be32c76314481eacb93ccf86daed92__section_bgr_fth_zqb"/>

## SAP Build Process Automation - Manual Subscription

-   If you run the booster with SAP Build Process Automation, you can't remove it.
-   If you run the booster without SAP Build Process Automation, you can rerun the booster but this time select SAP Build Process Automation.

The relevant service plans are *standard* and *advanced-user*.

The full configuration steps are listed here: [Configure SAP Build Process Automation](https://help.sap.com/docs/PROCESS_AUTOMATION/a331c4ef0a9d48a89c779fd449c022e7/3dbbe660fab54eeeb79c844a0de84103.html).

