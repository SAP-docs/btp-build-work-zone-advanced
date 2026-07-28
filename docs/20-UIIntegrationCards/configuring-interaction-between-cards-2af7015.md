<!-- loio2af7015bc37346f9973d88256385f01f -->

# Configuring Interaction Between Cards

Cards on the same workpage can interact with each other via the page context.

When developing cards, you can add parameters to the cards that write and read to the page context. At runtime, if the workpage contains several cards that are configured to respond to the page context, a user can select a context value in one card and this will update the other cards according to the selected value.

To learn more about how to configure card integration via a page context, refer to the following Developer Guide in Github. The guide contains an example of three cards that interact with each other:

-   **Brand card** - Lists all available brands in a dropdown list. Once a brand is selected, it is added to the current card context as the brand parameter.
-   **Region card** - Lists all available regions in a dropdown list. Once a region is selected, it is added to the current card context as the region parameter.
-   **Analytical card** - A card that subscribes to the brand and region card context parameters. The analytical chart automatically refreshes when the brand or region parameter is updated.

For more information, see:

-   [Interaction Between Cards in the SAP Build Work Zone](https://github.com/SAP-samples/build-workzone-integration/tree/main/advanced/context-awareness)
-   [Build-In Card Context](https://github.com/SAP-samples/build-workzone-integration/tree/main/advanced/built-in-card-context)
-   [Sample cards](https://github.com/SAP-samples/build-workzone-integration/tree/main/advanced/context-awareness/sample-cards/bundles):

