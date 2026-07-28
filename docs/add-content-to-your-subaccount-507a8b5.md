<!-- loio507a8b535c954df2aaef30b1458e9917 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Add Content to Your Subaccount

The *Content Explorer* displays the available content providers. From each content provider, you can select content items, such as apps and shell plugins, and add them to your subaccount.



**Prerequisites**

You have reviewed the following information for the relevant content provider:

-   [HTML5 Apps Content Provider \(Local Repository\)](html5-apps-content-provider-local-repository-ad2103e.md)
-   [Launchpad Modules Content Providers](launchpad-modules-content-providers-713f2f8.md)



**Procedure**

1.  Open the *Content Manager* and then select the *Content Explorer*, to explore content from the available content providers.
2.  Choose the content provider from which you want to add content.

    A table displays a list of all the apps and shell plugins that the selected provider exposes.

3.  Select the content items that you want to add to your subaccount.

4.  Click *Add* to add the selected content items to your subaccount.

    As a result, they are added to the list of content items in the *Content Manager*.

5.  In the *Content Manager*, assign each app to a group. You can optionally add the app to a catalog to make it available in the App Finder. For more information, see [Assign Apps to Groups](assign-apps-to-groups-6f60d52.md).

    > ### Note:  
    > This step is relevant only for apps, not for shell plugins.

6.  Also in the *Content Manager*, assign each app and shell plugin to at least one role.

    For more information, see [Assign Content to a Role](assign-content-to-a-role-baeaf6e.md).

7.  From the *Site Directory*, click the :gear: icon to open the *Site Settings* screen of the site.

8.  Click *Edit* and assign the role to the site from the *Assignments* panel on the right to enable access to the apps and shell plugins assigned to the role.


> ### Note:  
> Federated apps can be viewed in the content editors but can't be edited.



<a name="loio507a8b535c954df2aaef30b1458e9917__section_gdh_2lw_11c"/>

## How to remove a provider-based content item

You can remove a provider-based app or shell plugin from your subaccount.

In the *Content Explorer*, the last column in the list displays a *Remove* option next to each content item that was added to the subaccount.

When you remove a provider-based content item:

-   It is no longer selected in the *Content Explorer* list.

-   It is removed from the list in the *Content Manager*.

-   The app is removed from any assignments to catalogs, groups, and roles.

-   The shell plugin is removed from any assignments to roles.


