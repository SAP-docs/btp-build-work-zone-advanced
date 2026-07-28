<!-- loio5556cbf39cdf4d95b35bf7e886388a0b -->

# Deploying a Content Package

Deploy a content package using SAP Business Application Studio.



<a name="loio5556cbf39cdf4d95b35bf7e886388a0b__context_cgn_5f5_xkb"/>

## Context

You can deploy the content package to your subaccount in one of the following ways:

1.  Deploy the content package directly from SAP Business Application Studio to your subaccount. To be able to do that, the subscription to SAP Business Application Studio must exist on the same subaccount as the subscription to SAP Build Work Zone, advanced edition. In addition, there must be an OAuth client-credential destination defined.
2.  Package your content package into a ZIP file and then manually upload it to your subaccount, as explained below.



<a name="loio5556cbf39cdf4d95b35bf7e886388a0b__steps_dgn_5f5_xkb"/>

## Procedure

1.  Launch SAP Business Application Studio and navigate to the dev space where you created the content package.

2.  To deploy a content package:

    -   Direct deployment: Right-click the *manifest.json* file and choose *Content Package: Deploy to SAP Build Work Zone, advanced edition*.
    -   ZIP download:
        1.  Right-click the *manifest.json* file and choose *Content Package: Package*. The content package is packaged in a `<package>.zip` file.
        2.  Right-click the `<package>.zip` file and select *Download* to download the file. The content package is available in the Downloads folder in your file system.
        3.  In the Admin Console *UI Integration* \> *Content Packages*, use the *Upload Content Package* button to upload the ZIP file from your file system.



