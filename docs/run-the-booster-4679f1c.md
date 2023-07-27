<!-- loio4679f1cb6ed24e2eb0ebd07151758269 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Run the Booster

The SAP Build Work Zone, advanced edition booster assists you by performing configuration steps automatically on your subaccount.



<a name="loio4679f1cb6ed24e2eb0ebd07151758269__section_dwc_1gy_jmb"/>

## Running the Booster

**Previous Step:** [Prerequisites](prerequisites-9e78b62.md)

To run the booster:

1.  In the SAP BTP cockpit, use the breadcrumbs to access your global account.
2.  In the side menu, open the *Boosters* screen and click the *Get Started with SAP Build Work Zone, Advanced Edition* tile.
3.  SAP Build Work Zone, advanced edition contains integration with SAP Build Process Automation service. SAP Build Process Automation is a citizen developer solution to adapt, improve, and innovate business processes with no-code workflow management and robotic process automation capabilities. If you are not planning to use SAP Build Process Automation, you can remove the service when you run the booster. If you decide later on that you do want to use it, see below instructions for how to add it.



<a name="loio4679f1cb6ed24e2eb0ebd07151758269__section_s5q_kwh_zqb"/>

## Manual Execution of the Booster

If you encounter technical issues in running the booster, here are the steps that the booster performs for you:

1.  Account setup:
    1.  Select subaccount \(the one where you intend to use SAP Build Work Zone, advanced edition\)
    2.  Enable Cloud Foundry
    3.  Create a space
    4.  Assign entitlement \(list of services and number of quota for each service\)
    5.  Create a service instance and a service key for the SAP Build Work Zone, advanced edition service **\(optional\)**
        1.  In the *Entitlements* screen of your subaccount, click *Configure Entitlements* and then click *Add Service Plans*.
        2.  select the *advanced* service plan of SAP Build Work Zone, advanced edition \(not the standard\(application\)\), and click *Add Service Plans*.
        3.  In the SAP BTP cockpit, go to *Services* \> *Instances and Subscriptions*.
        4.  In the top right corner, click *Create* and fill in all the details of the new service instance. Note that you must enable Cloud Foundry and create a space before you create a service instance \(done by the booster\). For more information, see [Creating Service Instances in Cloud Foundry](https://help.sap.com/viewer/09cc82baadc542a688176dce601398de/Cloud/en-US/6d6846def3c443aa9f83d127353147ce.html) 
        5.  To create a service key, still in the *Instances and Subscriptions* screen, click the <span class="SAP-icons"></span> \(Actions\) next to the service instance entry in the table, and create a service key. For more information, see [Creating Service Keys in Cloud Foundry](https://help.sap.com/viewer/09cc82baadc542a688176dce601398de/Cloud/en-US/6fcac08409db4b0f9ad55a6acd4d31c5.html)

    6.  Create a destination to the content repository. For more information, see [**Creating a Destination to the Content Repository**](https://help.sap.com/docs/WZ/7d3b9c7211ca4d7a9630b524205ee836/4a90162810014b9396dd0edd00b9bc78.html)

2.  Subscribe to SAP Build Work Zone, advanced edition.
3.  Map the following role collections to the relevant SAP Cloud Identity Services - Identity Authentication groups:


    <table>
    <tr>
    <th valign="top">

    IAS Group


    
    </th>
    <th valign="top">

    Role Collections


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Workzone\_Admin


    
    </td>
    <td valign="top">
    
    Workzone\_Admin, Workflow\_Admin, Workflow\_End\_User, Workzone\_XSUAA\_ Access, Workzone\_Advanced\_Theming


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Workzone\_Area\_Admin


    
    </td>
    <td valign="top">
    
    Workzone\_Area\_Admin, Workflow\_End\_User, Workzone\_Advanced\_Theming


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Workzone\_Support\_Admin


    
    </td>
    <td valign="top">
    
    Workzone\_Admin, Workflow\_End\_User, Workzone\_Advanced\_Theming


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Workzone\_Page\_Content\_Admin


    
    </td>
    <td valign="top">
    
    Workzone\_End\_User, Workflow\_End\_User


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Workzone\_End\_User


    
    </td>
    <td valign="top">
    
    Workzone\_End\_User, Workflow\_End\_User


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Workzone\_User\_Type\_public


    
    </td>
    <td valign="top">
    
    Workzone\_External\_User


    
    </td>
    </tr>
    </table>
    
4.  Launch the SAP Build Work Zone, advanced edition Configurator.



<a name="loio4679f1cb6ed24e2eb0ebd07151758269__section_bgr_fth_zqb"/>

## SAP Build Process Automation Service - Manual Subscription

-   If you run the booster with SAP Build Process Automation, you can't remove it.
-   If you run the booster without SAP Build Process Automation, you can add it later in the following ways:
    1.  Run the booster again. This time select to run it with the SAP Build Process Automation service.
    2.  Configure SAP Build Process Automation to work with SAP Build Work Zone, advanced edition. For more information, see [Configure SAP Build Process Automation](https://help.sap.com/docs/PROCESS_AUTOMATION/a331c4ef0a9d48a89c779fd449c022e7/3dbbe660fab54eeeb79c844a0de84103.html) 


