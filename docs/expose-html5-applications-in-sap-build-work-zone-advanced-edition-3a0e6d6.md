<!-- loio3a0e6d6b791c4c2189f6a0a424188362 -->

# Expose HTML5 Applications in SAP Build Work Zone, advanced edition

To expose an HTML5 Application in SAP Build Work Zone, advanced edition , you need to add some information to the `manifest.json` file of the application.



## Deployment Restrictions

-   The HTML5 applications must be deployed to the same subaccount as the SAP Build Work Zone, advanced edition.
-   After subscribing to SAP Build Work Zone, advanced edition, an *HTML5 Apps* content provider is created in the *Channel Manager* screen. To keep the content up-to-date, you need to update this content provider after deploying or updating an HTML5 application. For more information, see [HTML5 Apps Content Provider](https://help.sap.com/docs/WZ_STD/8c8e1958338140699bd4811b37b82ece/ad2103e2fde342878bcf41a8ae8a0bd8.html).

> ### Note:  
> -   The value of `sap.app/id` of each application must be unique across all spaces in the subaccount.
> -   The value of `sap.cloud/service` of each application must be unique across all HTML5 repository instances, MTA files, and destinations.



<a name="loio3a0e6d6b791c4c2189f6a0a424188362__section_pfdb_lng_vch_3nb"/>

## Configure the manifest.json File



### Overview

The application attributes are stored in the `manifest.json` file.

For SAP Build Work Zone, advanced edition, these include the following configurations:


<table>
<tr>
<th valign="top">

Configuration

</th>
<th valign="top">

Mandatory?

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`sap.cloud.service`

</td>
<td valign="top">

Mandatory

</td>
<td valign="top">

Defines the business service.

</td>
</tr>
<tr>
<td valign="top">

`semanticObject` and `action`

</td>
<td valign="top">

Mandatory

</td>
<td valign="top">

Defines the navigation intent, which is composed of a semantic object and the action that is performed on this object.

</td>
</tr>
<tr>
<td valign="top">

`title, subTitle, info, icon`

</td>
<td valign="top">

Optional

</td>
<td valign="top">

Defines the visualization properties of the tile in the site.

</td>
</tr>
<tr>
<td valign="top">

`dataSources`

</td>
<td valign="top">

Optional

</td>
<td valign="top">

Within a specific `dataSource`, the value of the `uri` key defines the location of the OData from which to obtain the dynamic information.

</td>
</tr>
</table>

The following sections provide examples for each configuration.

> ### Note:  
> The `minUI5Version` parameter, within `sap.ui5`, under `dependencies`, defines the minimum SAPUI5 version.
> 
> The value must be an explicit version number, such as `"1.60.1"`.
> 
> Do not use a value such as the following: `"${sap.ui5.dist.version}"`



### Business Service \(Mandatory\)

The following example shows how to define the business service.

The value of the `service` key must be unique per subaccount.

```
"sap.cloud": {
        "service": "com.sap.sample.app"
    },
```



### Navigation Intent \(Mandatory\)

The following example shows how to define the navigation intent, which is used when navigating to the application. An intent is composed of a semantic object and the action that is performed on this object. In this example: `Dynamic-display`:

```
"sap.app": {
        ...
        "crossNavigation": {
            "inbounds": {
                "intent1": {
                    "signature": {
                        "parameters": {},
                        "additionalParameters": "allowed"
                    },
                    "semanticObject": "Dynamic",
                    "action": "display",
                    ...
                    }
                }
            }
        },
```



### Stable UI5 Version \(Optional\)

By default, when running applications from the HTML5 content provider, the applications use the latest official UI5 version.

To control the UI5 version the application use, you can add the following section and define a stable version for `ui5VersionNumber`.

```
"sap.platform.cf": {
	   "ui5VersionNumber": "1.136.2"
    },
"sap.ui5": {
        ...
        },
```

> ### Tip:  
> For best performance, it is highly recommended to use one stable UI5 version for all apps in a single site.

> ### Tip:  
> Using the x-range format for the patch level, you can get automatic patch updates for the UI5 version of your application. The UI5 version consists of \[major, minor, patch\]. You can replace the patch numeric value \(2 in the above example\) with an X, x, or \*. For example, use `"ui5VersionNumber": "1.136.x"` to get automatic updates of all patches of version 1.136.

> ### Note:  
> For more information about the removal of outdated SAPUI5 versions from the CDN, refer to [3001696](https://me.sap.com/notes/3001696)
> 
> To read the original blog post, see [Removing outdated UI5 versions from the UI5 CDN](https://help.sap.com/docs/link-disclaimer?site=https%3A%2F%2Fblogs.sap.com%2F2021%2F01%2F26%2Fremoving-outdated-ui5-versions-from-ui5-cdn%2F).



### Tile Visualization \(Optional\)

The following example shows how to define the visualization properties of the tile, which include the title, the subtitle, the info that appears at the bottom of the tile, and the icon.

```
"sap.app": {
        ...
        ...
        },
        "crossNavigation": {
            "inbounds": {
                "intent1": {
                    "signature": {
                        "parameters": {},
                        "additionalParameters": "allowed"
                    },
                    "semanticObject": "Dynamic",
                    "action": "display",
                    "title": "{{appTitle}}",
                    "info": "{{appTitle}}",
                    "subTitle": "{{appSubTitle}}",
                    "icon": "sap-icon://account"
                    ...
                    }
                }
            }
        },
```



### Dynamic Tile \(Optional\)

The following example shows how to define a dedicated `dataSource` with the value of the `uri` key that defines the location of the OData from which to obtain the dynamic information to display on the dynamic tile.

The value of the `uri` key, in this example `comsapsampleapp.html5dynamic/items`, is composed of the following information:

-   The value of the `sap.cloud/service` key, without the dots. In this example: `comsapsampleapp`

-   A dot \(.\)

-   The value of the `sap.app/id` key, without the dots. In this example: `html5dynamic`

-   A forward slash \(/\)

-   The value of the `route` in the `xs-app.json` file that defines the destination from which to bring the data. In this example: `items`


> ### Note:  
> To use a `dataSource` from within the application, you need to define a different data source, only with the value of the `route` in the `xs-app.json` file. In this example: `"uri": "items"`

```
{
    "_version": "1.9.0",
    "sap.cloud": {
        "public": true,
        "service": "com.sap.sample.app"
    },
    "sap.app": {
        "id": "html5.dynamic",
        "type": "application",
        "i18n": "i18n/i18n.properties",
        "applicationVersion": {
            "version": "1.0.0"
        },
        "title": "{{appTitle}}",
        "description": "{{appDescription}}",
        "info": "{{appTitle}}",
        "resources": "resources.json",
        "ach": "ach",
        "sourceTemplate": {
            "id": "html5moduletemplates.basicSAPUI5ApplicationProjectModule",
            "version": "1.40.12"
        },
        "crossNavigation": {
            "inbounds": {
                "intent1": {
                    "signature": {
                        "parameters": {},
                        "additionalParameters": "allowed"
                    },
                    "semanticObject": "Dynamic",
                    "action": "display",
                    "title": "{{appTitle}}",
                    "indicatorDataSource": {
                        "dataSource": "dynamicTileIndicatorDataSource",
                        "path": "count",
                        "refresh": 1000
                    }
                }
            }
        },
        "dataSources": {
            "dynamicTileIndicatorDataSource": {
                "uri": "items",
                "type": "JSON"
            }
        }
    },
...
}
```

> ### Note:  
> For more information about `dataSources`, see the section about **sap.app** in [Descriptor for Applications, Components, and Libraries](https://help.sap.com/viewer/468a97775123488ab3345a0c48cadd8f/201909.002/en-US/be0cf40f61184b358b5faedaec98b2da.html).



### Translation \(Mandatory\)

Add translation files in the i18n folder for every locale that is used at runtime.

Make sure the locales are written according to the supported format. For more information, see [Supported Locales and Fallback](https://sapui5.hana.ondemand.com/#/topic/ec753bc539d748f689e3ac814e129563).

It is highly recommended to check the console logs and provide the missing translation files to avoid the SAPUI5 fallback logic.

**Related Information**  


[Add a Shell Plugin](add-a-shell-plugin-1becea7.md "You can add shell plugins to SAP Build Work Zone, advanced edition.")

[Implement a Custom Visualization](implement-a-custom-visualization-376785f.md "You can implement a custom visualization (tile) for an app.")

