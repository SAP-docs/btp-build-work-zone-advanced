<!-- loio64fdbb82c2784e3fb05b472694e4b031 -->

# Card Types

Information about how component cards and declarative cards are defined in the manifest.



## Overview

SAPUI5 Integration Cards come in two main types:

-   **Component Cards:** full UI5 applications with resources \(views, controllers, models, etc.\). They provide maximum flexibility and can include custom UI5 components and complex interactions.
-   **Declarative Cards:** define only the data and display configuration through a manifest, without requiring UI5 resources \(though they can optionally include resources\). Data can be loaded via destinations or relative URLs. These are simpler and faster to develop for standard card use cases.

In the HTML5 repository, the deployment logic is the same for both card types. The only difference is how the card is defined in the manifest.

For more information, see [Integration Card Types](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/overview/cardTypes).



## Card Types



### Component Card


<table>
<tr>
<th valign="top">

Topic

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

Type

</td>
<td valign="top">

Full UI5 card with resources \(views, controllers, etc.\).

</td>
</tr>
<tr>
<td valign="top">

Deployment

</td>
<td valign="top">

Resources are deployed as an HTML5 app to the HTML5 repository.

</td>
</tr>
<tr>
<td valign="top">

Rendering

</td>
<td valign="top">

The card is rendered from the HTML5 apps repository via CDM \(`cdm -> viz -> vizResources`\).

</td>
</tr>
<tr>
<td valign="top">

Data

</td>
<td valign="top">

This example does not include data loading \(static card content only\).

</td>
</tr>
<tr>
<td valign="top">

Note

</td>
<td valign="top">

Does not require mapping destinations or defining separate destination configurations.

</td>
</tr>
</table>



### Component Card with Data Destination


<table>
<tr>
<th valign="top">

Topic

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

Based on

</td>
<td valign="top">

[SAPUI5 sample app](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/explore/destinations/component).

</td>
</tr>
<tr>
<td valign="top">

Data Loading

</td>
<td valign="top">

The card uses a data destination to load data.

</td>
</tr>
<tr>
<td valign="top">

Resolution

</td>
<td valign="top">

The destination is resolved via the Work Zone host using the UI5 function: `oCard.resolveDestination("myDestination")`.

</td>
</tr>
<tr>
<td valign="top">

Important Limitations

</td>
<td valign="top">

-   Integrated HTML5 business solutions: This card type is not intended for use in this scenario. Even if the destination exists, the runtime destination is returned when no destination mapping is configured in runtime.



</td>
</tr>
<tr>
<td valign="top">

More Information

</td>
<td valign="top">

[Destinations](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/configuration/destinations).

</td>
</tr>
</table>



### Declarative Card with Local Data


<table>
<tr>
<th valign="top">

Topic

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

Type

</td>
<td valign="top">

Pure declarative card with resources.

</td>
</tr>
<tr>
<td valign="top">

Deployment

</td>
<td valign="top">

Card resources \(manifest and data file\) are deployed as an HTML5 app.

</td>
</tr>
<tr>
<td valign="top">

Data Source

</td>
<td valign="top">

Uses a local `data.json` file bundled with the card.

</td>
</tr>
<tr>
<td valign="top">

Data Loading

</td>
<td valign="top">

Data is loaded via a relative app/card path: `./data.json`

</td>
</tr>
<tr>
<td valign="top">

Best Practice

</td>
<td valign="top">

This is the simplest approach for static or predefined data sets.

</td>
</tr>
<tr>
<td valign="top">

Use Case

</td>
<td valign="top">

Ideal for cards with static content, configuration-driven data, or demo/testing scenarios.

</td>
</tr>
</table>

**How the data is loaded:** In the card manifest, under `sap.card`, define a relative path to the local data file:

```
{
  "sap.card": {
    "type": "List",
    "content": {
      "data": {
        "request": {
          "url": "./data.json"
        }
      },
      "item": {
        "title": "{Name}",
        "description": "{Description}",
        "highlight": "{Highlight}"
      }
    }
  }
}
```

The `data.json` file is packaged with the card and deployed to the HTML5 repository.



### Declarative Card with Data Destination


<table>
<tr>
<th valign="top">

Topic

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

Resources

</td>
<td valign="top">

No resources defined \(declarative card\).

</td>
</tr>
<tr>
<td valign="top">

Declaration

</td>
<td valign="top">

The card is fully declared in the CDM JSON with a data destination configuration.

</td>
</tr>
<tr>
<td valign="top">

Deployment Limitations

</td>
<td valign="top">

-   Integrated HTML5 business solutions: Destination mapping is not available. The card automatically falls back to the runtime \(RT\) destination.



</td>
</tr>
<tr>
<td valign="top">

Recommendation

</td>
<td valign="top">

This pattern is not recommended for HTML5 apps. Users should reference data from within the HTML5 repository rather than from external destinations to avoid destination mapping complexity.

