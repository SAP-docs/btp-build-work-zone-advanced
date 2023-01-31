<!-- loio91d7e7c0b22c4d329abe3a90971f9bfe -->

# Developing a UI Card for MTB Backend

Develop a UI card for MTB backend using SAP Business Application Studio.



<a name="loio91d7e7c0b22c4d329abe3a90971f9bfe__prereq_asx_vwy_wkb"/>

## Prerequisites

You’ve created a dev space with the *Development Tools for SAP Build Work Zone, Advanced Edition* extension.



<a name="loio91d7e7c0b22c4d329abe3a90971f9bfe__context_j4c_lly_ykb"/>

## Context

You’re developing a UI card. The following procedure describes steps on how to create, update, and deploy a UI card.



<a name="loio91d7e7c0b22c4d329abe3a90971f9bfe__steps_k4c_lly_ykb"/>

## Procedure

1.  Launch SAP Business Application Studio and navigate to the dev space that you created for UI cards.

2.  On the welcome screen, choose *New Project From Template*.

3.  Choose *UI Integration Card For MTB* \> *Next*.

4.  In *Project Details* section, provide the following details and choose *Next*.


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

    **Select a Card Type**


    
    </td>
    <td valign="top">

    Select a card type from the available samples. .

    > ### Note:  
    > Currently, the supported card types are: *Object Card*, *List Card*, and *Table Card*.


    
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
    
5.  In *MTB Backend* section, provide the following details and choose *Next*.


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

    **Select a Destination**


    
    </td>
    <td valign="top">

    Select a destination from the dropdown. For more information on creating a destination, refer to this [link](https://help.sap.com/doc/f53c64b93e5140918d676b927a3cd65b/Cloud/en-US/docs-en/guides/getting-started/mtb/introduction.html).


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    **Select an Application**


    
    </td>
    <td valign="top">

    Select an application from the dropdown.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    **Select a Data Source**


    
    </td>
    <td valign="top">

    Select a data source from the dropdown.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    **Select a Function**


    
    </td>
    <td valign="top">

    Select a function from the dropdown.


    
    </td>
    </tr>
    </table>
    
6.  In *Data Setting* section, provide the following details and choose *Next*. In this step, you must provide the value for each available parameter for the MTB function specified in the previous step.


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

    **Value for Parameter <parameter name\>**


    
    </td>
    <td valign="top">

    Enter a value for the parameter.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    **Do you want to generate card configuration and content automatically?**


    
    </td>
    <td valign="top">

    Select either *Yes* or *No*. If you chose yes, then the card content is generated automatically and the required UI card is created. If you chose no, then proceed to the next step to create the card content manually.


    
    </td>
    </tr>
    </table>
    
7.  Based on the selected card type, in the *Card Configuration* section, specify the parameters, header type, and other configurations related to the card type. The provided values are included in the card configuration.

8.  In *Card Content* section, specify the detailed data binding as required.

    You’ve successfully created a card project that contains the required UI Card. The newly created card is now available in your workspace. You can now perform the following:

    -   Update the UI card: For more information, see [Updating a UI Card](updating-a-ui-card-c27069e.md)
    -   Delete the UI card: To do so, navigate to the newly created card project. Right-click on the project and select *Delete*.
    -   Deploy the UI card: For more information, see [Deploying a UI Card](deploying-a-ui-card-35e6049.md)


