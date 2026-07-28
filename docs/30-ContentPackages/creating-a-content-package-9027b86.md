<!-- loio9027b863c1b44c159ccb0584c0634827 -->

# Creating a Content Package

Create a content package using SAP Business Application Studio.



<a name="loio9027b863c1b44c159ccb0584c0634827__prereq_eyv_5wj_lyb"/>

## Prerequisites

You’ve created a dev space with the **Development Tools for SAP Build Work Zone** extension.



<a name="loio9027b863c1b44c159ccb0584c0634827__context_j4c_lly_ykb"/>

## Context

This procedure explains how to create a basic content package. For detailed instructions for how to enhance the content package with content, see [Project Templates for Content Packages](https://github.com/SAP-samples/build-workzone-integration/tree/main/advanced/content-package-template).



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

    You’ve successfully created a content package project. You can now perform the following actions:

    -   Update the content package: For more information, see [Updating a Content Package](updating-a-content-package-de85e4f.md).
    -   Delete the content package: To do so, navigate to the newly created content package project. Right-click on the project and select *Delete*.
    -   Deploy the content package: For more information, see [Deploying a Content Package](deploying-a-content-package-5556cbf.md).

    You can also create a content package using the command line. Execute the `Content Package: Create Content Package Project` to launch a command line interface for creating a content package.

6.  Add content to your content package. You can refer to the sample content package [Project Templates for Content Packages](https://github.com/SAP-samples/build-workzone-integration/tree/main/advanced/content-package-template) for detailed instructions on how to do it.

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


