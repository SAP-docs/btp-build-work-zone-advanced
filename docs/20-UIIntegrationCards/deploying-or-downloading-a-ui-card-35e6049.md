<!-- loio35e6049aff8b4495903ee16303508a76 -->

# Deploying or Downloading a UI Card

Directly deploy a UI integration card from SAP Business Application Studio to the subaccount or download it as a ZIP file.



<a name="loio35e6049aff8b4495903ee16303508a76__context_cgn_5f5_xkb"/>

## Context

The card that you've created can be added to your subaccount as an app with a card visualization. If you have a subscription to SAP Business Application Studio in the same subaccount as your subscription to SAP Build Work Zone, advanced edition, and you have a token-exchange destination configured on it, you can directly deploy the app to the subaccount. Otherwise, you can download the card as a ZIP file, and then upload it as an app visualization in the Content Manager.



<a name="loio35e6049aff8b4495903ee16303508a76__steps_dgn_5f5_xkb"/>

## Procedure

1.  **Option 1: Direct Deployment:** In SAP Business Application Studio, right-click the *manifest.json* file in the selected card project and choose *UI Integration Card: Deploy to SAP Build Work Zone*.

    Refresh the card editor in the in the Admin Console, *UI Integration* \> *Cards*. The card is added to the list of cards and you can activate it.

    In the Content Manager, you can find a new local app with this card visualization.

    > ### Note:  
    > -   On the first deployment of the sample card, it’s recommended to clear the destination. To do so, navigate to *File* \> *Settings* \> *Open Preference* \> *UIcarddk*. In the *UIcarddk* section, remove the value available for *Content Destination*.
    > 
    > -   For successive deployments of the sample card, it isn’t required to clear the content destination.

2.  **Option 2: Downloading a Zip File:** In SAP Business Application Studio, right-click the *manifest.json* file in the selected card project and choose *UI Integration Card: Package*.

    The UI card is packaged in a `<card id>.zip` file. Right-click the `<card id>.zip` file and select *Download* to download the file.

    In the Content Manager, create a new local app and upload the card ZIP file as the app visualization. For more information, see [Configuring Apps with a Card Visualization](../configuring-apps-with-a-card-visualization-25b3d37.md), [Integrating Cards into a Site](../integrating-cards-into-a-site-b65c218.md).


