<!-- loiod435663b25ce44bcabb54fbfeaea1a69 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Deploying a Workspace Template

Deploy a workspace template using SAP Business Application Studio.



<a name="loiod435663b25ce44bcabb54fbfeaea1a69__context_cgn_5f5_xkb"/>

## Context

> ### Note:  
> Before deploying a workspace template on SAP Build Work Zone, advanced edition, verify that the subscription to SAP Business Application Studio and the subscription to SAP Build Work Zone, advanced edition are in the same subaccount and that a destination is configured to SAP Jam.



<a name="loiod435663b25ce44bcabb54fbfeaea1a69__steps_dgn_5f5_xkb"/>

## Procedure

1.  Launch SAP Business Application Studio and navigate to the dev space where you created the workspace template.

2.  To deploy a workspace template to the subaccount:

    -   Direct deployment: navigate to the project that contains the required workspace template. From the context menu of the `manifest.json` file, choose *Workspace Template: Deploy to SAP Build Work Zone, advanced edition*.
    -   ZIP download:
        1.  From the context menu of the *manifest.json* file, choose *Workspace Template: Package*.
        2.  The workspace template is packaged into a `<workspace-template>.zip` file. Right-click the `<workspace-template>.zip` file and select *Download* to download the file.
        3.  The workspace template is available in the *Downloads* folder in your file system. You can use this zip file to upload the workspace template in the Admin Console *Area & Workspace Configuration* \> *Workspace Templates*, using the *Upload Template* button.





<a name="loiod435663b25ce44bcabb54fbfeaea1a69__result_vhy_j4k_lyb"/>

## Results

The new workspace template is available in the Admin Console *Area & Workspace Configuration* \> *Workspace Templates* list \(if you don't see it immediately, please refresh your browser\). Select your newly added template, and click <span class="SAP-icons-V5"></span> on the right. In the context menu, choose *Edit* and enhance your template with content. For more information, see [Workspace Templates](../workspace-templates-8a27022.md).

