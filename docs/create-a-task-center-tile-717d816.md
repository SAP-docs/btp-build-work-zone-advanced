<!-- loio717d816356d94f22955da93bfef6f74b -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Create a Task Center Tile

Administrators can create Task Center tiles in a site so that users can access all tasks created in the SAP Task Center service that have been assigned to them.



## Prerequisite

You've created a service instance of the SAP Task Center service. For more information, see [Create a Service Instance of the SAP Task Center Service.](https://help.sap.com/docs/task-center/sap-task-center/create-service-instance-of-sap-task-center-service?version=Cloud)



<a name="loio717d816356d94f22955da93bfef6f74b__section_k33_mxf_hzb"/>

## How to create the tile

1.  From the navigation panel, click <span class="SAP-icons-V5"></span> to open the Channel Manager.

2.  From the *HTML5 Apps* provider, under the *Actions* column, choose :arrows_clockwise: to fetch the updated content.

3.  From the side navigation panel, click :package: to open the *Content Manager*.

4.  Click the *Content Explorer* button and choose *HTML5 Apps*.

5.  Select the *Task Center* content item and click *Add* .

6.  Go back to the *Content Manager* to see that the Task Center app is added.

7.  Select *Create* \> *Group* to add a new group, name the group, and in the *Apps* tab, in the *Assignment Status* column, assign the *Task Center* app to the group.

    > ### Note:  
    > Assigning apps to groups makes them visible to the user.

8.  Go back to the *Content Manager* as you now need to assign the *Task Center* app to a role.

9.  Assign the *Task Center* to a role. You can use the default *Everyone* role.

    > ### Note:  
    > Content assigned to the *Everyone* role is visible to all users.

10. If you assigned the *Task Center* app to a different role than the *Everyone* role, you need to assign this role to your site in the Site Directory, in the *Site Settings* \> *Role Assignments* screen.

11. From the Site Directory, click <span class="SAP-icons-V5"></span> on the site tile to open the runtime view. You should be able to see the *Task Center* tile in the group that you assigned it to.




<a name="loio717d816356d94f22955da93bfef6f74b__section_sdy_txm_hzb"/>

## Optional: Setting up SAP Companion for SAP Task Center

Activate SAP Companion to enable on-screen help in the SAP Task Center Web app.

For more information, see [SAP Enable Now](https://help.sap.com/docs/SAP_ENABLE_NOW).

Follow these steps:

1.  Click :globe_with_meridians: to open the Site Directory.

2.  Click :gear: to navigate to the *Site Settings* screen.

3.  Click *Edit* and activate the *SAP Companion* setting by choosing *Yes*.

4.  Add the following parameters:


    <table>
    <tr>
    <th valign="top">

    Name
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    product
    
    </td>
    <td valign="top">
    
    TASK\_CENTER
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    version
    
    </td>
    <td valign="top">
    
    Cloud
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    stateUACP
    
    </td>
    <td valign="top">
    
    PRODUCTION
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    dataUrlUACP
    
    </td>
    <td valign="top">
    
    https://help.sap.com/webassistant/
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    resourceUrl
    
    </td>
    <td valign="top">
    
    https://webassistant.enable-now.cloud.sap/web\_assistant/framework/
    
    </td>
    </tr>
    </table>
    
5.  Save your settings.

    > ### Note:  
    > You can assign only one set of SAP Companion settings per site. Therefore you either activate the SAP Companion for SAP Task Center or the SAP Companion for the SAP Build Work Zone, advanced edition site. For more information, see [Restrictions](restrictions-b259464.md).


