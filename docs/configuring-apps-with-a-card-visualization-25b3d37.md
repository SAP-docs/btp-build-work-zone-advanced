<!-- loio25b3d374e76d4e1b8daf66cfada4269d -->

# Configuring Apps with a Card Visualization

Create local apps in the Content Manager, and configure them with a card visualization.



## Introduction

Both tiles and cards are visualization of apps. Apps have different visualization options such as tiles, cards or none in the case of shell plugins. Unlike tiles which are basic app launchers, cards can display business content and eliminate the need to launch the app. All cards can be consumed on mobile or desktop devices.

You can create a new app or use an existing app in the Content Manager, and select it to display as a card.



<a name="loio25b3d374e76d4e1b8daf66cfada4269d__section_nck_bkx_bbc"/>

## How to configure the app with a card visualization?

To upload a card, you need to create a local app with a card visualization in the Content Manager as follows:

1.  Open the Content Manager from the Administration Console by navigating to *External Integrations* \> *Business Content* \> ** and click *Content Manager*.

2.  In the Content Manager, select *Create* \> *App*.

    > ### Note:  
    > You can also take an existing business app and change the visualization to a card.

3.  Go to the *Visualization* tab.

4.  From the *Visualization Type* dropdown, select *UI Integration Card*.

5.  Click *Upload Card* and select the card you want to upload.

    > ### Note:  
    > When you upload the card, the card details are automatically added to the fields on the screen.
    > 
    > If you add a lower version of the card, you'll get a warning but you can still upload the card.

6.  *Save*.

7.  Assign the app to a role.

    > ### Note:  
    > Access to cards depends on the user's role. Therefore if all members of a workspace need to see the card, it should be assigned to the *Everyone* role.
    > 
    > You can also assign the card to a different role. For more information, see [Assign Content to a Role](assign-content-to-a-role-baeaf6e.md)
    > 
    > If you do this, then you should also assign the role to the site in the*Site Settings* screen.


> ### Note:  
> Assigning an app with a card visualization to groups and catalogs is not supported. The card will not be displayed in the Applications page.

Once uploaded, the card appears in the *Cards* screen in the Administration Console under the *Uploaded Cards* section.

For more information about the end-to-end flow for integrating cards into a site, see [Integrating Cards into a Site](integrating-cards-into-a-site-b65c218.md).

For more information about configuring apps in the Conent Manager, see [Configure Apps](configure-apps-4ba745b.md).

