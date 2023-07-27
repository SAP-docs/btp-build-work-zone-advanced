<!-- loioe89a79c691f849a2a98e7da292b37413 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Transporting Business Content

Administrators can transport business content between different services and between different environments.

Business content includes apps, roles, groups, catalogs, and shell plugins that are configured in the Content Manager, which is located in the Site Manager.

For more information about business content, see [Adding Apps to Your Site](adding-apps-to-your-site-cb936ef.md)

To transport business content between services and environments, you first need to select the content that you want to transport.

Access the Content Manager as follows:

1.  From the *Administration Console* menu, go to *External Integrations* \> *Business Content*.

2.  Click *Content Manager*.




<a name="loioe89a79c691f849a2a98e7da292b37413__section_dqv_kmy_cpb"/>

## Exporting business content from SAP Build Work Zone, advanced edition

In this scenario, you're exporting selected content items as follows:

1.  When you open the Content Manager, the *My Content* tab is in focus. From the list of content items, select those that you want to export.

2.  Click <span class="SAP-icons"></span> \(export selected content items\)at the top right of the list of content items.

3.  In the dialog that opens, review the list of selected items, and click *Export*.

    A transport package is downloaded to the default *Downloads* folder of the browser and appears in the following format: `ContentTransport_YYMMDD_HHMMSS.zip`

    The transport package with the exported content can then be imported to another environment or to another service.


> ### Note:  
> -   When you export an app, only the app is exported.
> 
> -   When you export a group or a catalog, the apps assigned to them are also exported.
> 
> -   When you export a role, its assigned apps are also exported, as well as the groups and catalogs to which the apps are assigned.
> 
> -   The *Everyone* role \(and its related content\) isn't exported. Even if you select it, it won't appear in the list of content items to export.



<a name="loioe89a79c691f849a2a98e7da292b37413__section_qsk_pry_cpb"/>

## Importing business content into SAP Build Work Zone, advanced edition

In this scenario, you're importing a transport package that was exported from another service or environment.

> ### Note:  
> -   Before importing content, make sure that the content providers from the source landscape are also defined in the target landscape, and that the ID of each provider is identical in all the environments. Otherwise, the content from these content providers won't be imported. For information about editing the ID, see [Edit the ID of a Content Provider.](https://help.sap.com/viewer/8c8e1958338140699bd4811b37b82ece/Cloud/en-US/28d9ffac644940048f6cb92e14ef2b96.html)
> 
> -   You can't import a file that is larger than 10 MB.

1.  When you open the Content Manager, the *My Content* tab is in focus. Click <span class="SAP-icons"></span> \(import content items\) at the top right of the list of content items.

2.  In the dialog that opens, select the transport package zip file from your *Downloads* folder.

3.  If a site with the same ID already exists in the target environment, a popup message enables you to choose whether to overwrite the existing site or cancel the import. Click *Agree and Import* if you agree that the imported content will overwrite any identical content that exists in the target landscape.

4.  Click *Import*.

5.  Go to the *Applications* page in your site to see the content items that you imported.


