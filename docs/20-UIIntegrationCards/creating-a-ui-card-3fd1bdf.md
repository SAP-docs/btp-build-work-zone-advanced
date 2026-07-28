<!-- loio3fd1bdf42ff0417f8adec8567908e901 -->

# Creating a UI Card

Create a UI card using SAP Business Application Studio.



<a name="loio3fd1bdf42ff0417f8adec8567908e901__prereq_eyv_5wj_lyb"/>

## Prerequisites

You’ve created a dev space with the **Development Tools for SAP Build Work Zone** extension.



<a name="loio3fd1bdf42ff0417f8adec8567908e901__context_j4c_lly_ykb"/>

## Context

This procedure explains how to create a basic card. However, you can enhance the card with many more options. For more information about the development flow, see [Developing Cards](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/overview/developingCards).



<a name="loio3fd1bdf42ff0417f8adec8567908e901__steps_k4c_lly_ykb"/>

## Procedure

1.  Launch SAP Business Application Studio and navigate to the dev space that you created for UI cards.

2.  On the welcome screen, choose *New Project From Template*.

3.  Choose *UI Integration Card* \> *Next*.

4.  In the *Project Details* section, provide the following details and choose *Next*.


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
    
    **Select a Card Sample**
    
    </td>
    <td valign="top">
    
    Select a card sample from the available samples.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **NameSpace**
    
    </td>
    <td valign="top">
    
    Enter a namespace. The card ID is generated using the namespace and the project name.

    Card ID: <namespace\>.<project name\>
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Card Title**
    
    </td>
    <td valign="top">
    
    Enter a title
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Card Subtitle**
    
    </td>
    <td valign="top">
    
    Enter a subtitle
    
    </td>
    </tr>
    </table>
    
    You’ve successfully created a card project that contains the required UI Card. You can now perform the following actions:

    -   Update the UI card: For more information, see [Updating a UI Card](updating-a-ui-card-c27069e.md)
    -   Delete the UI card: To do so, navigate to the newly created card project. Right-click on the project and select *Delete*.
    -   Package the UI card: For more information, see [Deploying or Downloading a UI Card](deploying-or-downloading-a-ui-card-35e6049.md)

    You can also create a UI card using the command line. To do so, navigate to *View* \> *Find Command*. In the CLI, select *UI Integration Card: Create Card Project*. Provide the required details and confirm to create the project. After confirmation, the newly created project is available in your workspace.


