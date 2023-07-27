<!-- loioc96d63621c5f4d81868682917472571b -->

# Integration with Enterprise Search

Enterprise Search provides direct search access to business data stored in SAP S/4HANA.



To locate business objects using the search bar, SAP Enterprise Search must be integrated and set up in your environment. Otherwise, the search returns only the local apps that have been deployed to the subaccount. The search result list contains all the business objects and apps you're authorized to access. Search providers must be connected to Enterprise Search to make their objects available for searching.

> ### Note:  
> When using SAP Enterprise Search and SAP Gateway OData services in a co-deployed configuration, you have to change the SAP Gateway configuration according to the following SAP Note [3191725](https://launchpad.support.sap.com/#/notes/3191725). Otherwise, navigation from an enterprise search result list item to an object page, may fail.



## Prerequisites

-   Enterprise Search is up and running.

    For more information see, [Setting Up Enterprise Search](https://help.sap.com/viewer/6522d0462aeb4909a79c3462b090ec51/1709.latest/en-US/f12e6f2de1424beda6286370406e7fcc.html)

-   SAP cloud connector is connected to the subaccount in which you connect to Enterprise Search. The SAP Gateway system, which is connected to the Enterprise Search backend, is exposed through SAP cloud connector and reachable from the cloud.

    For more information, see [Set Up Cloud Connector](https://help.sap.com/viewer/8c8e1958338140699bd4811b37b82ece/Cloud/en-US/009642f3831041d9a8d89651158a6099.html)




<a name="loioc96d63621c5f4d81868682917472571b__section_fbx_bqn_nqb"/>

## Configuration



### S/4HANA

1.  **Configure Destinations**

    1.  In the SAP BTP cockpit, *Destinations* screen, open the runtime destination, which exposes the enterprise search system.
    2.  Add a custom property to the destination: `launchpad.esearch.provider` with value `abap_odata`.

2.  **Configure Alias Mapping**

    1.  Open the Channel Manager screen in the Site Manager.
    2.  Edit the content provider that is using the above destination, click the *Alias Mapping* link.
    3.  In the *Alias Mapping* dialog, add an alias mapping for the Enterprise Search backend using the following format: `sid(<sid>.<client>)`. Replace <sid\> and <client\> with the correct values and without <\> characters. `sid` value must be all **uppercase**.

    For more information, see [Manage Content Providers \(On Premise\).](https://help.sap.com/viewer/ad4b9f0b14b0458cad9bd27bf435637d/Cloud/en-US/021bc1192cbd455d898542dcf584440e.html) 

3.  **Enable Enterprise Integration Setting**

    Open the Site Settings of your site and toggle on the *Enterprise Search Integration* setting.




### S/4HANA Cloud

1.  **Configure Destinations**

    1.  In the SAP BTP cockpit, open the *Destinations* screen. For S/4HANA Cloud there are two runtime destinations. One is used for launching apps in an iFrame via a direct URL to the host, and another one for retrieving dynamic data. Edit the runtime destination that launches the app in an iFrame.
    2.  Add a custom property to the destination: `launchpad.esearch.provider` with value `abap_odata`.

2.  **Configure Alias Mapping**

    1.  Open the Channel Manager screen in the Site Manager.
    2.  Edit the content provider and click the *Alias Mapping* link.
    3.  In the *Alias Mapping* dialog, add an alias mapping between the OData runtime destination and the Enterprise Search backend using the following format: `sid(<sid>.<client>)`. Replace <sid\> and <client\> with the correct values and without <\> characters. `sid` value must be all **uppercase**.

    For more information, see [Manage Content Providers \(Cloud\).](https://help.sap.com/viewer/ad4b9f0b14b0458cad9bd27bf435637d/Cloud/en-US/021bc1192cbd455d898542dcf584440e.html) 

3.  **Enable Enterprise Integration Setting**

    Open the Site Settings of your site and toggle on the *Enterprise Search Integration* setting.

    > ### Note:  
    > Make sure that the display setting *Search in Shell Header* is also set to *Yes*.




<a name="loioc96d63621c5f4d81868682917472571b__section_l3q_cyn_nqb"/>

## Using Enterprise Search

For more information about searching for business objects and apps, filtering and saving the search results, see [Searching for Business Objects and Apps](https://help.sap.com/viewer/3d99fdeadde04524bdd33d35f1e13777/Cloud/en-US/03000c73b2474a318bb2e9882d62676a.html)

