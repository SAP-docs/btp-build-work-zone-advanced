<!-- loio361d44573e42468894e75b40ef02057c -->

# Configure a SAML Local Service Provider

Configure a SAML Local Service Provider when you need SAP Build Work Zone, advanced edition to act as a Service Provider for SAML requests issued to an Identity Provider.



<a name="loio361d44573e42468894e75b40ef02057c__section_gx5_c2b_nrb"/>

## How to configure SAP Build Work Zone, advanced edition as a SAML local service provider

> ### Note:  
> The following settings apply only to the Digital Workplace Service \(DWS\) component of the product.

1.  Access the Administration Console and expand the *Authentication & Authorization* area.

2.  Select *SAML Local Service Provider* to display the page where you'll do the configuration.

    The first three fields \(*Issuer*, *Assertion Consumer Service*, and *Single Logout Service*\) are URIs that are needed by the identity provider so that they can use SAP Build Work Zone, advanced edition as a SAML local service provider. Take note of these URIs for the configuration of your identity provider.

3.  Click *Download SP Metadata* and use your browser's download file capabilities to save the metadata file to your hard drive. Save this file for the configuration of your identity provider.

4.  Click *Generate Key Pair* to automatically fill the *Request Signing Private Key* and the *Request X.509 Certificate \(Base64\)* text boxes with the required information.

5.  Once these steps are done, click *Save* to store the *Request Signing Private Key* and *Request X.509 Certificate \(Base64\)*.

6.  In order to work with your identity provider, configure it with the information you noted and downloaded.

