<!-- loioedc62f97f50a432bb8dba04626689050 -->

# Onboarding to SAP SuccessFactors Work Zone

A step by step guide for setting up SAP SuccessFactors Work Zone.



This onboarding guide describes the simplest approach for user authentication and provisioning, where users are provisioned from SAP SuccessFactors \(source system\) to SAP SuccessFactors Work Zone \(target system\), using SAP Cloud Identity Services - Identity Provisioning as the user provisioning system. However, there are other approaches that can be used, depending on your environment setup.

For more information about different configuration options, see [User Authentication, Provisioning and Authorization](user-authentication-provisioning-and-authorization-f04c185.md)

> ### Note:  
> For information about onboarding to SAP Build Work Zone, advanced edition see, [Onboarding to SAP Build Work Zone, advanced edition](onboarding-to-sap-build-work-zone-advanced-edition-f8c6eab.md)



<a name="loioedc62f97f50a432bb8dba04626689050__section_sbz_xfd_4rb"/>

## About the Onboarding Process

SAP SuccessFactors Work Zone consists of several components. The onboarding process is required to integrate these components into a comprehensive, working digital solution.

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

Prerequisite steps before launching the SAP SuccessFactors Work Zone application.



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

Connect your subaccount to the Identity Provisioning service.



</td>
<td valign="top">

[Post Booster Configuration](post-booster-configuration-44fbeec.md)



</td>
</tr>
<tr>
<td valign="top">

Post provisioning steps after launching the application, in the form of a wizard.



</td>
<td valign="top">

[Run the Configurator](run-the-configurator-07b0a26.md)



</td>
</tr>
</table>



<a name="loioedc62f97f50a432bb8dba04626689050__section_yrt_dfw_g4b"/>

## Migration and Implementation Considerations

To read more about architecture, the migration path, and implementation concepts to be considered while planning and executing an implementation of SAP SuccessFactors Work Zone, see [Implementation Design Principle](https://d.dam.sap.com/a/3nZVVDd)

> ### Note:  
> After customers complete the SAP SuccessFactors Work Zone migration process, some of the existing SAP Jam functionality will not be supported, including SAP Jam Mobile app functionality for feeds and groups. For customers with mobile requirements, it is recommended to deploy the SAP Build Work Zone, advanced edition Mobile app instead. For more information about unsupported features, see [Restrictions](restrictions-b259464.md)



<a name="loioedc62f97f50a432bb8dba04626689050__section_jtl_rvv_nnb"/>

## Unsubscribing from SAP SuccessFactors Work Zone

When unsubscribing from SAP SuccessFactors Work Zone, all new configurations will be deleted. All services that are part of the SAP SuccessFactors Work Zone setup will be unsubscribed, and their persisted data will be removed.

