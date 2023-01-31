<!-- loiod435663b25ce44bcabb54fbfeaea1a69 -->

# Deploying a Workspace Template

Deploy a workspace template using SAP Business Application Studio.



<a name="loiod435663b25ce44bcabb54fbfeaea1a69__prereq_asx_vwy_wkb"/>

## Prerequisites

You’ve created a workspace template, see [Creating a Workspace Template](creating-a-workspace-template-d1a7b42.md).

> ### Note:  
> Before deploying a workspace template on SAP Build Work Zone, advanced edition, verify that SAP Business Application Studio and the target are in the same subaccount and that a destination is configured to SAP Jam.



<a name="loiod435663b25ce44bcabb54fbfeaea1a69__context_cgn_5f5_xkb"/>

## Context



<a name="loiod435663b25ce44bcabb54fbfeaea1a69__steps_dgn_5f5_xkb"/>

## Procedure

1.  Launch SAP Business Application Studio and navigate to the dev space where you created the workspace template.

2.  To deploy a workspace template, navigate to the project that contains the required workspace template. From the context menu of `manifest.json`, choose *Workspace Template: Deploy to SAP Build Work Zone, Advanced Edition*.

    Alternative way to deploy: From the context menu of *manifest.json*, choose *Workspace Template: Package*. The workspace template is packaged in a `<workspace-template>.zip` file. Then, right-click the `<workspace-template>.zip` file and select *Download* to download the file. The workspace template is available in the downloaded file. You can use this zip file to upload the workspace template to SAP Build Work Zone, advanced edition.


