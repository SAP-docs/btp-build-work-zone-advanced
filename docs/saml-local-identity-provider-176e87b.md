<!-- loio176e87bb4f464b508370302398d00878 -->

# SAML Local Identity Provider

You can configure SAP Build Work Zone, advanced edition as a SAML local identity provider for external applications. Users can then have single-sign on \(SSO\) access to those applications.

> ### Note:  
> The following settings apply only to the Digital Workplace Service \(DWS\) component of the product.

1.  In the *Authentication & Authorization* section, go to the *SAML Local Identity Provider* page.

    The *Issuer* field contains the URL that shows the issuer identity, in this case, your company's SAP Build Work Zone, advanced edition instance.

2.  Choose *Generate Key Pair*.

    The *Signing Private Key* and *X509 Certificate* information is generated.

3.  Copy the information you want to use. The *Signing Private Key* is used for generating SAML assertions. The *X509 Certificate* is used when creating SAML Trusted IDPs, where the created IDP is used as the issuer in the generated SAML assertions.

4.  Save your changes.

