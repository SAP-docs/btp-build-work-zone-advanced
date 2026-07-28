<!-- loio1becea708c86455f9174f8cb9c094251 -->

# Add a Shell Plugin

You can add shell plugins to SAP Build Work Zone, advanced edition.



<a name="loio1becea708c86455f9174f8cb9c094251__section_pyy_1rq_rfb"/>

## What is a shell plugin?

A shell plugin is a type of an HTML5 application that changes the site shell. It is used to extend the site functionality or UI.

Plugins are automatically loaded and initialized by the runtime when the site is started.

To use a shell plugin in SAP Build Work Zone, advanced edition, first add the plugin code to the MTA as an HTML5 module, and then perform additional configuration in the `manifest.json` file.



<a name="loio1becea708c86455f9174f8cb9c094251__section_mzv_32r_zyb"/>

## Prerequisite

You have a project in SAP Business Application Studio.

> ### Note:  
> If you are not using SAP Business Application Studio, you need to perform the corresponding steps in your IDE. For information about the project structure, see [Set Up Your Development Environment](set-up-your-development-environment-3db887a.md).



<a name="loio1becea708c86455f9174f8cb9c094251__section_zl1_5vv_qfb"/>

## Procedure

A shell plugin is a type of an HTML5 app. For information about the basic development flow, see [Basic Development Flow](basic-development-flow-ea482cc.md).

To configure a shell plugin, complete the following steps:

1.  In your project, from the context menu of the `mta.yaml` file, create an MTA module using the *SAP Fiori application* module template.

    Complete the wizard to generate a module that includes the following files: `Component.js` and a `manifest.json` file that contains the app.

2.  Add the shell plugin code to the `Component.js` file of the HTML5 app.
3.  In the app's `manifest.json` file, add `"type": "plugin"` and under the `inbounds` section make sure `"hideLauncher": true`. For example:

    ```
    "myplugin":{
               "sap.app":{
                   "id": "sap.my.plugin",
                   "type": "component",
                   "applicationVersion": {
                       "version": "1.0.0"
                   },
                   "title": "Welcome plugin",
                   "crossNavigation": {
       			"inbounds": {
    				"Shell-plugin": {
    					"signature": {
    						"parameters": {},
    						"additionalParameters": "allowed"
    					},
    					"hideLauncher": true,
    					"semanticObject": "Shell",
    					"action": "plugin"
    				}
    			   }
    		     }
                …
               }
    
               ...
               "sap.flp": {
                  "type": "plugin"
               },
                  ...
             },
    
    ```


