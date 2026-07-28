<!-- loioa765b4c0fe4b4eaea6e8356af51b72b1 -->

# Cards in Business Solutions

The following flow explains how to deploy SAPUI5 Integration Cards inside business solutions to SAP Build Work Zone.



## Overview

When an app with the type `card` is deployed to the HTML5 repository, the CDM HTML5 repo library automatically detects it and creates a federated CDM app \(business app\). This enables SAP Build Work Zone to discover and consume the card content through the CDM exposure endpoint.

The CDM HTML5 library performs the following steps:

1.  Copies the card manifest to the `vizConfig` in the CDM app.
2.  Sets the `vizResources` at path `app->payload->visualizations->[vizId]->vizResources` to point to the deployed card in the HTML5 repository \(with FDC cache buster\), enabling the runtime to load the card.

For more information about how cards are loaded, see [Use Integration Cards In Apps](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/integrate/usage).



## Card App Structure

When deployed, the card app follows this structure:

```
{
  "_version": "3.0",
  "identification": {
    "id": "APP_ID",
    "entityType": "businessapp",
    "title": "{{title}}"
  },
  "payload": {
    "visualizations": {
      "default": {
        "vizType": "sap.card",
        "vizConfig": {
          // ...
        },
        "vizResources": {
          // The baseURL points to the deployed card in the HTML5 repository, with the FDC cache buster token
          "baseURL": "",
          "destination": "default"
        }
      }
    }
  },
  "texts": [
    ...
  ]
}
```

-   `vizConfig` contains the complete card manifest content.
-   `texts` contains i18n translations from FDC i18n files \(processed like any other HTML5 apps\).
-   `baseURL` is a relative URL with an FDC cache buster token pointing to the application in the HTML5 repository.



## Using Cards in Runtime

Cards can be referenced like any other CDM app by using the app ID and visualization ID \(named `default`\).

**Example: Referencing the app in a workpage:**

```
{
  "_version": "3.2.0",
  "identification": {
    "id": "PAGE_CARDS",
    "entityType": "workpage",
    "title": "{{title}}",
    "description": "{{description}}"
  },
  "payload": {
    "workpageConfig": {
      "title": "{{title}}"
    },
    "rows": [
      {
        "id": "row-1",
        "rowConfig": {
          "title": "{{rowDeclaritiveCard}}"
        },
        "columns": [
          {
            "id": "col-1",
            "columnConfig": {
            },
            "cells": [
              {
                "id": "cell-1",
                "cellConfig": {},
                "widgets": [
                  {
                    "id": "widg-1",
                    "viz": {
                      "appId": "sample.component.card",
                      "vizId": "default"
                    }
                  }
                ]
              }
            ]
          }
        ]
      }
    ]
  },
  "texts": [
    {
      "locale": "",
      "textDictionary": {
        "title": "WorkPage with Card",
        "description": "WorkPage with Card",
        "rowDeclaritiveCard": "Card without additional resources",
        "rowCardResources": "Declaritive Card with resources (images)",
        "rowComponentCard": "Component Card"
      }
    }
  ]
}
```

**Related Information**  


[Card Types](card-types-64fdbb8.md "Information about how component cards and declarative cards are defined in the manifest.")

