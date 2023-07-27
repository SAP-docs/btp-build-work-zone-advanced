<!-- loiob65c218d16b44532abeec4ea1cf0e091 -->

# Integrating Cards into a Site

Learn how to add UI5 integration cards to workpages in your site.

Cards can come from the following sources:

-   Out-of-the-box cards - provided by SAP. For example, the Web Content Card.

-   Uploaded cards - custom cards that are created by a developer and sent to you in a ZIP file for uploading.

-   Content Packages - cards that are used in a content package with other content and are bundled together in a ZIP file that can easily be uploaded and installed to your subaccount.

    For more information, see [Content Packages](content-packages-da203f9.md).


The cards are displayed in the *Cards* screen in the *Administration Console* under *UI Integration*.

**Out-of-the-box cards**

The Web Content card is an out-of-the-box card that you can use to embed content from any web page to display on a workpage. The following table explains the end to end flow of how to add a Web Content card to your site.


<table>
<tr>
<th valign="top">

Step



</th>
<th valign="top">

Persona



</th>
<th valign="top">

More information



</th>
</tr>
<tr>
<td valign="top">

1. Enable the Web Content Card.



</td>
<td valign="top">

Administrator



</td>
<td valign="top">

You can do this in the *Cards* screen in the Administration Console.



</td>
</tr>
<tr>
<td valign="top">

2. Configure the card - the title, subtitle, and the height.



</td>
<td valign="top">

Administrator



</td>
<td valign="top">

1.  From the *Cards* screen in the *Administration Console*, filter the cards from the *Providers* dropdown list and select *Out-Of-The-Box*.

2.  Click *Configure* on the card.

3.  Define the following configuration settings:

    -   Enter the URL of the web content that you want to display in the widget.

        > ### Note:  
        > Check if the web content is displayed properly in the preview. Sometimes web content can't be loaded to the card because the owner of the web content has restricted the embedding within frames. In this case, please contact the owner of the web content to lift this restriction for you.

    -   Enter a title and a subtitle. The title and subtitle are displayed as the card header.

    -   Specify the height of the card in pixels.

        The default height is 200 pixels. The height has to be greater than zero.

        > ### Note:  
        > Don't forget to specify the height otherwise the content that a user wants to embed into the card can collapse to zero.


4.  Save your changes.



</td>
</tr>
<tr>
<td valign="top">

3. Add the card to a workpage



</td>
<td valign="top">

Administrator, End User



</td>
<td valign="top">

You can do this using the page designer, which opens a widget gallery that you access in the workpage when you edit it.

Click *Add Widget* to open the widget gallery and select *Cards* .

For more information, see [How to Add Content to Workspaces](how-to-add-content-to-workspaces-19bf8aa.md).



</td>
</tr>
</table>

**Uploaded cards**

Uploaded cards can either be those cards that your developer has created and deployed or those that have been given to you by a provider to upload.

The following table is an end to end flow of how to add custom cards to your site.

> ### Note:  
> If a provider has sent you the card file to upload, you only need to do steps from number 4 and onwards.


<table>
<tr>
<th valign="top">

Step



</th>
<th valign="top">

Persona



</th>
<th valign="top">

More information



</th>
</tr>
<tr>
<td valign="top">

1. Set up your development environment.



</td>
<td valign="top">

Developer



</td>
<td valign="top">

For more information, see [Initial Setup](https://help.sap.com/viewer/7d3b9c7211ca4d7a9630b524205ee836/Cloud/en-US/87a6a5e1c64c4df49747b82a540701f8.html)



</td>
</tr>
<tr>
<td valign="top">

2. Develop a UI integration card.



</td>
<td valign="top">

Developer



</td>
<td valign="top">

Develop your own UI integration card or download a sample card from the SAPUI5 demo kit and configure it as needed.

For more information, see

-   [Creating a UI Card](https://help.sap.com/viewer/7d3b9c7211ca4d7a9630b524205ee836/Cloud/en-US/3fd1bdf42ff0417f8adec8567908e901.html).

-   To download a demo SAPUI5 card, go to [UI Integration Cards Explorer.](https://sapui5.hana.ondemand.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/list/quickLinks)



</td>
</tr>
<tr>
<td valign="top">

3. Deliver the card.



</td>
<td valign="top">

Developer, Administrator



</td>
<td valign="top">

Deliver the card in one of the following ways:

-   Deploy the card to the content repository so that it appears in the *Cards* screen in the *Administration Console*. For more information, see [Deploying a UI Card](https://help.sap.com/viewer/7d3b9c7211ca4d7a9630b524205ee836/Cloud/en-US/35e6049aff8b4495903ee16303508a76.html).

-   Package a developed card into a ZIP file and send it to the administrator who then uploads it from the *Cards* screen in the *Administration Console*.




</td>
</tr>
<tr>
<td valign="top">

4. Enable the card.



</td>
<td valign="top">

Administrator



</td>
<td valign="top">

Enable cards by using the toggle button. By doing this, you're making the card available to users who can then select the card in the page designer widget gallery and add it to a workpage.



</td>
</tr>
<tr>
<td valign="top">

5. Configure the card \(if the card is configurable\).



</td>
<td valign="top">

Administrator



</td>
<td valign="top">

Click *Configure* on the card.



</td>
</tr>
<tr>
<td valign="top">

6. Customize the card \(if necessary\).



</td>
<td valign="top">

End User



</td>
<td valign="top">

For some cards, users can configure which data they want to display on the card.



</td>
</tr>
<tr>
<td valign="top">

7. Add card to a workpage.



</td>
<td valign="top">

Administrator, End User



</td>
<td valign="top">

For more information, see [How to Add Content to Workspaces](how-to-add-content-to-workspaces-19bf8aa.md).



</td>
</tr>
</table>

> ### Note:  
> If a developer makes changes to a card that you've already added to your workpage, you'll need to remove it and add it again after the changes have been made.

