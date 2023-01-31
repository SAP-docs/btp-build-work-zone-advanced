<!-- loio1b275f8e2b624a1092f07b864b34515c -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Chatbots

You can configure a chatbot that interacts with users and helps them with their tasks. You can also train the chatbot to perform actions and render cards to support different scenarios.



<a name="loio1b275f8e2b624a1092f07b864b34515c__section_op4_qsd_wkb"/>

## Create a Chatbot

There are different ways to create a chatbot: You can create your own chatbot or implement the SAP Build Work Zone, advanced edition chatbot.

> ### Tip:  
> We recommend that you implement the SAP Build Work Zone, advanced edition chatbot. This chatbot requires some simple configurations before it’s ready to use.



### Create your own chatbot

You can create your own chatbot using the SAP Conversational AI platform. See [https://cai.tools.sap/](https://cai.tools.sap/).



### SAP Build Work Zone, advanced edition chatbot

> ### Note:  
> To implement the SAP Build Work Zone, advanced edition chatbot, sign up for SAP Conversational AI chatbot as a base for your chatbot, as it has some built-in functionalities delivered by SAP Build Work Zone, advanced edition. Go to [https://cai.tools.sap/signup](https://cai.tools.sap/signup) and create an account.

You can choose to implement the SAP Build Work Zone, advanced edition chatbot as a chatbot that contains all the functionalities or a chatbot that contains only one functionality as described in the table.


<table>
<tr>
<th valign="top">

Functionality



</th>
<th valign="top">

chatbot



</th>
</tr>
<tr>
<th valign="top">

All functionalities



</th>
<th valign="top">

[https://cai.tools.sap/workzone/workzone-bot](https://cai.tools.sap/workzone/workzone-bot)



</th>
</tr>
<tr>
<td valign="top">

Create workspace



</td>
<td valign="top">

[https://cai.tools.sap/workzone/create-workpspace-bot](https://cai.tools.sap/workzone/create-workpspace-bot)



</td>
</tr>
<tr>
<td valign="top">

Business news



</td>
<td valign="top">

[https://cai.tools.sap/workzone/business-news-bot](https://cai.tools.sap/workzone/business-news-bot)



</td>
</tr>
<tr>
<td valign="top">

Search



</td>
<td valign="top">

[https://cai.tools.sap/workzone/search-bot](https://cai.tools.sap/workzone/search-bot)



</td>
</tr>
<tr>
<td valign="top">

Simple leave request



</td>
<td valign="top">

[https://cai.tools.sap/workzone/simple-leave-request-bot](https://cai.tools.sap/workzone/simple-leave-request-bot)



</td>
</tr>
<tr>
<td valign="top">

Smart talk \(for example, greetings, weather, or jokes\)



</td>
<td valign="top">

[https://cai.tools.sap/workzone/smart-talk](https://cai.tools.sap/workzone/smart-talk)



</td>
</tr>
</table>

The first thing that you need to do is fork the chatbot. Forking means that you make a copy of the chatbot repository that includes all the intents and skills. You can also choose to fork partial intents. By forking the chatbot, you create your own independent branch of the chatbot that you can customize to your needs.

1.  Go to [https://cai.tools.sap/workzone/workzone-bot](https://cai.tools.sap/workzone/workzone-bot) and log on to SAP Conversational AI.

2.  To start forking the chatbot, select *Fork*.

    Your forked chatbot is created with a default name \("workzone-chatbot"\).

3.  We recommend that you rename the chatbot. To rename the chatbot, choose :gear: *Settings*.

    Under *Options*, in the *chatbot Settings* section, enter a name for your chatbot and choose *Rename*.

4.  In the *Data policy* tab, choose the type of data that your chatbot is allowed to use.

When you fork the chatbot, all the actions are copied to your chatbot.

Options:

-   When you fork a skill, all the related intents are copied.
-   You can choose to fork only intents.
-   When there are updates to the base chatbot, your forked chatbot isn’t updated automatically. You can choose whether or not you want to fork a new feature.
-   In *SAP Conversational AI*, you can set your chatbot to private, so that other users can’t see your chatbot. To set your chatbot to private, go to your chatbot and choose *Danger Zone* \> *MAKE PRIVATE*.


> ### Note:  
> You can only edit your forked chatbot.



<a name="loio1b275f8e2b624a1092f07b864b34515c__section_tgk_bwd_wkb"/>

## Establish a Connection Between the Chatbot and SAP Build Work Zone, Advanced Edition

The chatbot and SAP Build Work Zone, advanced edition are separate applications, so you need to establish a connection between them. To connect the chatbot to SAP Build Work Zone, advanced edition, you can use the built-in *SAP Jam Collaboration* connector in SAP Conversational AI.

You must be logged on to SAP Conversational AI to perform the following steps. Keep the internet browser tab open, as you have to copy data to and from this page.

1.  In SAP Conversational AI, go to your chatbot \(for example, `https://cai.tools.sap/workzonechatbot/MychatbotName`\).

2.  Choose the *Connect* tab.

3.  From the *Users channels* list, under *Third-party integrations,*select *SAP Jam Collaboration*.

4.  A configuration window opens and you’re automatically taken to step *3*.

    > ### Note:  
    > Skip steps 1 and 2 in the configuration window.




<a name="loio1b275f8e2b624a1092f07b864b34515c__section_rgh_hsd_wkb"/>

## Configure a Chatbot in the Administration Console

1.  Go to *Administration Console* \> *External Integrations* \> *Chatbot Configuration*.

    A list of previously configured chatbots is displayed. You can edit or delete a previously created chatbot.

2.  To create a new chatbot, choose *New Chatbot*.

3.  Enter your preferred chatbot name and choose *Next*.

    The chatbot configuration consists of the following parts: OAuth Client, Alias Account, and Push Notification Subscription.




### Register a new OAuth Client

To authorize the chatbot to access the SAP Build Work Zone, advanced edition API, you must register it as an OAuth client. For more information, see [Add an OAuth Client](https://help.sap.com/viewer/b03c84105ff74f809631e494bd612e83/Cloud/en-US/b3c804e1f999448b8011a475fea1da6c.html "") :arrow_upper_right:.

In the following table, the configuration steps are explained. Note that different steps \(left column\) are done in different places: In SAP Build Work Zone, advanced edition \(middle column\) and in SAP Conversational AI \(right column\). As you move through the steps, check in which application the step takes place.

At the same time, you have to copy data between SAP Conversational AI and SAP Build Work Zone, advanced edition. To navigate more easily, we recommend that you place the windows side by side or stacked on your screen \(so that the browser tabs are aligned with the documentation table\).

****


<table>
<tr>
<th valign="top">

Step



</th>
<th valign="top">

Chatbot Configuration

*Administration Console* \> *External Integration* \> *Chatbot Configuration* \> *New Chatbot*



</th>
<th valign="top">

SAP Conversational AI

https://cai.tools.sap/workzonechatbot/MychatbotName



</th>
</tr>
<tr>
<td valign="top">

**1**



</td>
<td valign="top">

 



</td>
<td valign="top">

1. In the browser, from the address bar, copy the URL including the chatbot's name. Exclude any parts of the URL after the chatbot's name, such as `/connect`.

Example URL: `https://cai.tools.sap/workzonechatbot/MychatbotName`



</td>
</tr>
<tr>
<td valign="top">

**2**



</td>
<td valign="top">

2. Paste this partial URL into the *Integration URL* field.

Skip the other entry fields.



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

**3**



</td>
<td valign="top">

3. Choose *Next*.



</td>
<td valign="top">

 



</td>
</tr>
</table>



### Manage Alias Account

You need an alias account as a system user to work with the chatbot. A system user allows you to post to SAP Build Work Zone, advanced edition with your chatbot. For more information, see [Alias Accounts](https://help.sap.com/viewer/b03c84105ff74f809631e494bd612e83/Cloud/en-US/8857401c21b94dec9143cf14fa57d2d3.html "As a Company administrator, you can create user alias accounts and assign users to the account using a specific email address.") :arrow_upper_right:.

In the following table, the configuration steps are explained. Note that different steps \(left column\) are done in different places: In SAP Build Work Zone, advanced edition \(middle column\) and in SAP Conversational AI \(right column\). To navigate more easily, we recommend that you place the windows side by side or stacked on your screen.

**Alias Account**


<table>
<tr>
<th valign="top">

Step



</th>
<th valign="top">

Chatbot Configuration

*Administration Console* \> *External Integration* \> *Chatbot Configuration* \> *New Chatbot*



</th>
<th valign="top">

SAP Conversational AI

https://cai.tools.sap/workzonechatbot/MychatbotName



</th>
</tr>
<tr>
<td valign="top">

**1**



</td>
<td valign="top">

1. From the *Basic Profile Information* section, copy the *Alias UserID*.



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

**2**



</td>
<td valign="top">

 



</td>
<td valign="top">

2. Paste the *Alias UserID* into the *Alias User ID* field.



</td>
</tr>
<tr>
<td valign="top">

**3**



</td>
<td valign="top">

3. In the *Users* section, choose *Add OAuth2 Access Token*.

An OAuth2 Access Token is generated automatically.



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

**4**



</td>
<td valign="top">

4. Copy the OAuth2 Access Token.



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

**5**



</td>
<td valign="top">

 



</td>
<td valign="top">

5. Paste the OAuth2 Access Token into the *OAuth2 Token* field.

6. Skip the other entry fields.



</td>
</tr>
<tr>
<td valign="top">

**6**



</td>
<td valign="top">

Choose *Next*.



</td>
<td valign="top">

 



</td>
</tr>
</table>



### Push Notifications

There are many events that can trigger a notification from your chatbot. You can choose from the following categories of events: Alias Account Notification, Content Notification, Workspace Notification, and Forum Notification.

In the following table, the configuration steps are explained. Note that different steps \(left column\) are done in different places: In SAP Build Work Zone, advanced edition \(middle column\) and in SAP Conversational AI \(right column\). To navigate more easily, we recommend that you place the windows side by side or stacked on your screen.

**Push Notification**


<table>
<tr>
<th valign="top">

Step



</th>
<th valign="top">

Chatbot Configuration

*Administration Console* \> *External Integration* \> *Chatbot Configuration* \> *New Chatbot*



</th>
<th valign="top">

SAP Conversational AI

https://cai.tools.sap/workzonechatbot/MychatbotName



</th>
</tr>
<tr>
<td valign="top">

**1**



</td>
<td valign="top">

1. In the *Event List* section, select all of the events for which you want to receive a notification from your chatbot.



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

**2**



</td>
<td valign="top">

2. From the *Token\** section, copy the displayed token.

> ### Note:  
> Don’t regenerate the token. If you regenerate the token, the current token becomes invalid.



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

**3**



</td>
<td valign="top">

 



</td>
<td valign="top">

3. Paste the token into the *Webhook Token* field.



</td>
</tr>
<tr>
<td valign="top">

**4**



</td>
<td valign="top">

4. In the *Manage Push Notification Subscription*window, next to the *Host URL* entry, choose *Copy URL*.

Example URL: `https://dwpdev1.sapjam-integration.com` .



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

**5**



</td>
<td valign="top">

 



</td>
<td valign="top">

5. Paste the URL into the *SAP Build Work Zone Base URL* field.



</td>
</tr>
<tr>
<td valign="top">

**6**



</td>
<td valign="top">

 



</td>
<td valign="top">

6. Choose *CONNECT*.

A popup window informs you whether or not the channel was created successfully.

A callback URL is generated automatically.

> ### Note:  
> Don’t close the window. Make sure you copy the callback URL from the window first.



</td>
</tr>
<tr>
<td valign="top">

**7**



</td>
<td valign="top">

 



</td>
<td valign="top">

7. Copy the Callback URL.



</td>
</tr>
<tr>
<td valign="top">

**8**



</td>
<td valign="top">

8. Paste the callback URL into the *Callback URL* field below the *Description* box.



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

**9**



</td>
<td valign="top">

9. Choose *Finish*.

Your chatbot is created and you're taken to the chatbot configuration workpage.



</td>
<td valign="top">

Choose *Close*.



</td>
</tr>
<tr>
<td valign="top">

**10**



</td>
<td valign="top">

From the chatbot configuration workpage, you can toggle push notifications.



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

**11**



</td>
<td valign="top">

As a final step, refresh the workpage and make sure that you get the success message.



</td>
<td valign="top">

 



</td>
</tr>
</table>



<a name="loio1b275f8e2b624a1092f07b864b34515c__section_d53_hy3_vkb"/>

## Enable the Chatbot Launcher

This option is only available if you’ve already configured a chatbot.

1.  Go to *Administration Console* \> *External Integrations* \> *Chatbot Configuration*.

2.  Enable *Display Chatbot Launcher*.

    If several chatbots have been configured, you can choose a chatbot from the dropdown list.




<a name="loio1b275f8e2b624a1092f07b864b34515c__section_wrd_3x2_wkb"/>

## Configure Your Forked Chatbot

Some configuration is required if you want to use the built-in functionalities of the SAP Build Work Zone, advanced edition chatbot. In addition to the basic functionality, the chatbot can do the following:

-   Perform actions that are specific to SAP Build Work Zone, advanced edition.

    See [Chatbot Actions](chatbot-actions-f640146.md).

-   Render any customized or built-in cards.

    See [Render Cards with a Chatbot](render-cards-with-a-chatbot-449a2ba.md).


