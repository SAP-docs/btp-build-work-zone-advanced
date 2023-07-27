<!-- loio9027b863c1b44c159ccb0584c0634827 -->

# Creating a Content Package

Create a content package using SAP Business Application Studio.



<a name="loio9027b863c1b44c159ccb0584c0634827__prereq_asx_vwy_wkb"/>

## Prerequisites

You’ve created a dev space with the *Development Tools for SAP Build Work Zone, Advanced Edition* extension.



<a name="loio9027b863c1b44c159ccb0584c0634827__context_j4c_lly_ykb"/>

## Context



<a name="loio9027b863c1b44c159ccb0584c0634827__steps_k4c_lly_ykb"/>

## Procedure

1.  Launch SAP Business Application Studio and navigate to the dev space that you created for content packages.

2.  On the welcome screen, choose *New Project From Template*.

3.  Choose *Content Package* \> *Start*.

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
    
    **NameSpace**


    
    </td>
    <td valign="top">
    
    Enter a namespace. The content package ID is generated using the namespace and the project name.

    Content Package ID: <namespace\>.<project name\>


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Title**


    
    </td>
    <td valign="top">
    
    Enter a title


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Subtitle**


    
    </td>
    <td valign="top">
    
    Enter a subtitle


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Include Content Samples**


    
    </td>
    <td valign="top">
    
    Choose *True* to include content samples for the project.

    If not, an empty project is generated, and you can add artifacts later.


    
    </td>
    </tr>
    </table>
    
5.  Choose *Finish*.

    You’ve successfully created a project that contains the required content package. The newly created content package is now available in your workspace. You can now perform the following:

    -   Update the content package: For more information, see [Updating a Content Package](updating-a-content-package-de85e4f.md)
    -   Delete the content package: To do so, navigate to the newly created card project. Right-click on the project and select *Delete*.
    -   Deploy the content package: For more information, see [Deploying a Content Package](deploying-a-content-package-5556cbf.md)

    You can also execute `Content Package: Create Content Package Project` to launch a command line interface for creating content package.

    **Adding Destinations**

    If the content package contains apps that are rendered on a remote system, you need to configure a destination to the remote system in the *Destinations* screen of the cockpit.

    After the destination is created, the following code should be added to the content package manifest.json file:

    ```
    {
    "sap.package": { 
       				 .....
       		 		"prerequisites":
    						{         
         					 "destinations": [                                             
             
    							{ "name": "123",             "document":"https://xxx.yyy.zzz"} 
    								,
              				  {"name": "456"}
             				]
         				   }
       			}
    }
    
    ```


