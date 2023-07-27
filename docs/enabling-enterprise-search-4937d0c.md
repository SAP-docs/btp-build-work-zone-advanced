<!-- loio4937d0ce590c4cb8ad7af14b67775f56 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Enabling Enterprise Search

SAP Build Work Zone, advanced edition offers an enterprise search capability that searches across all SAP S/4HANA apps and business objects.



## About Enterprise Search in SAP Build Work Zone, advanced edition

In SAP Build Work Zone, advanced edition, in order to search in all SAP S/4HANA systems for SAP S/4HANA apps and business objects that are assigned to your role, you need to do the following:

-   Enable the *Enterprise Search* setting in the *Site Settings* screen.

-   Integrate enterprise search with your site.

    For more information, see [Integration with Enterprise Search](integration-with-enterprise-search-c96d636.md).


> ### Note:  
> If you've enabled the enterprise search setting without doing the integration steps, your search will be limited to your local apps \(for example, HTML5 apps, federated apps, and manually added apps that you've added to your subaccount\).



<a name="loio4937d0ce590c4cb8ad7af14b67775f56__section_by1_31m_hsb"/>

## How to Enable Enterprise Search

In SAP Build Work Zone, advanced edition, there are 2 types of search mechanisms. There's the built-in site search and the enterprise search. To switch between these search options, open the *Site Settings* screen as follows:

1.  From the Administration Console, under *External Integrations*, click *Business Content*.

2.  Click *Content Manager*.

3.  From the side navigation panel, click :globe_with_meridians: to open the Site Directory.

4.  On the site tile, click :gear: to open the *Site Settings* screen.

5.  Under *User Capabilities*, enable *Enterprise Search*.

    -   Selecting *Yes*, enables users to search for all apps that they have permissions to access \(SAP S/4HANA apps and local apps\). The search is done from the search bar in the shell header of the site. Searching for site content, people, workspaces, and more is not available from the search bar.

    -   Selecting *No* enables users to search for only site content. This content doesn't include applications assigned to their roles.



> ### Note:  
> Even if enterprise search is enabled, users can still use the site search by adding a dedicated *Search* widget to a workpage. For more information, see [How to Add Content to Workspaces](how-to-add-content-to-workspaces-19bf8aa.md).

For more details about how users can search in the site , see [How to Search in Your Site](how-to-search-in-your-site-a3a83b4.md).

