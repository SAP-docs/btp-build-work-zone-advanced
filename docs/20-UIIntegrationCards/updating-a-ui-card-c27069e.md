<!-- loioc27069ecedf54a52a907acea029a5168 -->

# Updating a UI Card

Update a UI card using SAP Business Application Studio.



<a name="loioc27069ecedf54a52a907acea029a5168__prereq_asx_vwy_wkb"/>

## Prerequisites

You’ve created a UI card.



<a name="loioc27069ecedf54a52a907acea029a5168__context_cgn_5f5_xkb"/>

## Context



<a name="loioc27069ecedf54a52a907acea029a5168__steps_dgn_5f5_xkb"/>

## Procedure

1.  Launch SAP Business Application Studio and navigate to the dev space where you created the UI card.

2.  Navigate to the card project that contains the required UI card. Right-click on the `manifest.json` file in the selected card project and choose *UI Integration Card: Edit*.

    > ### Note:  
    > Currently, the property editor is only supported for List, Table, and Object card types. For all other card types, use the code editor.

3.  In the editor, update the required fields.

    To preview the changes, right-click on the `manifest.json` file and choose *UI Integration Card: Preview*. You can also select the preview button in the editor to view the changes.

    The UI Card editor provides an option to select the SAP UI5 version for card development. On selecting the SAP UI5 version, the property editor and the card preview supports features of the selected version accordingly. To select the SAP UI5 version, navigate to *File* \> *Settings* \> *Open Preferences* \> *UIcarddk* \> *ui5Version* and select the required version.

    The `autoPreviewOn ManifestChanged` and `autoPreviewOn ManifestSaved` attributes allow you to view the changes and save them automatically. To enable these attributes, set them to true by navigating to *File* \> *Settings* \> *Open Preferences* \> *UIcarddk*.


**Related Information**  


[Creating a UI Card](creating-a-ui-card-3fd1bdf.md "Create a UI card using SAP Business Application Studio.")

[Deploying a UI Card](deploying-a-ui-card-35e6049.md "Deploy a UI integration card using SAP Business Application Studio.")

