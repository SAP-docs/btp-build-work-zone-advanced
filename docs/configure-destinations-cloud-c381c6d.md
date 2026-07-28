<!-- loioc381c6d865074c81b0e1b682500ec1cd -->

# Configure Destinations \(Cloud\)

In the SAP BTP cockpit, you create a design-time destination to define the location from which to fetch the exposed content. In addition, you create the runtime destinations to obtain the resources needed to run the federated apps in runtime.



## Design-Time Destination

In the SAP BTP cockpit, in your subaccount, navigate to *Connectivity* \> *Destinations*.

Use the following properties to define the design-time destination:


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

We recommend to add the suffix `dt` to the name.

> ### Note:  
> The name should be unique for the current application. It should contain only alphanumeric characters, underscores, or dashes. The maximum length is 200 characters.



</td>
</tr>
<tr>
<td valign="top">

URL

</td>
<td valign="top">

Enter the value according to your content provider:


<table>
<tr>
<td valign="top">

SAP S/4HANA Cloud

</td>
<td valign="top">

`https://<host>-api.s4hana.cloud.sap:<port number>/sap/bc/http/sap/APS_FLP_CONTENT_EXPOSURE/entities`

> ### Note:  
> The URL should match the SAP S/4HANA Cloud domain that is in use - either `s4hana.cloud.sap` or `s4hana.ondemand.com.`



</td>
</tr>
<tr>
<td valign="top">

SAP IBP

</td>
<td valign="top">

`https://<host>-api.scmibp1.ondemand.com/sap/bc/http/sap/aps_flp_content_exposure/entities`

</td>
</tr>
<tr>
<td valign="top">

SAP BTP ABAP environment

</td>
<td valign="top">

`https://<guid>.abap.<region>.hana.ondemand.com/sap/bc/http/sap/aps_flp_content_exposure/entities`

</td>
</tr>
</table>



</td>
</tr>
<tr>
<td valign="top">

Proxy Type

</td>
<td valign="top">

*Internet*

</td>
</tr>
<tr>
<td valign="top">

Authentication Method

</td>
<td valign="top">

