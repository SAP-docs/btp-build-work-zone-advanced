<!-- loio14f44d455abe4f16bc70a8282ac73ab6 -->

# Configure SSO

This section describes the steps for configuring Single Sign On \(SSO\) to access on-premise systems, such as SAP S/4HANA or SAP Business Suite, using principal propagation.



## Overview

The authentication type principal propagation, also known as user propagation or user principal propagation, enables single sign-on \(SSO\) to an on-premise system or service by forwarding for each user a unique identifier, such as email.

The workflow includes the following steps:

1.  Configure the Cloud Connector
2.  Configure identity propagation to the on-premise system
3.  Assign users and configure destinations on SAP BTP
4.  Configure the identity provider \(IdP\)



<a name="loio14f44d455abe4f16bc70a8282ac73ab6__section_afm_zsj_fnb"/>

## Configure the Cloud Connector

In the Cloud Connector Administration tool, you perform configuration steps at the subaccount level and at the system level, to enable the Cloud Connector to connect to your on-premise system.

> ### Note:  
> This configuration is not necessary if you have already configured principal propagation for your Cloud Connector at the subaccount level and at the on-premise systems level.



### Subaccount Level

To set up Cloud Connector at the subaccount level, perform the following steps:


<table>
<tr>
<th valign="top">

Step

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

Configure Cloud Connector to connect to the subaccount in which you are subscribed to SAP Build Work Zone, advanced edition.

</td>
<td valign="top">

[Initial Configuration](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/a4ee70f0274248f8bbc7594179ef948d.html)

</td>
</tr>
<tr>
<td valign="top">

Configure **trust** from the Cloud Connector to the identity provider \(IdP\) to accept its user tokens as valid. The IdP can be an SAP or a corporate identity provider.

</td>
<td valign="top">

[Set Up Trust - Configure Trusted Entities in the Cloud Connector](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/a4ee70f0274248f8bbc7594179ef948d.html)

When using a corporate IdP: [Principal Propagation from SAP BTP Applications to On-Premise Systems Using Corporate IdP Tokens](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/1503442f766145fd8cfe9caa0c087da3.html)

</td>
</tr>
<tr>
<td valign="top">

Configure **access control** mapping to specify the on-premise systems that can be accessed by your cloud applications. Make sure that you use the principal type X.509 Certificate in the corresponding system mapping.

</td>
<td valign="top">

[Configure Access Control \(HTTP\)](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e7d4927dbb571014af7ef6ebd6cc3511.html)

If ICF services are relevant: [Configure Principal Propagation to an ABAP System for HTTPS - Access ICF Services](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/a8bb87a72d094e0d981d2b1f67df7bc3.html)

</td>
</tr>
</table>



### System Level

To set up Cloud Connector at the system level, perform the following steps: [Configuring Principal Propagation](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/c84d4d0b12d34890b334998185f49e88.html):


<table>
<tr>
<th valign="top">

Step

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

Make sure the **system certificate** exists.

The SSL handshake between Cloud Connector and the on-premise system is performed through the system certificate.

</td>
<td valign="top">

