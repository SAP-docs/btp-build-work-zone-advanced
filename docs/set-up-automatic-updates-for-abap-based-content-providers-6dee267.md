<!-- loio6dee2677010c48beb81d95074be1d965 -->

# Set Up Automatic Updates for ABAP-Based Content Providers

Administrators can set up automatic updates for ABAP-based content providers, such as SAP S/4HANA on premise and cloud, and SAP BTP ABAP environment. After setting this up, there is not need to manually fetch the updated content every time the content changes.



> ### Note:  
> Automatic updates are supported as of S/4HANA Cloud version 2111, and S/4HANA 2021 initial shipment.



<a name="loio6dee2677010c48beb81d95074be1d965__section_of2_t33_5qb"/>

## Callback URL

To set up automatic updates, a callback URL is used by the provider system to update the SAP Build Work Zone, advanced edition when there are changes to the exposed content.



### Format & Example:

`portal-service.cfapps.<datacenter>.<domain>`

`portal-service.cfapps.eu10.hana.ondemand.com`



### Format & Example \(China Region\):

`portal-service.portal.<datacenter>.<domain>`

portal-service.portal.cn40.apps.platform.sapcloud.cn

For more information about configuring the callback URL on the provider system, see:

-   S/4HANA - [Managing Content Change Notifications](https://help.sap.com/viewer/a7b390faab1140c087b8926571e942b7/202110.000/en-US/a6e718dcfe4f47e5adc71078bb35ec74.html)
-   S/4HANA Cloud - [Enable Content Change Notifications](https://help.sap.com/docs/SAP_S4HANA_CLOUD/4fc8d03390c342da8a60f8ee387bca1a/99ee1a851f404b00b16675c06726c347.html)

**Related Information**  


[Configuring the Automatic Creation/Deletion of Role Collections on SAP BTP](configuring-the-automatic-creation-deletion-of-role-collections-on-sap-btp-60eaf50.md "To enable the creation or deletion of role collections on SAP BTP automatically, it is necessary to configure a destination to the Identity Authentication service.")

[Set Up Automatic Updates for Content Providers](set-up-automatic-updates-for-content-providers-b5f4f4e.md "Administrators can set up automatic updates of content consumed from a remote content provider. This replaces the need to manually fetch updated content in the Channel Manager every time the content changes.")

