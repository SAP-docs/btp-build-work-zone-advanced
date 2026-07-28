<!-- loioedc62f97f50a432bb8dba04626689050 -->

# Onboarding to SAP SuccessFactors Work Zone

A step by step guide for setting up SAP SuccessFactors Work Zone.



The SAP SuccessFactors Work Zone onboarding guide describes the simplest approach for user authentication and provisioning, when users are provisioned from SAP SuccessFactors \(source system\) to SAP SuccessFactors Work Zone \(target system\), using SAP Cloud Identity Services - Identity Provisioning as the user provisioning system. However, you can adjust the process to meet the requirements of your own environment.

For more information about different configuration options, see [User Authentication and Authorization](user-authentication-and-authorization-f04c185.md).

> ### Note:  
> You can’t subscribe to SAP SuccessFactors Work Zone if you’re already subscribed to SAP Build Work Zone, advanced edition on a given subaccount.



<a name="loioedc62f97f50a432bb8dba04626689050__section_sbz_xfd_4rb"/>

## About the Onboarding Process

Unlike many other services in SAP Business Technology Platform, it is not enough to subscribe to SAP SuccessFactors Work Zone and configure roles in order to access the service. The onboarding process a more complex because of the integration with the different components that comprise it, such as Identity Authentication and Identity Provisioning, the fact that the DWS component runs as in iframe inside the SAP SuccessFactors Work Zone application, and more.

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

[Prerequisites](prerequisites-96b51b1.md)

</td>
</tr>
<tr>
<td valign="top">

Run the SAP SuccessFactors Work Zone booster for automatic setup steps on your subaccount

</td>
<td valign="top">

[Run the Booster](run-the-booster-77be32c.md)

</td>
</tr>
<tr>
<td valign="top">

Complete the post-booster steps of connecting directly to Identity Authentication and creating a tenant with the relevant connectors in Identity Provisioning.

</td>
<td valign="top">

[Post Booster Configuration](post-booster-configuration-44fbeec.md)

</td>
</tr>
<tr>
<td valign="top">

Complete the final steps using the configurator wizard.

</td>
<td valign="top">

[Run the Configurator](run-the-configurator-07b0a26.md)

</td>
</tr>
</table>

A Learning Journey is available for you in *SAP Learning* where you can find explanations about basic architecture concepts and different aspects of the onboarding process. For more information, see [Implementing and Administering SAP Build Work Zone](https://learning.sap.com/learning-journeys/implement-and-administer-sap-build-work-zone).



<a name="loioedc62f97f50a432bb8dba04626689050__section_jtl_rvv_nnb"/>

## Unsubscribing from SAP SuccessFactors Work Zone

When unsubscribing from SAP SuccessFactors Work Zone, all new configurations will be deleted. All services that are part of the SAP SuccessFactors Work Zone setup will be unsubscribed, and their persisted data will be removed.