[Set Up Trust - Configure an On-Premise System for Principal Propagation](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/a4ee70f0274248f8bbc7594179ef948d.html#loioa4ee70f0274248f8bbc7594179ef948d__configure_on_premise)

</td>
</tr>
<tr>
<td valign="top">

Configure a **CA certificate** \(or make sure it exists\).

The Cloud Connector uses the configured CA certificate to issue short-lived certificates for logging on to the same identity in the backend as is logged on to in the cloud.

</td>
<td valign="top">

[Configure a CA Certificate](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/d0c4d5675d4f4bc78a5b7a7b8687c841.html)

</td>
</tr>
<tr>
<td valign="top">

Configure a **subject pattern** for principal propagation.

This pattern identifies the user for the subject of the generated short-lived X.509 certificate, as well as its validity period.

</td>
<td valign="top">

[Configure Subject Patterns](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/58803a25e5894d759e0df1c5513b41ed.html)

</td>
</tr>
</table>



<a name="loio14f44d455abe4f16bc70a8282ac73ab6__section_t5q_1tj_fnb"/>

## Configure identity propagation to the on-premise system

To configure identity propagation to the on-premise system:

-   Perform the steps that are relevant to HTTP in this topic: [Configure Identity Propagation for HTTPS](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/configure-principal-propagation-for-https).
-   If you are using SAP Web Dispatcher, perform also the steps in this topic: [Configure Identity Propagation via SAP Web Dispatcher](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/configure-principal-propagation-via-sap-web-dispatcher).


<table>
<tr>
<th valign="top">

Step

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

Configure the ABAP system to trust the system certificate of SAP Cloud Connector. If the system certificate is signed by CA, then you need to import the certificate into the SSL trust service list.

</td>
<td valign="top">

[Configure Principal Propagation to an ABAP System for HTTPS - Configure an ABAP System to Trust the Cloud Connector's System Certificate](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/a8bb87a72d094e0d981d2b1f67df7bc3.html)

</td>
</tr>
<tr>
<td valign="top">

Set the profile parameters in the instance profile - verify that the SAP Cloud Connector port has a client certificate enabled and set `Verify_Client=1`.

</td>
<td valign="top">

[Setting the Profile Parameters for Using SSL](https://help.sap.com/viewer/e73bba71770e4c0ca5fb2a3c17e8e229/7.51.2/en-US/4923691cbf5a1902e10000000a42189c.html)

</td>
</tr>
<tr>
<td valign="top">

User mapping – rule-based mapping of certificates is the recommended approach and it's based on the `CERTRULE` transaction.

</td>
<td valign="top">

[Rule-based Mapping of Certificates](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/4f8540f4c01f447992ef2f3dff8ab4dd.html)

</td>
</tr>
</table>



<a name="loio14f44d455abe4f16bc70a8282ac73ab6__section_l1t_1tj_fnb"/>

## Assign users and configure destinations on SAP BTP

You need to assign users to role collections or roles, and configure a design-time destination with basic authentication and a runtime destination with principal propagation.



### Assign Users

The way to assign users depends on whether you selected to use the SAP Cloud Identity Services - Identity Provisioning service \(IPS\) when creating the content provider for your on-premise system.

**With IPS**

If you selected to use IPS when creating the content provider, you need to create an IPS source system \(an on-premise system\) and a target system in the SAP Build Work Zone, standard edition instanceeven when usingSAP Build Work Zone, advanced edition.

The user authorization data is replicated from the source system to the target system for the respective roles.

For more information, see [Configure Integration with the Identity Provisioning Service](https://help.sap.com/docs/build-work-zone-standard-edition/sap-build-work-zone-standard-edition/configure-integration-with-identity-provisioning-service).

**Without IPS**

When not using IPS, you need to assign users to the role collections, which were created automatically on SAP BTP when the roles were added from the content provider. This can be done in one of the following ways:


<table>
<tr>
<th valign="top">

Step

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

Manual assignment:

Use the admin UI in the SAP BTP cockpit.

</td>
<td valign="top">

[Assign Users to Role Collections](https://help.sap.com/docs/btp/sap-business-technology-platform/assign-users-to-role-collections?locale=en-US&state=PRODUCTION&version=Cloud) 

</td>
</tr>
<tr>
<td valign="top">

Assignment via attribute mapping:

Use the attribute mapping \(for example, Groups\) from the connected IdP, relying on the OIDC token values.

</td>
<td valign="top">

[Mapping Role Collections](https://help.sap.com/docs/btp/sap-business-technology-platform/mapping-role-collections-in-subaccount?locale=en-US) 

</td>
</tr>
<tr>
<td valign="top">

Assignment via API:

Assigning through the XSUAA SCIM API, using identity provisioning. For this setup, a dedicated target system is available to assign or unassign role collections.

</td>
<td valign="top">

[SAP BTP XS Advanced UAA](https://help.sap.com/docs/btp/sap-business-technology-platform/mapping-role-collections-in-subaccount?locale=en-US) 

</td>
</tr>
</table>



### Create Destinations

In the subaccount in which you are subscribed to SAP Build Work Zone, advanced edition, you need to create the following destinations:

-   A **design-time** destination with **basic authentication**, which points to the on-premise system via the Cloud Connector. \(Principal propagation is not supported.\)

-   A **runtime** destination with **principal propagation**, which points to the on-premise system.


For more information, see [Configure Destinations \(On Premise\)](configure-destinations-on-premise-f337b80.md) and [Principal Propagation SSO Authentication for HTTP](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/73194cc419894433994c5f0444b4c6a1.html).



<a name="loio14f44d455abe4f16bc70a8282ac73ab6__section_nw5_1tj_fnb"/>

## Configure the identity provider \(IdP\)

Create an application for the subaccount:

1.  Determine the *Subject Name ID* – the recommendation is to use `email`.

    For more information, see [Configure User Attributes from the Identity Directory](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/configure-subject-name-identifier-sent-to-application?state=PRODUCTION&version=Cloud&locale=en-US).

2.  Configure the user attributes to be sent to the application. For example, add `Groups` to the IdP as a user attribute.

    For more information, see [Configure the User Attributes Sent to the Application](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/d361407d36c5443298a909acbbd96ec4.html).


