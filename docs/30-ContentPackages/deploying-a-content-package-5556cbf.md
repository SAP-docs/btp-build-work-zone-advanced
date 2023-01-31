<!-- loio5556cbf39cdf4d95b35bf7e886388a0b -->

# Deploying a Content Package

Deploy a content package using SAP Business Application Studio.



<a name="loio5556cbf39cdf4d95b35bf7e886388a0b__prereq_asx_vwy_wkb"/>

## Prerequisites

You’ve created a content package, see [Creating a Content Package](creating-a-content-package-9027b86.md).

> ### Note:  
> To deploy a content package on SAP Build Work Zone, advanced edition, verify if SAP Business Application Studio and the target are in the same subaccount and there’s a OAuth client-credential destination defined. If there’s no destination, users need to manually upload the package to the target.



<a name="loio5556cbf39cdf4d95b35bf7e886388a0b__context_cgn_5f5_xkb"/>

## Context



<a name="loio5556cbf39cdf4d95b35bf7e886388a0b__steps_dgn_5f5_xkb"/>

## Procedure

1.  Launch SAP Business Application Studio and navigate to the dev space where you created the content package.

2.  To deploy a content package, navigate to the project that contains the required content package. From the context menu of `manifest.json`, choose *Content Package: Deploy to SAP Build Work Zone, Advanced Edition*.

    Alternative way to deploy: From the context menu of *manifest.json*, choose *Content Package: Package*. The content package is packaged in a `<package>.zip` file. Then, right-click the `<package>.zip` file and select *Download* to download the file. The content package is available in the downloaded file. You can use this zip file to upload the content package to SAP Build Work Zone, advanced edition.


