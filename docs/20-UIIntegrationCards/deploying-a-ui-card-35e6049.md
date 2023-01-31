<!-- loio35e6049aff8b4495903ee16303508a76 -->

# Deploying a UI Card

Deploy a UI integration card using SAP Business Application Studio.



<a name="loio35e6049aff8b4495903ee16303508a76__prereq_asx_vwy_wkb"/>

## Prerequisites

You’ve created a UI card.

> ### Note:  
> To deploy a UI integration card, SAP Business Application Studio and the target must exist in the same subaccount and a token-exchange destination must be configured. If there's no destination, the user needs to manually upload the ZIP file to the target.



<a name="loio35e6049aff8b4495903ee16303508a76__context_cgn_5f5_xkb"/>

## Context



<a name="loio35e6049aff8b4495903ee16303508a76__steps_dgn_5f5_xkb"/>

## Procedure

1.  Launch SAP Business Application Studio and navigate to the dev space where you created the UI card.

2.  Navigate to the card project that contains the required UI card. Right-click on *manifest.json* file in the selected card project and choose *UI Integration Card: Deploy to SAP Build Work Zone, advanced edition*.

    Alternative way to deploy: Right-click on the *manifest.json* file in the selected card project and choose *UI Integration Card: Package*. The UI card is packaged in a `<card id>.zip` file. Then, right-click the `<card id>.zip` file and select *Download* to download the file. The UI card is available in the downloaded file. You can use this zip file to upload the UI card to SAP Work Zone.

    > ### Note:  
    > -   On the first deployment of the sample card, it’s recommended to clear the destination. To do so, navigate to *File* \> *Settings* \> *Open Preference* \> *UIcarddk*. In the *UIcarddk* section, remove the value available for *Content Destination*.
    > 
    > -   For successive deployments of the sample card, it isn’t required to clear the content destination.


**Related Information**  


[Creating a UI Card](creating-a-ui-card-3fd1bdf.md "Create a UI card using SAP Business Application Studio.")

[Updating a UI Card](updating-a-ui-card-c27069e.md "Update a UI card using SAP Business Application Studio.")