Choose the authentication method you selected for the communication system \(see [Create a Communication System with Inbound and Outbound Users](https://help.sap.com/viewer/4fc8d03390c342da8a60f8ee387bca1a/latest/en-US/f8b7fcba6b3a467a8486cd18572caefb.html)\).

> ### Note:  
> The selected method must also be supported on the side of the content provider.

The following methods are supported:

-   *ClientCertificateAuthentication* \(recommended\)

    > ### Note:  
    > The value of the Keystore Location must be a PFX file. You can convert JKS or PEM files to PFX format using the OpenSSL tool. The keystore might require a password.
    > 
    > To continue you need to include a trusted certificate authority \(CA\) certificate. The list of known and trusted CAs can be found here: [2801396](https://me.sap.com/notes/2801396).

-   *Basic Authentication*

-   *OAuth2ClientCredentials*




</td>
</tr>
<tr>
<td valign="top">

User

</td>
<td valign="top">

> ### Note:  
> This field is only relevant if you use *Basic Authentication* as authentication method.

Enter the user you have created in the *Communication User* app. See [Create a Communication System with Inbound and Outbound Users](https://help.sap.com/viewer/4fc8d03390c342da8a60f8ee387bca1a/latest/en-US/f8b7fcba6b3a467a8486cd18572caefb.html).

</td>
</tr>
</table>



<a name="loioc381c6d865074c81b0e1b682500ec1cd__section_f2x_kpw_5sb"/>

## Runtime Destinations

> ### Note:  
> Multiple runtime destinations with identical URLs, but different authentication methods are not supported.
> 
> In case multiple content channels are using the same backend, please make sure to use the same runtime destination with the same authentication method.

To create the runtime destinations, in the SAP BTP cockpit, in your subaccount, navigate to *Connectivity* \> *Destinations*.

There are two types of runtime destinations:


<table>
<tr>
<th valign="top">

Destination Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Runtime Destination*

</td>
<td valign="top">

The default runtime destination for launching apps in an iFrame via a direct URL to the UI host of the cloud solution.

</td>
</tr>
<tr>
<td valign="top">

*Runtime Destination for Dynamic Data* \(Optional\)

</td>
<td valign="top">

A runtime destination for fetching data for dynamic tiles, only when this destination is different than the default one.

When integrating SAP ABAP Cloud systems, it is mandatory to define this second destination, because while direct access is used for the apps, the access to the dynamic data is via tunneled access.

> ### Note:  
> When using two destinations with different HTTP clients, then different security session cookies are issued. As a result, there will be multiple entries in the *Display Security Audit Log* app of your solution.



</td>
</tr>
</table>

> ### Note:  
> The destinations are very similar. However, note that the value of the *URL* parameter is different.

**Runtime Destination**

The following table lists the properties that are required to configure a runtime destination.


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

Specify a name for the destination.

</td>
</tr>
<tr>
<td valign="top">

Type

</td>
<td valign="top">

*HTTP*

</td>
</tr>
<tr>
<td valign="top">

Description

</td>
<td valign="top">

Enter a description.

</td>
</tr>
<tr>
<td valign="top">

URL

</td>
<td valign="top">

Enter the value according to your content provider:


<table>
<tr>
<td valign="top">

SAP S/4HANA Cloud

</td>
<td valign="top">

`https://<SAP S/4HANA Cloud tenant host>.s4hana.cloud.sap`

> ### Note:  
> The URL should match the SAP S/4HANA Cloud domain that is in use - either `s4hana.cloud.sap` or `s4hana.ondemand.com`.



</td>
</tr>
<tr>
<td valign="top">

SAP IBP

</td>
<td valign="top">

`https://<SAP IBP Cloud tenant host>.scmibp1.ondemand.com`

</td>
</tr>
<tr>
<td valign="top">

SAP BTP ABAP environment

</td>
<td valign="top">

`https://<SAP BTP ABAP environment tenant host>.abap-web.<region>.hana.ondemand.com`

</td>
</tr>
</table>



</td>
</tr>
<tr>
<td valign="top">

Proxy Type

</td>
<td valign="top">

*Internet*

</td>
</tr>
<tr>
<td valign="top">

Authentication

</td>
<td valign="top">

*NoAuthentication*

</td>
</tr>
<tr>
<td valign="top">

HTML5.DynamicDestination

\(additional property\)

</td>
<td valign="top">

`true`

> ### Note:  
> To enable CSRF protection via the approuter, set the`CEP.EnableCsrfProtection` destination property to *true* for all dynamic destinations where their respective backend doesn’t handle CSRF protection.
> 
> If your backend is already protected, there’s no need to add this property.

> ### Caution:  
> Adding an `HTML5.DynamicDestination` property and setting it to true, enables dynamic access to the destination to any logged-in user.
> 
> Therefore before adding this property to the destination, make sure that the underlying API is not public and requires the correct user credentials.



</td>
</tr>
<tr>
<td valign="top">

sap-platform

\(additional property\)

</td>
<td valign="top">

`ABAP`

</td>
</tr>
</table>

**Runtime Destination for Dynamic Data**

The following table lists the properties that are required to configure a runtime destination for fetching dynamic data displayed on dynamic tiles, if this destination is different than the default runtime destination.


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description/Value

</th>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

Specify a name for the destination.

</td>
</tr>
<tr>
<td valign="top">

Type

</td>
<td valign="top">

*HTTP*

</td>
</tr>
<tr>
<td valign="top">

Description

</td>
<td valign="top">

Enter a description.

</td>
</tr>
<tr>
<td valign="top">

URL

</td>
<td valign="top">

Enter the value according to your content provider:


<table>
<tr>
<td valign="top">

SAP S/4HANA Cloud

</td>
<td valign="top">

`https://<SAP S/4HANA Cloud tenant host>-api.s4hana.cloud.sap`

> ### Note:  
> The URL should match the SAP S/4HANA Cloud domain that is in use - either `s4hana.cloud.sap` or `s4hana.ondemand.com`.



</td>
</tr>
<tr>
<td valign="top">

SAP IBP

</td>
<td valign="top">

`https://<SAP IBP Cloud tenant host>-api.scmibp1.ondemand.com`

</td>
</tr>
<tr>
<td valign="top">

SAP BTP ABAP environment

</td>
<td valign="top">

`https://<SAP BTP ABAP environment tenant host>.abap.<region>.hana.ondemand.com`

</td>
</tr>
</table>



</td>
</tr>
<tr>
<td valign="top">

Proxy Type

</td>
<td valign="top">

*Internet*

</td>
</tr>
<tr>
<td valign="top">

Authentication

</td>
<td valign="top">

*SAMLAssertion*

</td>
</tr>
<tr>
<td valign="top">

Audience

</td>
<td valign="top">

Enter the value according to your content provider:


<table>
<tr>
<td valign="top">

SAP S/4HANA Cloud

</td>
<td valign="top">

`https://<SAP S/4HANA Cloud tenant host>.s4hana.cloud.sap`

> ### Note:  
> The URL should match the SAP S/4HANA Cloud domain that is in use - either `s4hana.cloud.sap` or `s4hana.ondemand.com`.



</td>
</tr>
<tr>
<td valign="top">

SAP IBP

</td>
<td valign="top">

`https://<SAP IBP Cloud tenant host>.scmibp1.ondemand.com`

</td>
</tr>
<tr>
<td valign="top">

SAP BTP ABAP environment

</td>
<td valign="top">

`https://<SAP BTP ABAP environment tenant host>.abap-web.<region>.hana.ondemand.com`

</td>
</tr>
</table>



</td>
</tr>
<tr>
<td valign="top">

AuthnContextClassRef

</td>
<td valign="top">

`urn:oasis:names:tc:SAML:2.0:ac:classes:PreviousSession`

</td>
</tr>
<tr>
<td valign="top">

nameIdFormat

\(additional property\)

</td>
<td valign="top">

`urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress`

</td>
</tr>
<tr>
<td valign="top">

HTML5.DynamicDestination

\(additional property\)

</td>
<td valign="top">

`true`

</td>
</tr>
<tr>
<td valign="top">

sap-platform

\(additional property required for SAP ABAP Cloud systems\)

</td>
<td valign="top">

`ABAP`

</td>
</tr>
</table>

As a result, in calls to the cloud solution tenant, the user ID \(i.e. the E-Mail received via the Identity Authentication tenant proxy from the corporate IdP\) is sent with the format *nameIdFormat* as the Subject Name ID in the SAML Bearer assertion.

> ### Note:  
> After saving the destination, select it and click the *Destination Trust* option \(above the destinations' table\) to download the trust certificate for the destination.
> 
> You will need this certificate in the next step:
> 
> -   SAP S/4HANA Cloud: [Configure Communication for the Content Consumption](https://help.sap.com/docs/SAP_S4HANA_CLOUD/4fc8d03390c342da8a60f8ee387bca1a/386f16bba3884924a4c54507fd5347c2.html?version=latest&locale=en-US)
> -   SAP IBP: [Configure Communication for the Content Consumption](https://help.sap.com/viewer/0292066056f642f1a0f6d9135e39abaf/latest/en-US/386f16bba3884924a4c54507fd5347c2.html)
> -   SAP BTP ABAP environment: [Configure Communication for the Content Consumption](https://help.sap.com/docs/BTP/10fd1742ea914256abedb34bf15bd069/386f16bba3884924a4c54507fd5347c2.html?version=Cloud)

