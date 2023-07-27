<!-- loiocb936ef56acb4c6a9bdb37870e373e43 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Adding Apps to Your Site

You can add apps from different sources into the workpages of your site from the Content Manager tool.



<a name="loiocb936ef56acb4c6a9bdb37870e373e43__section_uy5_4pl_fnb"/>

## Which apps can you add to your site?

The apps that you can add to your workpages can be grouped as follows :

-   **Business apps**

    These are apps that are assigned to roles, groups, and catalogs. In SAP Build Work Zone, advanced edition, these apps are displayed on the *Applications* page - a single page in SAP Build Work Zone, advanced edition. The business apps are displayed as tiles that a user can launch. The *Applications* page is filtered to display only apps that the user can access.

    On the *Applications* page, the app tiles are displayed either in *Group* mode or *Spaces and Pages* mode depending on the settings defined for a specific site.

    -   In *Group* mode, the app tiles are organized in one or more groups on a workpage.

    -   In *Spaces and Pages* mode, there are one or more spaces - each space can have one or more workpages that display the app tiles organized into different sections.

        > ### Note:  
        > You can only select this option if the apps have been modeled using spaces and pages. In cases where you have some apps modeled in spaces and pages and others modeled in groups, you'll see the apps displayed in spaces and pages mode. You'll also see a specific space called *Home Page* that displays the groups - this is an applications home page and is not to be confused with a site's home page.


-   **Other apps**

    These are applications that are not modeled as business apps and can't be found in the Content Manager. You'll find these apps in the App Finder, which is basically a catalog of **all** the apps that a user is allowed to see \(including business apps and functional apps that are provided out-of-the-box with your site\).


> ### Note:  
> To enable users to quickly find all their apps, you can enable the *All My Apps* navigation option in the *Site Settings* screen. Once enabled, the user can click *Home* and the top hierarchical navigation menu of the site is automatically launched in the middle of the shell header. This enables users to browse and navigate through the apps that they have permissions to use. For more information, see [Launching Apps from the Top Navigation Bar](launching-apps-from-the-top-navigation-bar-35a8be7.md).



<a name="loiocb936ef56acb4c6a9bdb37870e373e43__section_f4k_wvq_2pb"/>

## How to add apps to your site?



### Adding business apps

To add business apps to your site, you need to configure them in a tool called the Content Manager, located in the Site Manager. Once configured, they're visible in the *Applications* page of your site. You can access the Content Manager as follows:

1.  From the *Administration Console* menu, go to *External Integrations* \> *Business Content*.

2.  Click *Content Manager*.


The Content Manager includes 2 tabs:

-   *My Content*

    Displays a list of all the business content items such as apps, groups, catalogs, roles, and shell plugins that exist in your subaccount. From here, you can access the various editors to configure your content.

-   *Content Explorer* 

    Displays all available business content that is exposed by various content channels. From here, you can explore and select the content that you want from a channel and add it to your subaccount.


For more information, see [Add Business Apps](add-business-apps-8bf719e.md)



### Adding apps to the App Finder

You can find all the apps that you have permission to access in a tool called the App Finder.

To access the App Finder, click the <span class="SAP-icons"></span> icon from the header of your screen or from the User Actions menu, depending on how you defined it in the *Site Settings* screen.

The apps appear in categories and can include:

-   Functional apps that are part of the product - for example, depending on your role, you'll see Home, Administration Console, User Profile, Notifications, and others. You don't need to add these apps to your site as they already come with the product.

-   Business apps that are displayed on the *Applications* page of your site. If you've assigned your business apps to a catalog in the Content Manager, you'll be able to see them in the App Finder under the name of the catalog you assigned them to.

-   All other apps that you've permissions to see - these apps are available to you to add to your workpages. For more information, see [Add Apps to Your Workpages](add-apps-to-your-workpages-e7c9cef.md).


