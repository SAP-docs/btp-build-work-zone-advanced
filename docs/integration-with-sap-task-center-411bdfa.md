<!-- loio411bdfa49b7e42cda7b731bc6fc108fd -->

# Integration with SAP Task Center

Complete the following steps to integrate with the SAP Task Center service.



<a name="loio411bdfa49b7e42cda7b731bc6fc108fd__section_pwh_2fb_3yb"/>

## Setting Up SAP Task Center

The SAP Task Center service enables integration with SAP and non-SAP applications to provide a single entry point for end users to access all their assigned tasks.

To integrate with SAP Task Center perform the following steps:


<table>
<tr>
<th valign="top">

Step

</th>
<th valign="top">

More information

</th>
</tr>
<tr>
<td valign="top">

Complete the initial setup steps on SAP Task Center side.

</td>
<td valign="top">

[Initial Setup](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/834769400794464489f390350a82bbd6.html).

</td>
</tr>
<tr>
<td valign="top">

Create a Task Center tile in your site.

</td>
<td valign="top">

[Create a Task Center Tile](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/70e7f6e91e7b480796c5d24c34e1228e.html).

</td>
</tr>
<tr>
<td valign="top">

\[Optional\] Create a Task Center Administration tile in your site.

</td>
<td valign="top">

[Create a Task Center Administration Tile](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/8053d72535eb4c7891cfc0cf07104a8d.html).

</td>
</tr>
</table>



## Exposing Tasks in SAP Task Center

To be able to expose workspace-related tasks in the SAP Task Center, you need to configure SAP Build Work Zone, advanced edition/ SAP SuccessFactors Work Zone as task providers.

Once configured, workspace users will be able to see their tasks as well as comments and attachments in the SAP Task Center UI.

> ### Note:  
> Workspace tasks exposed to SAP Task Center are not supported when viewed in the Joule Work mobile app.

Supported tasks:


<table>
<tr>
<th valign="top">

Task Type

</th>
<th valign="top">

Supported Languages

</th>
<th valign="top">

Supported As Of

</th>
</tr>
<tr>
<td valign="top">

Workspace tasks

</td>
<td valign="top">

English

</td>
<td valign="top">

August 10th, 2023

</td>
</tr>
<tr>
<td valign="top">

Migration of notifications to SAP Task Center. For more information, see [Notifications Migrated to SAP Task Center](https://help.sap.com/docs/WZ/b03c84105ff74f809631e494bd612e83/103020b3ed2e4f899a6f896ada65acb3.html).

</td>
<td valign="top">

English

</td>
<td valign="top">

December 28th, 2023

</td>
</tr>
</table>



### Procedure

1.  If you've completed the onboarding process to SAP Build Work Zone, advanced edition/ SAP SuccessFactors Work Zone prior to August 10th, 2023, you would need to update the transformation code in Identity Provisioning service. If you've completed the onboarding after this date, you can skip this step.
    1.  For SAP Build Work Zone, advanced edition, see [Run the Configurator](https://help.sap.com/docs/WZ/b03c84105ff74f809631e494bd612e83/7202ced311534d25856aa6901d43fc1b.html) - option 2, step 3. Please repeat the step **Configure transformation**.
    2.  For SAP SuccessFactors Work Zone, see [Run the Configurator](https://help.sap.com/docs/WZ/b03c84105ff74f809631e494bd612e83/07b0a265ef4a41b8a1413005bc3c5e31.html) - option 1, step 4. Please repeat the step **Configure transformation**.

2.  Create an OAuth Client for SAP Task Center. This will authorize SAP Task Center to access the SAP Build Work Zone, advanced edition API.
    1.  In the Admin Console, go to *External Integrations* \> *OAuth Clients*.
    2.  Click *Add OAuth Client*.
    3.  Enter the OAuth client details. The name is mandatory. For more information, see [Add an OAuth Client](https://help.sap.com/docs/WZ/b03c84105ff74f809631e494bd612e83/b3c804e1f999448b8011a475fea1da6c.html).

3.  Configure a destination between SAP Task Center and SAP Build Work Zone, advanced edition/SAP SuccessFactors Work Zone. When configuring the destination, you will need to use the below parameters. For more information, see [Connect SAP Build Work Zone, advanced edition and SAP Task Center](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/f07f3103d40447d6bfbb0ae0b7920f6a.html).


    <table>
    <tr>
    <th valign="top">

    Entry
    
    </th>
    <th valign="top">

    Where to find this info
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Audience
    
    </td>
    <td valign="top">
    
    <DWS URL\>/company/saml\_local\_service\_provider/<company\_uuid of WZ\>

    This information can be found in the Admin Console, *Authentication and Authorization* \> *SAML Local Service Provider*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client Key
    
    </td>
    <td valign="top">
    
    OAuth client Key from the OAuth client that you've created.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service URL
    
    </td>
    <td valign="top">
    
    <DWS URL\>/api/v2/auth/token

    Same main URL as the first one, but with a different path.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service User
    
    </td>
    <td valign="top">
    
    OAuth client Key from the OAuth client that you've created.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Service Password
    
    </td>
    <td valign="top">
    
    OAuth client Secret from the OAuth client that you've created.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    API endpoint
    
    </td>
    <td valign="top">
    
    This information can be found in the Admin Console, *Overview* \> *DWS URL*.
    
    </td>
    </tr>
    </table>
    

