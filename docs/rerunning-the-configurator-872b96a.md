<!-- loio872b96aa749f4ce4aef7578a61edd6db -->

# Rerunning the Configurator

After obtaining the custom domain, you must rerun the onboarding configurator and use your custom domain instead of the default domain. Using a non-custom domain such as ondemand.com is not supported once you've already configured a custom domain.



## Step 1: Copy OAuth Client Details

Before running the configurator, have the OAuth client details ready. You will have to enter them to the configurator. In the Admin Console, go to *External Integrations* \> *OAuth Clients*, and copy the details of the OAuth client that was created when you ran the configurator for the first time.

-   For tenants that were upgraded for SAP Jam, use the OAuth client that was created for SAP Jam.
-   For new tenants, use the OAuth client that was created for SAP Build Work Zone, advanced edition via the configurator run.

> ### Note:  
> Do not use the OAuth client that was created for the SCIM API provisioning - `Workzone API Client`.



<a name="loio872b96aa749f4ce4aef7578a61edd6db__section_tmr_j52_gbc"/>

## Step 2: Reset the Configurator

Reset the configurator to make sure all previously entered data has been removed.

1.  Open the configurator from the Site Manager \( `<design time URL of default domain>/sites#Workzone-Config`\). You can also access the Site Manager from the Admin Console, *External Integrations* \> *Business Content.* \> *Configurator*.
2.  Navigate back using the **<** icon to the screen where you need to select the configuration option.
3.  Select the respective other option from what you selected in the first run. If you previously selected a new service instance, select now a service instance based on a SAP Jam tenant, and vice versa.
4.  In the warning message that pops up, confirm the loss of input data.
5.  Navigate back again.
6.  Select the previous option \(the option you originally selected\).
7.  Confirm loss of data again.
8.  Re-run the configurator with fresh input!

