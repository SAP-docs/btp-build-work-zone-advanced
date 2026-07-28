<!-- loio407647d2a92b4b88a07aef8eef97732b -->

# Configure a Custom SMTP Server

Administrators can configure their own SMTP server to send out email notifications, instead of using the default SAP Build Work Zone, advanced edition SMTP server.



## Overview

You can replace the default SMTP server provided by SAP Build Work Zone, advanced edition with your company's SMTP server, to send out email notification. Doing so will also let you use your own custom domain address, and own sender and reply-to email addresses.

> ### Note:  
> The custom SMTP server can be used for the SAP Build Work Zone, advanced edition notifications. To use the central SAP BTP notification mechanism and integrate multiple notification providers, you also need to configure a destination to the SAP BTP SMTP server. For more information, see [Configuring an SMTP Mail Destination](configuring-an-smtp-mail-destination-e403f2c.md).



<a name="loio407647d2a92b4b88a07aef8eef97732b__section_vgf_1gh_1bc"/>

## Procedure

In the Admin Console, go to *External Integrations* \> *SMTP Server Configuration*, and enter all the require settings.

To reset the SMTP server settings and go back to the default SAP Build Work Zone, advanced edition SMTP server, simply click *Delete Configuration*.

