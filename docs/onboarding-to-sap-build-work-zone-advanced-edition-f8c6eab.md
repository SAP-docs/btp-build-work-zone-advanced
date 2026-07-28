<!-- loiof8c6eab5b9c8437f9367271863ac90eb -->

# Onboarding to SAP Build Work Zone, advanced edition

A step by step guide for setting up SAP Build Work Zone, advanced edition.



> ### Note:  
> In China region, SAP Build Work Zone, advanced edition, which is based on the subscription commercial model, isn’t supported. You can only onboard to SAP SuccessFactors Work Zone.

The SAP Build Work Zone, advanced edition onboarding guide describes the simplest approach for user authentication and provisioning, using SAP Cloud Identity Services - Identity Authentication as the primary IdP and SAP Cloud Identity Services - Identity Provisioning for user provisioning. However, you can adjust the process to meet the requirements of your own environment.

For example, instead of using Identity Authentication as the primary IdP, you can use an SAP or 3rd-party IdP as a source system for user data, and use Identity Authentication as a proxy between the source and SAP Build Work Zone, advanced edition. Another example is that in the onboarding guide you are instructed to use SuccessFactors as a source system in Identity Provisioning when onboarding to SAP SuccessFactors Work Zone, however, there is no real restriction here. You can choose any source system from the supported list in Identity Provisioning.

For more information about different configuration options, see [User Authentication and Authorization](user-authentication-and-authorization-f04c185.md).

> ### Note:  
> You can’t subscribe to SAP Build Work Zone, advanced edition if you’re already subscribed to SAP SuccessFactors Work Zone on a given subaccount.



<a name="loiof8c6eab5b9c8437f9367271863ac90eb__section_vx2_4hh_2mb"/>

## About the Onboarding Process

Unlike many other services in SAP Business Technology Platform, it is not enough to subscribe to SAP Build Work Zone, advanced edition and configure roles in order to access the service. The onboarding process is more complex because of the integration with the different components that comprise it, such as Identity Authentication and Identity Provisioning, the fact that the DWS component runs in an iframe inside the SAP Build Work Zone, advanced edition application, and more.

The onboarding process consists of the following steps:


<table>
<tr>
<th valign="top">

Step

</th>
<th valign="top">

Detailed Instructions

</th>
</tr>
<tr>
<td valign="top">

Complete the prerequisite configurations such as setting up an account, establishing trust, and more.

</td>
<td valign="top">

[Prerequisites](prerequisites-9e78b62.md)

</td>
</tr>
<tr>
<td valign="top">

Run the SAP Build Work Zone, advanced edition booster for automatic setup steps on your subaccount.

</td>
<td valign="top">

[Run the Booster](run-the-booster-4679f1c.md)

</td>
</tr>
<tr>
<td valign="top">

Complete the post-booster steps of connecting directly to Identity Authentication and creating a tenant with the relevant connectors in Identity Provisioning.

</td>
<td valign="top">

[Post Booster Configuration](post-booster-configuration-e567b51.md)

</td>
</tr>
<tr>
<td valign="top">

Complete the final steps using the configurator wizard.

</td>
<td valign="top">

[Run the Configurator](run-the-configurator-7202ced.md)

</td>
</tr>
</table>

A Learning Journey is available for you in *SAP Learning* where you can find explanations about basic architecture concepts and different aspects of the onboarding process. For more information, see [Implementing and Administering SAP Build Work Zone](https://learning.sap.com/learning-journeys/implement-and-administer-sap-build-work-zone).



<a name="loiof8c6eab5b9c8437f9367271863ac90eb__section_vwm_k55_nnb"/>

## Unsubscribing from SAP Build Work Zone, advanced edition

When unsubscribing from SAP Build Work Zone, advanced edition, all new configurations will be deleted. All services that are part of the SAP Build Work Zone, advanced edition setup will be unsubscribed, and their persisted data will be removed.

