<!-- loio0a7f9acd4dba4aa1b84f7f36b3330d84 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Map Back-End System Aliases to Runtime Destinations

When a back-end system has aliases, the administrator needs to map these aliases to the relevant runtime destination.



The mapping is needed to support cross-app navigation used by legacy apps \(Wed Dynpro, SAP GUI\) when running in an intent-based navigation environment. Back-end systems may have several aliases assigned to them, which are used in cross-app navigation. When navigating from one app to another, the app URL might contain the `sap-system` parameter that points to one of the aliases. To ensure that the navigation succeeds, it is necessary to map the back-end aliases to the corresponding runtime destinations.

This is done in the subaccount settings screen: *Settings* \> *Alias Mapping*.

To specify the alias, use sid notation. For example: `sid(<system id>.<client>)`

> ### Note:  
> The alias mapping is saved at the subaccount level.
> 
> As a result, if there are apps that come from different back-end systems that have the same alias, the alias mapping will be possible only for one of the back-end systems.



<a name="loio0a7f9acd4dba4aa1b84f7f36b3330d84__section_cp3_hxd_t4b"/>

## Procedure



1.  In the subaccount *Settings* screen, select the *Alias Mapping* tab.

2.  Click :heavy_plus_sign: to add a mapping to the table.

3.  Type one or more aliases in sid notation, separated by pressing the [Enter\] key.

4.  Select the corresponding runtime destination.

5.  Repeat steps 2-4 for any additional aliases.

6.  Save.


