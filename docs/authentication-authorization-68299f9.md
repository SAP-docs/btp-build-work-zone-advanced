<!-- loio68299f9dbcf541c2917a2bdbd667468c -->

# Authentication & Authorization



In SAP Build Work Zone, advanced edition, you can configure the following security settings.

> ### Note:  
> The following settings apply only to the Digital Workplace Service \(DWS\) component of the product. For more information about the overall trust settings, see [User Authentication, Provisioning and Authorization](user-authentication-provisioning-and-authorization-f04c185.md).


<table>
<tr>
<th valign="top">

Method



</th>
<th valign="top">

Use



</th>
<th valign="top">

Task



</th>
</tr>
<tr>
<td valign="top">

Trusted Certificate Authorities



</td>
<td valign="top">

If your organization uses unrecognized or self-signed certificates, add the certificate authority to the trusted certificate authorities of SAP Build Work Zone, advanced edition.



</td>
<td valign="top">

*External Integrations* \> [Add a Trusted Certificate Authority](add-a-trusted-certificate-authority-0f5c6b2.md)



</td>
</tr>
<tr>
<td valign="top">

OAuth Clients



</td>
<td valign="top">

You can authorize an external application to access the SAP Build Work Zone, advanced edition API by registering the application as an OAuth client.



</td>
<td valign="top">

*External Integrations* \> [Add an OAuth Client](add-an-oauth-client-b3c804e.md)



</td>
</tr>
<tr>
<td valign="top">

SAML Trusted IDP



</td>
<td valign="top">

You register a trusted SAML identity provider \(IDP\) so that users can be authenticated using the Security Assertion Markup Language \(SAML\). SAP Build Work Zone, advanced edition stores authorizations and their assignment.



</td>
<td valign="top">

*Authentication & Authorization* \> [SAML Trusted IDPs](saml-trusted-idps-c2f81fd.md)



</td>
</tr>
<tr>
<td valign="top">

SAML Local Identity Provider



</td>
<td valign="top">

You can configure SAP Build Work Zone, advanced edition as a SAML local identity provider for external applications. Users can then have single sign-on \(SSO\) access to those applications.



</td>
<td valign="top">

*Authentication & Authorization* \> [SAML Local Identity Provider](saml-local-identity-provider-176e87b.md)



</td>
</tr>
</table>

> ### Note:  
> If you want to change the business data that is shown in SAP Build Work Zone, advanced edition and have those changes communicated back to the source external business application:
> 
> -   See [Add a Trusted Certificate Authority](add-a-trusted-certificate-authority-0f5c6b2.md) if the external application to SAP Build Work Zone, advanced edition requires OAuth authorization.
> -   See [SAML Trusted IDPs](saml-trusted-idps-c2f81fd.md) if the external application to SAP Build Work Zone, advanced edition requires SAML authorization.

