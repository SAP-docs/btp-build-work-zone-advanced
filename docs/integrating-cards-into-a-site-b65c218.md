<!-- loiob65c218d16b44532abeec4ea1cf0e091 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Integrating Cards into a Site

Learn how to add UI integration cards to workpages in your site.

Cards can come from the following sources:

-   Out-of-the-box cards - provided by SAP.

-   Custom cards - custom cards that are created by a developer and either directly deployed from SAP Business Application Studio to the subaccount, or uploaded as local app card visualization ZIP files.

    > ### Note:  
    > If you directly deploy the card from SAP Business Application Studio to the subaccount, there is no need to create a local app. The deployed card is already associated with an app which is assigned to the *Everyone* role. If you choose to upload a ZIP file that contains the card, you need to create a local app in the Content Manager, and then upload the ZIP file as an app visualization. For more information, see [Configuring Apps with a Card Visualization](configuring-apps-with-a-card-visualization-25b3d37.md).
    > 
    > Once the card is added to the Content Manager, you can go to the *Cards* screen in the Administration Console to perform any configurations you need for the card, such as creating a destination, or enabling the card.
    > 
    > The card is associated with an app, therefore access to the card depends on the app role assignment. The user must be assigned to the same role as the role that is assigned to the app. To allow all users to access the card, assign the app to the *Everyone* role. To retrict the access even further, assign the app to a specific role.

-   Content Packages - cards that are used in a content package with other content and are bundled together in a ZIP file that can easily be uploaded and installed from the Content Manager screen in the Administration Console. You don't have to upload the cards in a content package separately.

    For more information, see [Content Packages](content-packages-da203f9.md).


The available cards are displayed in the *Cards* screen in the *Administration Console* under *UI Integration*.

**Out-of-the-box cards**

SAP provides the following two out-of-the box cards:

-   **Web Content Card**: a card that you can use to embed other web pages as content of a UI Integration Card.

-   **Button Card**: a component card that renders as a fully configurable button that includes a title, subtitle, icon, and more.



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

1. Enable the card with the toggle to make it available for end users so they can add it to their workpages.

</td>
<td valign="top">

Administrator

</td>
<td valign="top">

In the Administration Console, go to *UI Integration* \> *Cards* to enable the card.

</td>
</tr>
<tr>
<td valign="top">

2. Configure the card with the various settings for your card.

</td>
<td valign="top">

Administrator

</td>
<td valign="top">

1.  In the *Cards* screen of the *Administration Console*, you will see the available *Out-Of-The-Box* cards.

2.  Click *Configure* on the card.

3.  Define the following configuration settings:


    <table>
    <tr>
    <th valign="top">

    **Web Content Card**
    
    </th>
    <th valign="top">

    **Button Card**
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    -   Enter the URL of the web content that you want to display in the widget.

        > ### Note:  
        > Check if the web content is displayed properly in the preview. Sometimes web content can't be loaded to the card because the owner of the web content has restricted the embedding within frames. In this case, please contact the owner of the web content to lift this restriction for you.

    -   Enter a title and a subtitle. The title and subtitle are displayed as the card header.

    -   Specify the height of the card in pixels.

        The default height is 200 pixels. The height must be greater than zero.

        > ### Note:  
        > Don't forget to specify the height otherwise the content that a user wants to embed into the card can collapse to zero.

    -   *Save* your settings.


    
    </td>
    <td valign="top">
    
    -   Under the *General* area, you can:

        -   Use the toggle button to see the card background as well as the filling for the background.

        -   Give the card a title, a subtitle, and select an icon from the dropdown list of icons.

        -   Add more information if required.

        -   Select font sizes for the title, subtitle, and icon.


    -   In the *Colors* area, you can:

        -   Use the slider to determine background opacity.

        -   Select background color, text color, and icon colors.


    -   In the *Border* area, you can:

        -   Use the toggle button to show a border.

        -   Select a color for your border.

        -   Determine the border width and radius.


    -   In the *Layout & Alignment* area, you can:

        -   Select the layout direction, icon position, as well as horizontal and vertical alignment.


    -   In the *Interaction* area, you can:

        -   Use the toggle to make your button clickable.

        -   Enter the URL for the button.

        -   Use the toggle to open the button in a new tab.

        -   Use the toggle to enable hovering.


    -   *Save* your settings.



    
    </td>
    </tr>
    </table>
    



</td>
</tr>
<tr>
<td valign="top">

3. Add the card to a workpage.

</td>
<td valign="top">

Administrator, End User

</td>
<td valign="top">

You can do this using the workpage editor.

In edit mode, click *Add Content* and select *Cards*.

For more information, see [How to Use the Workpage Editor](how-to-use-the-workpage-editor-9164929.md).

</td>
</tr>
</table>

**Custom cards**

Custom cards can either be those cards that your developer has created \(see steps 1-3 below\) or those given to you by a provider \(in this case start you can start from step 4 below\).

The following table is an end to end flow of how to add custom cards to your site.


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

Developer

</td>
<td valign="top">

Either deploy the card from SAP Business Application Studio or package it into a ZIP file and download it on your system to pass it on to an administrator.

</td>
</tr>
<tr>
<td valign="top">

4. Upload the card.

</td>
<td valign="top">

Administrator

</td>
<td valign="top">

To upload a card, you need to create a local app with a card visualization in the Content Manager.

For more information, see [Configuring Apps with a Card Visualization](configuring-apps-with-a-card-visualization-25b3d37.md).

Once uploaded, the card appears in the *Cards* screen in the Administration Console under the *Uploaded Cards* section.

</td>
</tr>
<tr>
<td valign="top">

5. Enable the card.

</td>
<td valign="top">

Administrator

</td>
<td valign="top">

This step is done in the Administration Console in the *Cards* screen that you can access as follows:

1.  From the Content Manager, select the :globe_with_meridians: to open the site directory.

2.  On the site tile, click <span class="SAP-icons-V5"></span> to open the runtime site.

3.  From your avatar, select *Administration Console* and go to to *UI Integration* \> *Cards*.

Enable cards by using the toggle button. By doing this, you're making the card available to workspace administrators who can then select the card in the workpage editor's content finder and add it to a workpage.

</td>
</tr>
<tr>
<td valign="top">

6. Configure the card \(if the card is configurable\).

</td>
<td valign="top">

Administrator

</td>
<td valign="top">

Click *Configure* on the card to select a destination and to do other configurations.

> ### Note:  
> If the card already inlcudes a destination with a specific name and a desitnation already exists with this name, then the card will work directly without configuring a destination.



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

For more information, see [How to Use the Workpage Editor](how-to-use-the-workpage-editor-9164929.md).

</td>
</tr>
<tr>
<td valign="top">

8. Customize card \(if necessary\).

</td>
<td valign="top">

End User

</td>
<td valign="top">

For some cards, users can configure which data they want to display on the card.

</td>
</tr>
</table>

> ### Note:  
> If a new version of the card is available, you need to upload the card again as explained in Step 4 above. When the user refreshes their workpage, they will see the updated version.

