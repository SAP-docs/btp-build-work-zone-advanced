<!-- loio13bd2ea33c7a4cc7bf5d229d4fdc3cb7 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Install a Content Package

Once your content package is uploaded, you need to install it.

Once your content package is displayed on the *Content Packages* screen \(whether you uploaded it yourself or if it was automatically uploaded from the content repository, you need to install it.

> ### Note:  
> If the content package contains apps that are rendered on a remote system, you need to configure a destination to the remote system in the *Destinations* screen of the SAP BTP cockpit. If a destination hasn't yet been configured, the content package will display an error message when you try to install it.

1.  Click <span class="SAP-icons"></span> to install the content package.

    Once installed, the content package status changes to *Installed*.

2.  To uninstall the content package, open <span class="SAP-icons"></span>and select *Uninstall*.

3.  Once uninstalled, you can delete the content package. Click <span class="SAP-icons"></span> and select *Delete*.

    > ### Note:  
    > You can only delete content packages that you've uploaded yourself.
    > 
    > Before uninstalling a content package, some content items may still be in use and will be affected as follows:
    > 
    > -   Cards are deleted and won't be available for display on any page.
    > 
    > -   Workflows are deleted as well as the content derived from it.
    > 
    > -   Workspaces aren't deleted. If the workspace was created based on a template, it won't be deleted, but the template will no longer be available for future use.
    > 
    > -   Home pages are not deleted.
    > 
    > 
    > If the installation or uninstallation fails, click *Download Report* to view the error log and try resolving the problem. Sometimes, the provider of a content package provides a link to get support. If this is the case, you'll see a *Get Support* button next to the error message.


