<!-- loio449a2ba8c06845498b98a6fba949711c -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Render Cards with a Chatbot

Your chatbot can render any customized or built-in cards in SAP Build Work Zone, advanced edition.

For example, your chatbot can render the following cards:

-   Leave request card

-   Business News card

-   Search card


> ### Tip:  
> For more information about cards in SAP Build Work Zone, advanced edition, see [UI Integration Cards](../ui-integration-cards-0bf9adc.md).



<a name="loio449a2ba8c06845498b98a6fba949711c__section_y51_1wq_xkb"/>

## Configuration



### Upload a card

If you do not have any cards, you must upload a card to SAP Build Work Zone, advanced edition.

1.  Go to *Administration Console* \> *UI Integration* \> *Cards & Widgets*.

2.  Upload a card by selecting *Upload Card or Widget*.




### Configure the card information

You configure the card information on SAP Conversational AI.

1.  You can set up the training model or fork the training model targeting the corresponding card. For more information, see [**Train Your Chatbot**](https://help.sap.com/docs/SAP_CONVERSATIONAL_AI/a4522a393d2b4643812b7caadfe90c18/5913277b0cfc444583e426148b14b595.html).

2.  In the trigger action, set up a correct webhook URL. For more information, see [**Triggers**](https://help.sap.com/docs/SAP_CONVERSATIONAL_AI/a4522a393d2b4643812b7caadfe90c18/17c5aedf93944d5392f2a27c6039b378.html).

3.  To configure the Authorization, see [**Authentication**](https://help.sap.com/docs/SAP_CONVERSATIONAL_AI/a4522a393d2b4643812b7caadfe90c18/c2daef7a0bc643ca97e62c891a24de54.html).

    Refer to the OAuth token generated for the Alias Account.




### Configure the Payload

The payload defines which data is communicated between SAP Build Work Zone, advanced edition and SAP Conversational AI. To set up the correct payload for the card, you have to retrieve the unique ID of the card that you want to render.

1.  Go to *Administration Console* \> *UI Integration* \> *Cards & Widgets* \> *Custom Card & Widget*.

2.  Choose a card, for example, the *Search Card*.

3.  Copy the unique ID from the card.

    For example:

    ```
    sap.dwp.test.card.searchResult
    ```

4.  Navigate to your chatbot on SAP Conversational AI, for example, `https://cai.tools.sap/workzonechatbot/MychatbotName`.
5.  Go to *Build* \> *Card*.
6.  In the *Webhook Configuration* section, choose :pencil2:.
7.  Choose the *Body* tab.
8.  In the line that starts with "cardID", paste the unique ID within the second pair of quotation marks.

    For example:

    ```
    "cardId":"sap.dwp.test.card.searchResult",
    ```

9.  Choose *Save*.

**Webhook Payload "Cards"**


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

"action"



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

For rendering cards, use `ui5_card`.



</td>
</tr>
<tr>
<td valign="top">

"context"



</td>
<td valign="top">

required



</td>
<td valign="top">

```
{
 "senderId":"       {{participant_data.jamId}}"
    },
```



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

"parameters.cardId"



</td>
<td valign="top">

required for render card



</td>
<td valign="top">

```
card.explorer.line.card 
```



</td>
<td valign="top">

Copied from card information.



</td>
</tr>
<tr>
<td valign="top">

"parameters.widgetType"



</td>
<td valign="top">

optional



</td>
<td valign="top">

```
["sapCard", "sapWidget"]
```



</td>
<td valign="top">

The default is "sapWidget". Depending on the card type, you can use "sapCard" or "sapWidget".



</td>
</tr>
</table>

Example:

```
{
    "action":"ui5_card",
    "context":{
        "senderId":"{{participant_data.jamId}}"
    },
    "parameters":{
       "cardId":"card.explorer.line.card",
       "widgetType":"sapCard"
    }
}
```

