<!-- loiode85e4f7a6e744ac979a398be857c111 -->

# Updating a Content Package

Update a content package using SAP Business Application Studio.



<a name="loiode85e4f7a6e744ac979a398be857c111__steps_dgn_5f5_xkb"/>

## Procedure

1.  Launch SAP Business Application Studio and navigate to the dev space where you created the content package.

2.  To edit the `manifest.json` file, navigate to the project that contains the required content package. From the context menu, choose *Content Package: Edit*. You can also directly open the `manifest.json` file in the code editor.

3.  To edit the `content.json` file, navigate to project that contains the required content package. From the context menu, choose *Content Package: Content Edit*. You can also directly open the `content.json` file in the code editor and make the necessary changes.

    1.  In the property editor, you can choose *Add: Artifact* to add a new artifact and specify the properties as per your requirements. Also, you can choose *Add* to quickly include a new artifact from an existing project in the SAP Business Application Studio workspace.

        For each of the artifacts, you can define the following properties:


        <table>
        <tr>
        <th valign="top">

        Property Name
        
        </th>
        <th valign="top">

        Value
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        Name
        
        </td>
        <td valign="top">
        
        Enter the name of the artifacts folder in the package.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Type
        
        </td>
        <td valign="top">
        
        Enter the type of the artifact currently supported: card, workflow, workspace-template
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Mode
        
        </td>
        <td valign="top">
        
        Specify if the source is from Git or from an existing project.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Git
        
        </td>
        <td valign="top">
        
        Enter the name of the Git repository to pull the content. \(Git mode\)
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Branch
        
        </td>
        <td valign="top">
        
        Specify branch or label of the repository. \(Git mode\)
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        From
        
        </td>
        <td valign="top">
        
        Enter the path to the source folder. \(project mode\)
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Path
        
        </td>
        <td valign="top">
        
        Specify the path within the folder to execute the build.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Build
        
        </td>
        <td valign="top">
        
        Specify the build scripts to create the artifact package. If this field is empty, the general build process is executed by default.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Package
        
        </td>
        <td valign="top">
        
        Specify the location of the artifact's package after the build.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Manifest
        
        </td>
        <td valign="top">
        
        Specify the location of the manifest to extract the settings for the Content Package.
        
        </td>
        </tr>
        </table>
        
    2.  In the property editor, you can also customize the build action. To do so, specify the values for the *Build* and *Package* fields.



