<!-- loiof640146ae5bf499c8dc8861724d280ed -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Chatbot Actions

Your forked chatbot offers built-in functionalities of SAP Build Work Zone, advanced edition. You can use these built-in functionalities by configuring chatbot actions.



## chatbot Actions

For the SAP Build Work Zone, advanced edition chatbot, the create workspace action is preconfigured.

To see a list of what the SAP Build Work Zone, advanced edition chatbot can do, go to [https://cai.tools.sap/workzonebot/workzone-bot-master/train/intents](https://cai.tools.sap/workzonebot/workzone-bot-master/train/intents).

The chatbot can deliver specific functionalities in SAP Build Work Zone, advanced edition only if it can call the appropriate services. For example, if you want to create a workspace, the chatbot must call the create workspace service. If you want to create a workspace based on a template, the chatbot must also call the retrieve workspace templates service.

Webhooks provide a means for the chatbot to call these services. Your chatbot can also subscribe to certain changes on SAP Build Work Zone, advanced edition and receive real-time updates.

For more information about configuration and customization, see [SAP Build Work Zone Webhook Documentation](https://jam2.sapjam.com/work_zone/ODataDocs/webhook_reference).



<a name="loiof640146ae5bf499c8dc8861724d280ed__section_eqy_qpq_xkb"/>

## How to Configure an Action

In this example, we configure the create workspace action:

1.  Go to your chatbot on SAP Conversational AI. For example, `https://cai.tools.sap/workzonechatbot/MychatbotName`.

2.  Select the *Build* tab.

3.  Select the *create\_workspace* link.

4.  Select the *Actions* tab.

5.  Go to *Webhook Configuration* and configure a webhook as described in the following section.



### Configure a Webhook

1.  In the *Webhook Configuration* section, choose the edit icon :pencil2: .

2.  Choose the *Headers* tab.

3.  Make sure the URL and the API endpoint are correct:

    -   Enter the correct URL for your company.

        On the chatbot configuration workpage, go to the section for your chatbot \(for example, MychatbotName\). In the *Host URL* field, choose *Copy URL*.

        Example URL:

        ```
        https://dwpdev1.sapjam-integration.com
        ```

    -   The API endpoint is:

        ```
        /api/v2/ai/webhook
        ```

    -   The correct URL is a combination of the host URL and the API endpoint.

        In this example, the correct URL is:

        ```
        https://dwpdev1.sapjam-integration.com/api/v2/ai/webhook
        ```


4.  In the *Authorization* field, enter the OAuth token that was generated for the Alias Account.






### Configure the Payload

The payload defines which data is communicated between SAP Build Work Zone, advanced edition and SAP Conversational AI.

1.  Choose the *Body* tab.


It is mandatory to include an action, context, and parameters.

**Webhook Payload: Create Workspace**


<table>
<tr>
<th valign="top">

Parameter



</th>
<th valign="top">

Required



</th>
<th valign="top">

Values



</th>
<th valign="top">

Comments



</th>
</tr>
<tr>
<td valign="top">

action



</td>
<td valign="top">

required



</td>
<td valign="top">

```
["perform_actions",  "ui5_card"]
```



</td>
<td valign="top">

To create a workspace, perform\_actions is required.



</td>
</tr>
<tr>
<td valign="top">

context



</td>
<td valign="top">

required



</td>
<td valign="top">

```
 {
   "senderId":"{{participant_data.jamId}}"
  },
```



</td>
<td valign="top">

Required



</td>
</tr>
<tr>
<td valign="top">

Example: parameters.actionName



</td>
<td valign="top">

Example: required for perform\_actions



</td>
<td valign="top">

Example: create\_workspace



</td>
<td valign="top">

Currently, we only support create workspace.



</td>
</tr>
<tr>
<td valign="top">

parameters.name



</td>
<td valign="top">

required for create\_workspace



</td>
<td valign="top">

User input



</td>
<td valign="top">

AI derived from user input



</td>
</tr>
<tr>
<td valign="top">

parameters.is\_private



</td>
<td valign="top">

optional for create\_workspace



</td>
<td valign="top">

User input



</td>
<td valign="top">

AI derived from user input



</td>
</tr>
<tr>
<td valign="top">

parameters.template



</td>
<td valign="top">

optional for create\_workspace



</td>
<td valign="top">

User input



</td>
<td valign="top">

AI derived from user input



</td>
</tr>
</table>

Example:

```
{
    "action":"perform_actions",         
     "context":{
        "senderId":"{{participant_data.jamId}}"
    },
    "parameters":{
       "actionName":"create_workspace",
       "name": "{{memory.group_name.raw}}",
       "is_private":{{memory.group_scope.raw}},
 "template": "{{memory.group_template.raw}}"
    }
}
```

Use the same URL and authorization configuration as in create workspace.

**Webhook Payload: Retrieve Workspace Templates**


<table>
<tr>
<th valign="top">

Parameter



</th>
<th valign="top">

Required



</th>
<th valign="top">

Values



</th>
<th valign="top">

Comments



</th>
</tr>
<tr>
<td valign="top">

action



</td>
<td valign="top">

required



</td>
<td valign="top">

perform\_actions



</td>
<td valign="top">

Enumeration value:

```
["perform_actions", "ui5_card"]
```

To create a workspace, use perform\_actions.



</td>
</tr>
<tr>
<td valign="top">

context



</td>
<td valign="top">

required



</td>
<td valign="top">

```
{
   "senderId":"{{participant_data.jamId}}"
}
```



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

parameters.actionName



</td>
<td valign="top">

required for perform\_actions



</td>
<td valign="top">

get\_workspace\_templates



</td>
<td valign="top">

Use this service to retrieve all available workspace templates.



</td>
</tr>
</table>

Example:

```
{
    "action":"perform_actions",
    "context":{
        "senderId":"{{participant_data.jamId}}"
    },
    "parameters":{
       "actionName":"get_workspace_templates"
    }
}
```