</td>
</tr>
<tr>
<td valign="top">

Fallback Behavior

</td>
<td valign="top">

When the destination is not mapped, the system falls back to the runtime \(RT\) destination.

</td>
</tr>
<tr>
<td valign="top">

General Comment

</td>
<td valign="top">

This functionality is not new and works the same way with external content providers and content packages.

</td>
</tr>
</table>

**How the data is loaded:** In the card definition under `sap.card`, define the destination configuration:

```
{
  "sap.card": {
    "type": "List",
    "configuration": {
      "destinations": {
        "myDestination": {
          "name": "northwindV3"
        }
      }
    }
  }
}
```

**Complete CDM Definition Example:**

```
{
  "_version": "3.2.0",
  "identification": {
    "id": "uli.dest.card.app",
    "title": "Title for Card with NorthwindV2 Destination",
    "entityType": "businessapp",
    "description": "Description for Card with NorthwindV2 Destination"
  },
  "payload": {
    "visualizations": {
      "uli.dest.card.viz": {
        "vizType": "sap.card",
        "vizConfig": {
          "_version": "1.14.0",
          "sap.app": {
            "id": "groot.card_with_dest",
            "type": "card",
            "title": "Products by Category",
            "subTitle": "List card with destination",
            "applicationVersion": {
              "version": "1.0.0"
            }
          },
          "sap.ui": {
            "technology": "UI5",
            "deviceTypes": {"desktop": true, "phone": true, "tablet": true},
            "icons": {
              "icon": "sap-icon://list"
            }
          },
          "sap.card": {
            "type": "List",
            "configuration": {
              "destinations": {
                "ES5": {
                  "name": "ES5",
                  "defaultUrl": "/sap/opu/odata/sap/EPM_REF_APPS_SHOP_SRV/"
                },
                "NorthwindV2": {
                  "name": "NorthwindV2",
                  "defaultUrl": "/Products"
                }
              }
            },
            "data": {
              "request": {
                "url": "{{destinations.NorthwindV2}}/Products",
                "withCredentials": true
              },
              "path": "/d/results"
            },
            "designtime": "dt/configuration",
            "header": {
              "title": "Title for Card with NorthwindV2 Destination",
              "subTitle": "Original Card",
              "icon": {
                "src": "sap-icon://desktop-mobile"
              },
              "status": {
                "text": "5 of 20"
              }
            },
            "content": {
              "item": {
                "title": "{ProductName}",
                "description": "{UnitPrice}",
                "icon": {
                  "src": "{ImageUrl}"
                },
                "info": {
                  "value": "{UnitsInStock}",
                  "state": "{= ${UnitsInStock} > 3.5 ? 'Success' : 'Warning' }"
                }
              },
              "maxItems": 5
            }
          },
          "sap.platform.mobilecards": {
            "compatible": false
          }
        },
        "vizResources": {
          "artifactId": "uli.dest.card.app"
        }
      }
    }
  }
}
```



### Declarative Card with Relative URL


<table>
<tr>
<th valign="top">

Topic

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

Resources

</td>
<td valign="top">

No resources defined \(declarative card\).

</td>
</tr>
<tr>
<td valign="top">

Destination

</td>
<td valign="top">

No destination configuration in CDM

</td>
</tr>
<tr>
<td valign="top">

Data Loading

</td>
<td valign="top">

Uses a relative URL to load data, which resolves differently based on the deployment type:

-   Integrated HTML5 business solutions: The relative URL resolves to the runtime \(RT\) destination configured in the provider.



</td>
</tr>
<tr>
<td valign="top">

More Information

</td>
<td valign="top">

[Data Handling](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/data).

</td>
</tr>
</table>

**How the data is loaded:** In the card manifest under `sap.card`, define a relative URL:

```
{
  "sap.card": {
    "data": {
      "request": {
        "url": "northwind/Products",
        "withCredentials": true
      },
      "path": "/d/results"
    }
  }
}
```



### Declarative Card with Non-Existing Destination


<table>
<tr>
<th valign="top">

Topic

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

Resources

</td>
<td valign="top">

No UI5 resources defined \(pure declarative card\).

</td>
</tr>
<tr>
<td valign="top">

Scenario

</td>
<td valign="top">

The specified data destination does not exist in the subaccount.

</td>
</tr>
<tr>
<td valign="top">

Fallback Behavior

</td>
<td valign="top">

The system automatically falls back to the runtime \(RT\) destination

</td>
</tr>
<tr>
<td valign="top">

Use Case:

</td>
<td valign="top">

Demonstrates system resilience when destination configuration is missing or incorrect.

</td>
</tr>
</table>

**Related Information**  


[Use Integration Cards In Apps](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/integrate/usage)

[Integration Card Types](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/overview/cardTypes)

[Destinations](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/configuration/destinations)

[Data Handling](https://ui5.sap.com/test-resources/sap/ui/integration/demokit/cardExplorer/webapp/index.html#/learn/features/data)

