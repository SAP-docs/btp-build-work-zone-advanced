<!-- loio91d7e7c0b22c4d329abe3a90971f9bfe -->

# Developing a UI Integration Card for MTB

Develop a UI card for MTB \(Mobile Transaction Bridge\) backend using SAP Business Application Studio.



<a name="loio91d7e7c0b22c4d329abe3a90971f9bfe__context_j4c_lly_ykb"/>

## Context

The following procedure describes steps on how to create, update, and deploy a UI card from MTB generated OData services.



<a name="loio91d7e7c0b22c4d329abe3a90971f9bfe__steps_k4c_lly_ykb"/>

## Procedure

1.  Launch SAP Business Application Studio and navigate to the dev space that you created for UI cards.

2.  On the Get Started page, choose *New Project From Template*.

3.  Choose *UI Integration Card For MTB* \> *Start*.

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
    
    **NameSpace**
    
    </td>
    <td valign="top">
    
    Enter a namespace. The card ID is generated using the namespace and the project name.

    Card ID: <namespace\>.<project name\>
    
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
    
    Select a destination from the dropdown.
    
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


