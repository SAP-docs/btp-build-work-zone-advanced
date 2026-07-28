<!-- loioe567b51e2e554814836bf2d7b0e2a9fc -->

# Post Booster Configuration

The following steps can be executed only after successfully running the booster. They are required to connect your subaccount to the SAP Cloud Identity Services - Identity Provisioning, and to switch the authentication mechanism to SAP Cloud Identity Services - Identity Authentication.



<a name="loioe567b51e2e554814836bf2d7b0e2a9fc__section_epl_zqp_5wb"/>

## Switch to SAP Cloud Identity Services - Identity Authentication

> ### Note:  
> This step is only applicable to subscriptions created before March 20th, 2025. If you created a subscription after this date, your subaccount is already connected directly to Identity Authentication and you can skip this step.

For subscriptions created before March 20th, 2025, by default, SAP Build Work Zone, advanced edition is integrated with Identity Authentication indirectly, through SAP Authentication and Trust Management service \(XSUAA\). Some capabilities, such as using a custom domain, are not fully supported in this setup, therefore, it is required to form a direct connection with Identity Authentication as follows:

1.  Access the Site Manager as follows: In the SAP BTP cockpit, *Services* \> *Instances and Subscriptions*, click on the subscription to SAP Build Work Zone, advanced edition in the *Subscriptions* table to access the application.
2.  Open the *Settings* screen from the left-side menu.
3.  Select the *Identity Authentication* tab.

4.  Confirm that your subaccount has an active trust configuration with SAP Cloud Identity Services - Identity Authentication.

5.  Click *Enable*.

    > ### Note:  
    > This action can take up to 15 minutes to take effect.

    > ### Note:  
    > For instructions how to switch back to SAP Authorization and Trust Management service \(XSUAA\), refer to [3311634](https://me.sap.com/notes/3311634).


> ### Note:  
> After switching to Identity Authentication as the authentication mechanism, you can use App to App Navigation to consume the APIs of another application in Identity Authentication. Other applications or services may use a different application in Identity Authentication than the one used by SAP Build Work Zone, advanced edition, therefore, it is necessary to request tokens with access privileges for APIs of the other application and enable token exchange. For more information, see [Configure Integration Between Applications.](https://help.sap.com/docs/identity-authentication/identity-authentication/communicate-between-applications).
> 
> If the App to App navigation is modeled using the `IASDependencyName` property in the GACD \(Generic Application Content Deployer\) HTML5 deployer module, the SAP Build Work Zone, advanced edition approuter will perform an App to App navigation from its application in Identity Authentication to the Identity Authentication application accessed from the repository service. For more information about approuters and their destinations, see [Application Routes and Destinations.](https://help.sap.com/docs/btp/sap-business-technology-platform/application-routes-and-destinations).



<a name="loioe567b51e2e554814836bf2d7b0e2a9fc__section_zz3_k2g_mxb"/>

## Connect Your Subaccount to Identity Provisioning



### Prerequisites

-   The integration with the Identity Provisioning service supports only one active Identity Authentication tenant. Before you start the configuration, open the cockpit, *Security* \> *Trust Configuration*, and verify that you have only one active Identity Authentication trust configuration in the list. The default IdP, `sap.default`, is not relevant to the flow and can be ignored for this requirement. After the connection is formed, you can configure additional active IdPs.
-   If you already have an active Identity Authentication tenant, you are required to reconnect it to the Identity Provisioning service after you've modified it.



### Connector for User and Group Provisioning

> ### Note:  
> This step is required only if you don't already have an active tenant with SAP Build Work Zone, advanced edition connector configured for your subaccount.

1.  Access the Site Manager as follows: In the SAP BTP cockpit, *Services* \> *Instances and Subscriptions*, click on the subscription to SAP Build Work Zone, advanced edition in the *Subscriptions* table to access the application.
2.  Open the *Settings* screen from the left-side menu.
3.  Go to the *Identity Provisioning* tab, and click the *Connect* button.
    -   If your subaccount is not yet connected to the Identity Provisioning service, a new tenant will be created for your subaccount, and it will include the SAP Build Work Zone, advanced edition connector. In addition, a connection will be created between the Identity Authentication service and the Identity Provisioning service.
    -   If your subaccount already has an Identity Provisioning tenant connected to the Identity Authentication service, clicking the connect button will expand the scope of the tenant to include the SAP Build Work Zone, advanced edition connector.


At this point, the connector is created with default values. In the next step of the onboarding, when you run the configurator, you will have to configure specific values.

SAP Build Work Zone, advanced edition is also available as a bundle connector. For more information about , see [SAP Build Work Zone Bundle](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/930015d483a74ee8b68a132db7699825.html).



### Connector for Integrating Remote Content \(Optional\)

If you plan to integrate business content from remote business providers, you can use the Identity Provisioning to provision users authorizations from the remote providers \(instead of using SAP BTP role mechanism\).

To use Identity Provisioning for this purpose, you need to configure a connector to SAP Build Work Zone, standard edition in addition to the connector you've configured for SAP Build Work Zone, advanced edition.

When you click *Connect*, a connector to SAP Build Work Zone, standard edition is created as well. To complete the configuration you need to define the source and target system based on your scenario:

-   Source system - select the Identity Provider from which you want to fetch the user authorizations: [Source Systems](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/sap-build-work-zone-advanced-edition).
-   Target system - if you connect to Identity Authentication directly, use these settings: [SAP Build Work Zone, standard edition](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/sap-build-work-zone-standard-edition).
-   Proxy system - if you're using Identity Authentication as a proxy, use these settings [SAP Build Work Zone, standard edition](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/proxy-sap-build-work-zone-standard-edition).



### Troubleshooting


<table>
<tr>
<th valign="top">

Error

</th>
<th valign="top">

Cause

</th>
<th valign="top">

Possible Solution

</th>
</tr>
<tr>
<td valign="top">

The connection to the Identity Provisioning service has failed.

</td>
<td valign="top">

Connection failed due to an internal issue.

</td>
<td valign="top">

As instructed on the screen, please open a support ticket. To find the component details, see [Getting Support](getting-support-37b7948.md)

In this case, the *Retry* button isn't active.

</td>
</tr>
<tr>
<td valign="top">

Could not find an active Identity Authentication service tenant. Please check your configuration and try again.

</td>
<td valign="top">

Connection failed due to lack of an active Identity Authentication Service tenant.

</td>
<td valign="top">

Verify that you have an active tenant. Open the SAP BTP cockpit, *Security* \> *Trust Configuration* and verify that your Identity Authentication Service tenant is set to *Active*. Note that an active default identity provider is not sufficient for this scenario.

Once you've fixed the configuration, click *Retry*.

</td>
</tr>
<tr>
<td valign="top">

Sorry, something has gone wrong. Please try again later.

</td>
<td valign="top">

Connection failed due to a temporary issue.

</td>
<td valign="top">

This error is presented when there's a temporary glitch. In this case, you should try again later.

The *Retry* button is active in this case.

</td>
</tr>
</table>



### Exploring Role Assignments

After you have set up the integration with the Identity Provisioning service, you can explore the role assignment that were provisioned to the system for specific users. For more information, see [Exploring Role Assignments](exploring-role-assignments-7eed569.md).

