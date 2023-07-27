<!-- loio3fd1bdf42ff0417f8adec8567908e901 -->

# Creating a UI Card

Create a UI card using SAP Business Application Studio.



<a name="loio3fd1bdf42ff0417f8adec8567908e901__prereq_asx_vwy_wkb"/>

## Prerequisites

You’ve created a dev space with the *Development Tools for SAP Build Work Zone, Advanced Edition* extension.



<a name="loio3fd1bdf42ff0417f8adec8567908e901__context_j4c_lly_ykb"/>

## Context



<a name="loio3fd1bdf42ff0417f8adec8567908e901__steps_k4c_lly_ykb"/>

## Procedure

1.  Launch SAP Business Application Studio and navigate to the dev space that you created for UI cards.

2.  On the welcome screen, choose *New Project From Template*.

3.  Choose *UI Integration Card* \> *Next*.

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
    <tr>
    <td valign="top">
    
    **Mobile Card Compatible**


    
    </td>
    <td valign="top">
    
    Select *True* to enable mobile card compatibility.

    After the UI Card is deployed, if this feature is enabled, then you can use the option *add to mobile* on the card.


    
    </td>
    </tr>
    </table>
    
    You’ve successfully created a card project that contains the required UI Card. The newly created card is now available in your workspace. You can now perform the following:

    -   Update the UI card: For more information, see [Updating a UI Card](updating-a-ui-card-c27069e.md)
    -   Delete the UI card: To do so, navigate to the newly created card project. Right-click on the project and select *Delete*.
    -   Deploy the UI card: For more information, see [Deploying a UI Card](deploying-a-ui-card-35e6049.md)

    You can also create a UI card using the command line. To do so, navigate to *View* \> *Find Command*. In the CLI, select *UI Integration Card: Create Card Project*. Provide the required details and confirm to create the project. After confirmation, the newly created project is available in your workspace.


**Related Information**  


[Updating a UI Card](updating-a-ui-card-c27069e.md "Update a UI card using SAP Business Application Studio.")

[Deploying a UI Card](deploying-a-ui-card-35e6049.md "Deploy a UI integration card using SAP Business Application Studio.")

