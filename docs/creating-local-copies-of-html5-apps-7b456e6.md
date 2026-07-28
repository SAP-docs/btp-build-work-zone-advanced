<!-- loio7b456e64c9374f7d9756bbec3ff40ced -->

# Creating Local Copies of HTML5 Apps

You can create a local copy of an HTML5 app that was added from the HTML5 Apps content provider.



**Overview**

When you create a local copy of an HTML5 app that was added from the HTML5 Apps content provider, you can configure its properties, including the navigation intent and parameters and the visualization properties and parameters. To do this, use the *Create a Local Copy* button in the App editor of the app.



**What you should know about creating local copies of an app**

-   When importing local copy, for which the content provider doesn't exist in the target landscape, the warning message to the administrator about a missing content provider won't appear.

-   When importing a local copy from a source landscape to a target landscape, any system that is referenced by the app in the source landscape must also be configured in the target landscape. For example, for an app with a dynamic tile visualization, the system defined for dynamic data \(in the *Visualization* tab\) must also exist on the target landscape.

-   After creating the local copy, configuration changes to the app descriptor of the HTML5 app, such as changing the tile title, won't be reflected in the local copy. However, changes to the app resources, such as changes to a JavaScript file, will continue to be reflected.

-   When the HTML5 app is removed from the subaccount, the local copy will still be visible in the Content Manager and available in runtime, however the local copy won't work.

-   Creating local copies of HTML5 apps that were built with SAP Build Apps is not supported.


**Related Information**  


[HTML5 Apps Content Provider \(Local Repository\)](html5-apps-content-provider-local-repository-ad2103e.md "An overview of federating content from the HTML5 Apps content provider.")

[Transporting Content Manually](transporting-content-manually-b2a3a47.md "Administrators can transport content between Dev, Test, and Production environments.")

