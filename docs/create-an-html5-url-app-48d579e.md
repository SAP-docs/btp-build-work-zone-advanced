<!-- loio48d579ee59c54b8bbade062f5451c429 -->

# Create an HTML5 URL App

Developers can create a simple URL app that opens a website and deploy it on the HTML5 app repository.



You can create a simple URL app and deploy it to the HTML5 repository, from which the administrator can add this app from the HTML5 content provider to the subaccount.

Most of the steps described in the [Basic Development Flow](basic-development-flow-ea482cc.md) are not required when developing a simple URL app. Therefore, follow the below procedure instead.



<a name="loio48d579ee59c54b8bbade062f5451c429__section_iwn_jtp_qpb"/>

## Procedure

1.  Set up your environment. For more information, see [Set Up Your Development Environment](set-up-your-development-environment-3db887a.md)
2.  Develop a simple HTML5 app. A code sample for the app is provided below.
3.  In the `sap.flp` section of the `manifest.json` file, add the information relevant to the URL app:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    type
    
    </td>
    <td valign="top">
    
    URL
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    url
    
    </td>
    <td valign="top">
    
    Specify the URL address that points to the app.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    navmode
    
    </td>
    <td valign="top">
    
    Specify the navigation mode: inplace - in the same window, or explace - in a new window. When not specified, the default value is explace.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    parameters
    
    </td>
    <td valign="top">
    
    Optional: specify any URL params, if required, as shown in the example below.
    
    </td>
    </tr>
    </table>
    
    ```
    {
        "_version": "1.32.0",
        "sap.cloud": {
            "public": true,
            "service": "com.sap.sample.subaccount.app"
        },
        "sap.app": {
            "id": "html5.urlLauncherTile",
            "type": "application",
            "applicationVersion": {
                "version": "1.0.0"
            },
            "title": "Minimal URL Tile",
            "description": "URL App on HTML5",
            "info": "Minimal URL Tile",
            "ach": "EP-CPP-CF-LP-DEV",
            "crossNavigation": {
                "inbounds": {
                    "external": {
                        "semanticObject": "ExternalUrl",
                        "action": "dc4dcef0595e4d04",
                        "icon": "sap-icon://BusinessSuiteInAppSymbols/icon-line-bar-chart",
                        "title": "Minimal URL Tile",
                        "subTitle": "URL App on HTML5"
                    }
                }
            }
        },
        "sap.flp": {
            "type": "application",
            "config": {
                "target": {
                    "type": "URL",
                    "url": "https://www.android.com/tv/",
     
                    "navmode": "inplace",
                    "parameters": {
                        "val1": "param1"
                    }
                }
            }
        },
        "sap.ui": {
            "technology": "URL",
            "deviceTypes": {
                "desktop": true,
                "tablet": true,
                "phone": true
            }
        }
    }
    ```

4.  Build and deploy the app. For more information, see [Build and Deploy Content](build-and-deploy-content-4394315.md)

