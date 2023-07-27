<!-- loiod1a7b42015084959952f18ee5c5568f3 -->

# Creating a Workspace Template

Create a workspace template using SAP Business Application Studio.



<a name="loiod1a7b42015084959952f18ee5c5568f3__prereq_asx_vwy_wkb"/>

## Prerequisites

You’ve created a dev space with the *Development Tools for SAP Build Work Zone, Advanced Edition* extension.



<a name="loiod1a7b42015084959952f18ee5c5568f3__context_j4c_lly_ykb"/>

## Context



<a name="loiod1a7b42015084959952f18ee5c5568f3__steps_k4c_lly_ykb"/>

## Procedure

1.  Launch SAP Business Application Studio and navigate to the dev space that you created for workspace templates.

2.  On the welcome screen, choose *New Project From Template*.

3.  Choose *Workspace Template for Workzone* \> *Start*.

4.  In Project Details section, provide the following details and choose *Next*.


    <table>
    <tr>
    <th valign="top">

    Field name


    
    </th>
    <th valign="top">

    Value


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **Project Name**


    
    </td>
    <td valign="top">
    
    Enter a project name.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Namespace**


    
    </td>
    <td valign="top">
    
    Enter a namespace. The workspace template ID is generated using the namespace and the project name.

    Workspace template ID: <namespace\>.<project name\>


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Select a Template**


    
    </td>
    <td valign="top">
    
    Choose either *New Workspace Template* or *Download Workspace Template*. If you choose *Download Workspace Template* option, the workspace templates available in the system will be listed in the next window for your selection. Also, specify *JAM* as your destination.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Title**


    
    </td>
    <td valign="top">
    
    Enter a title of the workspace.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Subtitle**


    
    </td>
    <td valign="top">
    
    Enter a subtitle of the workspace.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Short Title**


    
    </td>
    <td valign="top">
    
    Enter a short title of the workspace.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Info**


    
    </td>
    <td valign="top">
    
    Specify the info for the workspace.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Description**


    
    </td>
    <td valign="top">
    
    Provide the description of the workspace.


    
    </td>
    </tr>
    </table>
    
5.  Choose *Finish*.

    You’ve successfully created a project that contains the required workspace template. The newly created workspace template is now available in your workspace. You can now perform the following:

    -   Update the workspace template: For more information, see [Updating a Workspace Template](updating-a-workspace-template-569df27.md).
    -   Delete the workspace template: To do so, navigate to the newly created card project. Right-click on the project and select *Delete*.
    -   Deploy the workspace template: For more information, see [Deploying a Workspace Template](deploying-a-workspace-template-d435663.md).

    You can also execute `Workspace Template: Create Workspace Template Project` to launch a command line interface for creating workspace template.


