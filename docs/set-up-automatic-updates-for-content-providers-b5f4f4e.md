<!-- loiob5f4f4e965194924ab392d591205a9f5 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Set Up Automatic Updates for Content Providers

Administrators can set up automatic updates of content consumed from a remote content provider. This replaces the need to manually fetch updated content in the Channel Manager every time the content changes.



In the Channel Manager, you can manually update a content provider with changes from the back-end system, by using the action :arrows_clockwise:.

However, instead of the manual option, it is possible to set up automatic updates so that the content of the provider in the Channel Manager is updated automatically every time there are changes to the exposed content of the provider. A notification from the content provider is only sent to the Channel Manager when there is a new exposure with changes, so to have this fully automated, you would need to schedule for the content provider regular exposure runs, which would then trigger the notification about the change to be sent to the Channel Manager so that the content channel is updated.

To enable automatic updates from the content provider, the back-end system needs to configure a callback URL, that is used to inform the SAP Build Work Zone, advanced edition about the content changes.

The process involves:

1.  Configuring the callback URL on the back-end system of the provider. This is done differently, depending on the content provider type: ABAP-Based or SAP Enterprise Portal:

    -   [Set Up Automatic Updates for an SAP Enterprise Portal Content Provider](set-up-automatic-updates-for-an-sap-enterprise-portal-content-provider-232b6da.md)

    -   [Set Up Automatic Updates for ABAP-Based Content Providers](set-up-automatic-updates-for-abap-based-content-providers-6dee267.md)


2.  If you are using SAP BTP role mechanism to manage authorizations, configure the automatic creation/deletion of role collections on SAP BTP. This step is not relevant if you are using the Identity Provisioning service to manage authorizations.

    For more information, see [Configuring the Automatic Creation/Deletion of Role Collections on SAP BTP](configuring-the-automatic-creation-deletion-of-role-collections-on-sap-btp-60eaf50.md).


