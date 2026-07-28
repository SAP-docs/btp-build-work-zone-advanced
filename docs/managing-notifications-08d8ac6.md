<!-- loio08d8ac6251904410a247734c21ae7bca -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Managing Notifications

Notifications enable users to get immediate updates on the latest and most important events that are related to their daily work.



<a name="loio08d8ac6251904410a247734c21ae7bca__section_v3q_lp4_spb"/>

## Introduction

As an administrator, you can configure notifications from various systems such as SAP S/4HANA, SAP BTP, and more. Users can access their notifications from the right side of the header bar of their site by clicking the :bell: \(notifications\) icon and they can act on these notifications.

![The bell icon of the notifications appears on the right side of the header bar.](images/Notification_icon_in_site_header_8a022aa.png)

There are two notification mechanisms:

-   SAP Build Work Zone, advanced edition default notification mechanism that covers all events within the site, such as new and changed content, requests to access, and actions related to workspaces.

-   SAP Notification service - a notification mechanism that displays notifications from multiple providers.


> ### Note:  
> The SAP Notification service is optional. If you choose to configure it, the local notifications will continue to use the default notification mechanism, while all the notifications from other providers are sent by the SAP Notification service. An exception to this is when the SMTP mail destination is configured. In that case, the SAP Notification service is used for all notifications.



<a name="loio08d8ac6251904410a247734c21ae7bca__section_mkj_blh_tzb"/>

## How to enable the integration with SAP Notification service

To enable the use of SAP Notification service \(on top of the default notification mechanism\), complete the following steps.

> ### Note:  
> Once you've enabled the integration with SAP Notification service, you can't reverse the configuration.

1.  Set up an integration with SAP Task Center. This integration is mandatory because some of the workspace notifications were migrated to SAP Task Center.
    -   For more information about setting up SAP Task Center, see [Initial Setup](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/834769400794464489f390350a82bbd6.html).
    -   For more information about the migrated notifications, see [Notifications Migrated to SAP Task Center](notifications-migrated-to-sap-task-center-103020b.md).

2.  Access the *Site Settings* screen as follows:
    -   Under your avatar, click *Administration Console*.

    -   Go to the *External Integrations* section, expand it, and click *Business Content*.

    -   In the screen that opens, click *Content Manager*.
    -   From the *Content Manager* navigate to the *Settings* screen using the left-side menu.

3.  Under the *Notifications* tab, confirm that you’ve completed integration with the SAP Task Center.
4.  Click *Switch* to enable the integration with SAP Notification service.



> ### Note:  
> To manage notification preferences, make sure you are assigned to the relevant business roles. For more info, please refer to the [3315110](https://me.sap.com/notes/3315110) .

**Related Information**  


[Enabling Notifications From Cloud Solutions and Services](enabling-notifications-from-cloud-solutions-and-services-cbe83dd.md "Enable publishing notifications from cloud solutions. Users can access the notifications from the shell header of their site.")

[Enabling Notifications From SAP S/4HANA](enabling-notifications-from-sap-s-4hana-394a035.md "Enable publishing notifications from SAP S/4HANA. Users can access the notifications from the shell header of their site and they can act on these notifications.")

[Enabling Notifications for Custom Apps on SAP BTP Cloud Foundry](enabling-notifications-for-custom-apps-on-sap-btp-cloud-foundry-d5429a2.md "Custom apps that have been developed and deployed to SAP BTP, Cloud Foundry environment can be configured to publish notifications. Users can access the notifications from the shell header of their site and they can act on these notifications.")

[Email Notifications](email-notifications-75aaf05.md "Configure your preferred email SMTP server that will be used to send email notifications.")

