<!-- loioee7d8935fcd44ee1917800879db3048f -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Transport Selected Content

Transport specific content items between Dev, Test, and Production landscapes.



<a name="loioee7d8935fcd44ee1917800879db3048f__section_h1l_rht_21c"/>

## Overview

To transport business content between services and environments, you first need to select the content that you want to transport in the Content Manager.

Access the Content Manager as follows:

1.  From the *Administration Console* menu, go to *External Integrations* \> *Business Content*.

2.  Click *Content Manager*.




<a name="loioee7d8935fcd44ee1917800879db3048f__section_z2b_4k4_3nb"/>

## Export Selected Content Items

1.  In the Content Manager, select the content items that you want to export.

    Toggle the *Selected* button at the top, to toggle between viewing only the selected items or viewing all the items in the list.

2.  Click <span class="SAP-icons-V5"></span> \(export selected content items\)at the top right of the list of content items.

3.  In the dialog that opens, review the list of selected items and click *Export*.


As a result, a transport package is downloaded by the browser to the default downloads folder of the browser.

The transport package name is in the following format:

`ContentTransport_YYMMDD_HHMMSS.zip`



<a name="loioee7d8935fcd44ee1917800879db3048f__section_a44_j1k_ylb"/>

## Import Content

> ### Note:  
> -   You cannot import a file that is larger than 50 MB.
> 
> -   Export and import do not support deleted entities on the target system.
> 
>     Entities deleted in the source system could remain visible in the Content Manager of the target system, but they will not be visible in runtime.

1.  In the Content Manager, click *Import* above the list on the right.

2.  Select the transport package that was created in the source landscape, and choose *Agree & Import* to agree that the imported content will overwrite any identical content that exists in the target landscape.

3.  If one or more content providers are not defined in the target landscape, you receive a list of the missing providers.

    Choose one of the following options:

    -   Cancel the import, define the missing content providers, and then import again.

    -   Continue with the import. This means that the content of the missing content providers will not be imported.

        You can define the missing content providers at a later stage and import again.



**Related Information**  


[Before Transporting Content - Important Rules and Guidelines](before-transporting-content-important-rules-and-guidelines-4d3f192.md "The rules and guidelines regarding transporting content and the related content that is also exported when exporting content items.")

[Transporting Content Manually](transporting-content-manually-b2a3a47.md "Administrators can transport content between Dev, Test, and Production environments.")

