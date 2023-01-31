<!-- loio2af7015bc37346f9973d88256385f01f -->

# Interaction Between Cards

Cards on the same page can interact with each other by setting and getting parameters to and from the page context.

All the parameters in the page context will be made available to a card when it is initialized. A card can then respond to any parameters it recognizes. Whenever a card updates a parameter to the page context, this will trigger a refresh for all the other cards on the same page, so that they will all get the updated context parameter.

After configuring the site context, users can select one of the available card parameters, and all the other cards on the page that are designed to respond to the page context, will respond and update accordingly. For more information about the user flow, see [**Interaction Between UI Integration Cards**](https://help.sap.com/docs/WZ/fec5ca6e3229418f84a932c745cbe985/e3dd5cc172034d4eb5f7812ce7bb5c5e.html)

**Related Information**  


[Add or Update Context](add-or-update-context-e69aef3.md "Card actions provide a mechanism to make elements interactive. Card actions are either attached by the card developer to the desired element (card header, content, list item, etc.), or built into the element. Upon user interaction, a corresponding event is dispatched for handling. If there is a predefined behavior for the action (for example, for Navigation) it will be executed. To add or update a context, you need to use a customized SAP UI5 Card action named updateContext.")

[Context Values](context-values-571b7d3.md)

