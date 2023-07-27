<!-- loiod3e18a9964be4dd392ea3eee33d4e3bd -->

# Widget Builders

Using widget builders, you can create and customize widgets that display your site content in an HTML page, without editing the JavaScript in which they're written.

On the *UI Integration* \> *Widget Builders* page, you can build widgets from a given range of common widget types. The widgets are complex HTML5 components that use a preset structure to present content in external web pages.

The following widget builders are available:

-   *Feed Widget Builder*: Feed widgets embed a feed in an external web page.
-   *Recommendation Widget Builder*: Recommendation widgets embed content, people, or workspace recommendations in an external web page.
-   *Share Widget Builder*: Share widgets embed a share link \(like other social network share buttons\) in an external web page, and post the page to either workspace or member feeds when chosen in the external web page.



<a name="loiod3e18a9964be4dd392ea3eee33d4e3bd__section_md4_msw_vkb"/>

## How to Use the Widget Builders

1.  On the *UI Integration* \> *Widget Builders* page, choose the widget builder from which you want to create a widget.

2.  Enter the properties as required.

    For details about the settings and their values, see the following sections.

3.  At any time during configuration, choose *Preview* to see both a rendered example of the current settings and an example of the script that is set using the current options.

4.  When you're finished configuring, choose *Preview* to reflect the latest change in the JavaScript code.

5.  Copy the JavaScript code and paste it into your web page within script tags.

6.  Ensure that you have the div element with the ID you set in your widget in your HTML page.

    Only this way can the script be called and the widget displayed within the div element.

7.  Add a div tag above the JavaScript that you pasted into the HTML body in the previous step as follows:

    -   Place the div tag before the JavaScript, or use something like the jQuery `.ready()` function, so that the order of script elements in the page doesn't matter.

    -   Use the same ID for the div tag as you set or accepted in the *Widget div ID* field of the widget builder.

    -   Include style statements that set the width and height of the widget if you don't want the widget to inherit the dimensions of its container element.





<a name="loiod3e18a9964be4dd392ea3eee33d4e3bd__section_pw2_4rw_vkb"/>

## Feed Widget Builder

This table explains the settings and their values.


<table>
<tr>
<th valign="top">

Setting



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

*Widget div ID*



</td>
<td valign="top">

Unique ID for the HTML div element that contains the widget

The div ID is used in the widget JavaScript that you generate using the form, and it must match the div ID in the HTML page that you use as the container for the widget. Accept the default ID of *myDiv* unless there are other divs in the same page with the same ID, as the div ID must be unique within the page in which you add the widget.



</td>
</tr>
<tr>
<td valign="top">

*Authentication type*



</td>
<td valign="top">

The options are:

