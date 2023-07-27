<!-- loio30b63a53d2ef41cf960ccc116128f499 -->

# Hiding Widgets and Cards

On a workpage, it’s possible to hide widgets or cards that are not relevant to a user for a number of reasons.



<a name="loio30b63a53d2ef41cf960ccc116128f499__section_r2j_5lc_5xb"/>

## Hiding widgets

To make a workpage less cluttered and only see what’s relevant for the user, it’s possible to hide the following empty widgets:

-   External content widgets

-   Content widgets

-   Knowledge-base widgets

-   Event widgets

-   Forum widgets


In some cases, a widget will still be displayed, even when selecting the option to hide the empty widgets. The expected behavior is as follows:

-   If a private/external workspace is selected as a source and the user has no access - the widget is hidden.
-   If a private workspace is selected as a source, the user has no access, and the option to request access is enabled - the empty widget will be displayed with an option to request access.
-   Widgets that are empty but have an action button on them to create/upload content - the widget will be displayed.

To show these widgets again, you can select the *Show empty widgets* toggle that appears when the workpage is in edit mode.



<a name="loio30b63a53d2ef41cf960ccc116128f499__section_awv_xlc_5xb"/>

## Hiding cards

On a workpage, administrators can dynamically hide cards if:

-   The card doesn’t have any content

-   The user can’t access the card

-   The card hasn’t been enabled
-   If any rules have been set for the card \(for example, location-based\).


If any of the above criteria are removed, the card is displayed again.

To show cards again despite being empty, administrators can select the *Show empty widgets* toggle that appears when the workpage is in edit mode.

For more information about empty cards, see SAPUI5 documentation [Component UI Integration Cards with no data](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/component/noDataMessage).

