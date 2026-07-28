<!-- loio92c4adbca05841ee8609375c76268bc2 -->

# SMTP Server Configuration

Administrators can replace the default SMTP server configuration with their own SMTP server configuration to send out notification emails.



In some cases you might want to use your own company's SMTP server to send out email notifications about workspace-related changes.

The SMTP server settings are using for the workspace-level notifications. To integrate with the central SAP BTP notification mechanism, you need an additional configuration of creating destination to the SAP BTP SMTP server.

To revert to the default SMTP server settings, simply delete the custom settings that you've added.

> ### Note:  
> For deployments in regions with EU data access requirements, customers **must** configure the integration with their own SMTP server to enable the built-in SAP Build Work Zone email notifications. This configuration is mandatory , as no default mail service is provided by the platform in these regions.

**Related Information**  


[Configure a Custom SMTP Server](configure-a-custom-smtp-server-407647d.md "Administrators can configure their own SMTP server to send out email notifications, instead of using the default SAP Build Work Zone, advanced edition SMTP server.")

[Email Notifications](email-notifications-75aaf05.md "Configure your preferred email SMTP server that will be used to send email notifications.")

