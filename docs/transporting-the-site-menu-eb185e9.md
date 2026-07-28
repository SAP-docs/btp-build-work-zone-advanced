<!-- loioeb185e94b91c4f45b4801e7535879bf7 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Transporting the Site Menu

Site administrators can transport a site menu including workpages that are referenced from the site menu, from one environment to another using the import and export feature.



## Export the Site Menu

Export the site menu including workpages as follows:

1.  Open the Site Menu editor.

2.  From the left panel, click the <span class="SAP-icons-V5"></span> Export icon.

3.  An *Export Menu* dialog box opens - select the checkbox to include all menu content.

    > ### Note:  
    > If you select this option, all content items from the *Menu Content* screen will be exported. If you don't select it, only content that is referenced by the menu is exported.

4.  Click *Export* to start the export process and don't refresh your window until it's done.

    > ### Note:  
    > When you click *Export*, the menu is saved as a draft version and exported as a ZIP64 file. The access control settings aren't exported.




<a name="loioeb185e94b91c4f45b4801e7535879bf7__section_gln_j24_fzb"/>

## Import the Site Menu

Once you've exported the site menu, you can import it into a different environment as follows:

1.  From the left panel of the site menu, click the <span class="SAP-icons-V5"></span> Import icon.

2.  The *Import Menu* dialog box opens. Browse your computer to where you saved the ZIP file, and click *Agree and Import* to start the import process. The import process runs in the background and you won't be able to edit the menu until the import is done.

    > ### Note:  
    > When the menu is imported into the target environment, it's saved as a draft. You'll need to redefine access control for custom menu items, and reconfigure the reference to any workspace type menu item \(workspaces won't point to any workspace after import because the same workspace it points to in the source system, probably doesn't exist in the target system\). Once these configurations are done, you need to publish the menu in the target system.


