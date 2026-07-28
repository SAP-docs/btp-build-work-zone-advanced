<!-- loio232b6da08a9e4bcc914b24c30372be0e -->

# Set Up Automatic Updates for an SAP Enterprise Portal Content Provider

Administrators can set up automatic updates of an SAP Enterprise Portal content provider when the content on the SAP Enterprise Portal system changes. This replaces the need to manually fetch updated content in the Channel Manager.



## Overview

> ### Note:  
> Automatic updates from SAP Enterprise Portal are enabled by default starting from version 7.5 SP22.

When creating a content provider for a system with version 7.5 SP22 or above, saving the content provider automatically sends a callback URL to the SAP Enterprise Portal system. The callback URL is used by the SAP Enterprise Portal system to update the content provider when there are changes to the exposed content, thus enabling automatic updates.

If the version in use when creating a content provider is 7.5 SP21 or below, or there was an error in creating the provider, or there is an existing content provider from an earlier release, then it is necessary to manually activate the “fetch updated content” action once to ensure that the callback URL is sent to the SAP Enterprise Portal system. This manual update must end with the status ‘Updated’ so that the automatic updates will begin to take place from that point on.

To disable automatic updates, this option needs to be disabled in the SAP Enterprise Portal system. For more information, see the section about *Portal Services Configuration* in [Enterprise Portal as a Content Provider to SAP BTP](https://help.sap.com/viewer/40fb2965584a448a996f1e1aa3e3c08d/7.5.22/en-US/3199ba8b24244b32bce08cbe7fff7dd3.html).



<a name="loio232b6da08a9e4bcc914b24c30372be0e__section_of2_t33_5qb"/>

## Callback URL

The callback URL is used by SAP Enterprise Portal system to connect to the SAP Build Work Zone, advanced edition.

SAP Enterprise Portal uses a *Check if URL in Allowed List* property that is disabled by default.

If this property is enabled, then you **must add** the callback URL to the allowed list of URLs, as described in the section about *Portal Services Configuration* in [Enterprise Portal as a Content Provider to SAP BTP](https://help.sap.com/viewer/40fb2965584a448a996f1e1aa3e3c08d/7.5.22/en-US/3199ba8b24244b32bce08cbe7fff7dd3.html).

The format of the callback URL:

`portal-service.cfapps.<datacenter>.<domain>`

For example:

`portal-service.cfapps.eu10.hana.ondemand.com`

**Related Information**  


[Configuring the Automatic Creation/Deletion of Role Collections on SAP BTP](configuring-the-automatic-creation-deletion-of-role-collections-on-sap-btp-60eaf50.md "To enable the creation or deletion of role collections on SAP BTP automatically, it is necessary to configure a destination to the Identity Authentication service.")

[Set Up Automatic Updates for Content Providers](set-up-automatic-updates-for-content-providers-b5f4f4e.md "Administrators can set up automatic updates of content consumed from a remote content provider. This replaces the need to manually fetch updated content in the Channel Manager every time the content changes.")