-   *Single-use Token*: uses a single-use token provided by the SAP Build Work Zone, advanced edition API. **\[Recommended\]** 

    For more information about single-use tokens, see the [SAP Build Work Zone OData API Documentation](https://jam2.sapjam.com/work_zone/ODataDocs/ui).

    After obtaining a single-use token, it needs to be included in the parameters passed into the `sapjam.feedWidget.create` function call in the widget initialization script. For example:

    ```
    sapjam.feedWidget.init(
        "https://workzonebetatest.workzone.cfapps.eu10.hana.ondemand/widget/v1/feed",
        "single_use_token");
    var w = sapjam.feedWidget.create("myDiv",{
        type: "follows",
        avatar: false,
        post_mode: "inline",
        reply_mode: "inline"
        single_use_token: '883a5486-62af-407a-a5ca-cec6dcf259dc'
    });
    ```

    > ### Note:  
    > The other authentication types aren't recommended for use in production.

-   *Login from your Identity Provider*: uses an existing session, or it presents your identity provider's sign-on page and then redirects to the requested feed widget after the user signs in. **\[Not recommended: included for legacy support\]**
-   *Login from your Identity Provider in pop-up*: uses an existing session, or it presents your identity provider's sign-on page in a new page or tab. Upon successful sign-on, the new page closes, and the original requesting page redirects to the requested feed widget. **\[Not recommended: included for legacy support\]**
-   *Pre-existing**session*: uses an existing session, or it displays an error message if one isn't found. **\[Not recommended: included for legacy support\]**



</td>
</tr>
<tr>
<td valign="top">

*Feed type*



</td>
<td valign="top">

The options are:

-   *Company Feed*: displays the same feed that you would see in the Company tab.
-   *My Follows Feed*: displays the same feed that you would see in the Home tab.
-   *Workspace Feed*: displays the same feed, or feeds, for one or more workspaces. Enter one or more *Workspace IDs*.

    If only one workspace ID is entered in the Workspace IDs field, the widget displays the same feed as is displayed on the *Feed Updates* tab for that particular workspace. If multiple workspace IDs are provided, then the widget displays a dropdown menu from which you can select a specific workspace or *All workspaces*. Selecting a workspace displays the feed for that workspace, and any posts made while viewing that feed are posted to the selected workspace's wall. If *All workspaces* is selected, the widget displays the combined feed for all workspaces. Posting is disabled while viewing the *All workspaces* feed.

-   *External Object Feed*: displays the feed for an external object or business record. This option requires the entry of the following fields:

    -   In the *External ID* field, enter the value of the *Exit* property returned by the OData API’s `ExternalObjects` endpoint. This value is typically the external OData URL for the object.
    -   In the *External type* field, enter the value of the *ObjectType* property returned by the OData API’s `ExternalObjects` endpoint. This value is the *External Type* value for the object.

    The feed behaves differently depending on whether the logged-in user can view the full feed history for that particular external object type:

    -   **Default behavior**: If feed history isn't enabled, or the user isn't authorized to view the full feed history for the object, they only see the feed updates that are explicitly routed to them, such as by a distribution list.
    -   **Feed History**: To enable feed history for an external object, a company administrator must configure the necessary authentication settings and external object types in the *External Applications* page of the Administration Console. From this page, administrators can enable the feed history for specific external object types. Once feed history is enabled, when a user views an external object feed, the Feed widget calls back to the external application to determine whether the user has permission to view that object. If authorization succeeds, the Feed widget displays the entire feed history for the external object. If authorization fails, the widget reverts back to the default behavior.

    For more information about external objects, see [External Solutions](external-solutions-d51825b.md).

-   *External Wall Feed*: displays the same feed that you would see in the Home tab if you were to log in as an external user. This option requires you to enter the following fields:
    -   *External ID*: enter any string that you want to use to uniquely identify the feed.
    -   *Name*: enter a user-friendly name for the feed. The name shows up in the feed when you comment on the topic, which appears as `"John Doe commented on <name>"`.
    -   *External URL*: \[Optional\] enter any fully qualified external URL. If this property is provided, then the topic name is rendered in the feed as a link that opens this URL in a new tab when a user clicks it.

-   *Mentions Feed*: displays a feed of messages in which the user was mentioned, including all `@@notify` mentions. This is the same as the feed that is shown when a user chooses the *@<user\_name\>* option on their home page.
-   *Content Item Feed*: displays the feeds related to specific content items. This option requires that you enter the following fields:
    -   *Content Type*: enter the content type that you want the feed items for, such as *Document*, *Discussions, Ideas, Questions*, or *Blog*.
    -   *Content Item ID*: enter the ID of the specific content item for which you want to display the feed. To get this value, view the page that displays the item, and copy the ID from the last segment of the URL for that page.




</td>
</tr>
<tr>
<td valign="top">

*Style*



</td>
<td valign="top">

Select the styling that you want to apply to the widget.



</td>
</tr>
<tr>
<td valign="top">

*Show Profile Images in Feed*



</td>
<td valign="top">

Shows thumbnails of the creators of each post in the feed.



</td>
</tr>
<tr>
<td valign="top">

*Show User Profile Image*



</td>
<td valign="top">

Shows a thumbnail of the requesting user at that top of the feed.



</td>
</tr>
<tr>
<td valign="top">

*Live Feed Updates*



</td>
<td valign="top">

Sets whether updates are automatic or by notification message.



</td>
</tr>
<tr>
<td valign="top">

*Mobile Mode*



</td>
<td valign="top">

Presents only mobile-capable features in the feed.



</td>
</tr>
<tr>
<td valign="top">

*Filter by the Following Hashtags*



</td>
<td valign="top">

Allows you to filter the feed based on the hashtags that you enter.



</td>
</tr>
<tr>
<td valign="top">

*Post Mode*



</td>
<td valign="top">

The post mode refers to the text entry box at the top of the feed in which you can post a comment. The options are:

-   *Inline*: A text entry box is displayed at the top of the feed widget.
-   *Link to*: A link to the feed is displayed at the top of the feed widget.
-   *Hidden*: There isn't an option for posting at the top of the feed widget.



</td>
</tr>
<tr>
<td valign="top">

*Reply Mode*



</td>
<td valign="top">

The reply mode refers to the options to reply to other peoples' comments. The options are:

-   *Inline*: A *Reply* control, that opens a reply text box, is displayed below a user's comment.
-   *Link to*: A link to the feed is displayed below a user's comment.
-   *Hidden*: There isn't an option for replying to user's comments.



</td>
</tr>
<tr>
<td valign="top">

*Hide Like Links*



</td>
<td valign="top">

Shows or hides users' likes as a post in the feed as replies.



</td>
</tr>
<tr>
<td valign="top">

*Hide Bookmark Links*



</td>
<td valign="top">

Shows or hides users' bookmarks in the feed as replies.



</td>
</tr>
<tr>
<td valign="top">

*Limit feed items to a maximum of*



</td>
<td valign="top">

Allows you to set the maximum number of feed items.



</td>
</tr>
</table>



<a name="loiod3e18a9964be4dd392ea3eee33d4e3bd__section_jkj_1hx_vkb"/>

## Recommendations Widget Builder

This table explains the settings and their values.


<table>
<tr>
<th valign="top">

Setting



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

*Widget div ID*

*Authentication Type* 



</td>
<td valign="top">

See the description in the *Feed Widget Builder* section.



</td>
</tr>
<tr>
<td valign="top">

*Type*



</td>
<td valign="top">

Select the layout of the recommendations that you want to use.



</td>
</tr>
<tr>
<td valign="top">

*\# of Recommendations*



</td>
<td valign="top">

Select the number of recommendations that you want to display.



</td>
</tr>
<tr>
<td valign="top">

*Recommendation Type*



</td>
<td valign="top">

Select the type of recommendations that you want to display, such as content, people, or workspaces.



</td>
</tr>
</table>



<a name="loiod3e18a9964be4dd392ea3eee33d4e3bd__section_g3r_43x_vkb"/>

## Share Widget Builder

This table explains the settings and their values.


<table>
<tr>
<th valign="top">

Setting



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

*Widget element ID* 



</td>
<td valign="top">

The ID of the HTML DOM element that opens the widget.



</td>
</tr>
<tr>
<td valign="top">

*Create default widget button*



</td>
<td valign="top">

Select the field to have a widget button included in the embedded widget.

> ### Note:  
> If you deselect this option, you must add the text or icon to be displayed in the div element in which the widget is displayed.



</td>
</tr>
<tr>
<td valign="top">

*Page URL*



</td>
<td valign="top">

Enter the URL of the external web page in which the widget is embedded. The initial content of this page is displayed in the feed.



</td>
</tr>
<tr>
<td valign="top">

*Workspace ID \(optional\)*



</td>
<td valign="top">

Enter the ID for the workspace in which you want the external page to have an entry added to that workspace's feed.

You can get this ID from the last segment of the workspace URL. For example, in the URL`https://.../overview_page/6jAzl7p5W9gtIyEv6O7TAQ`, the ID would be `6jAzl7p5W9gtIyEv6O7TAQ`.

> ### Note:  
> If you leave this field blank, the widget adds the shared content to your company's members' walls.



</td>
</tr>
<tr>
<td valign="top">

*Use custom branding*



</td>
<td valign="top">

To include your company logo in the shared content. The logo is configured under *Theming & Branding* \> *Local Theme Designer*.



</td>
</tr>
</table>

