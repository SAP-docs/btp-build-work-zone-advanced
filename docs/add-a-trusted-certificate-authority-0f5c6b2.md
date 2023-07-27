<!-- loio0f5c6b27744f4884a6ad5f360a1973f6 -->

# Add a Trusted Certificate Authority

If your organization uses unrecognized or self-signed certificates, add the certificate authority to the trusted certificate authorities of SAP Build Work Zone, advanced edition.

> ### Note:  
> Adding a trusted certificate authority disables the use of certificates in the default Certificate Authority store. Therefore, if you add a trusted certificate authority, you must manually add all required Certificate Authorities in this section of the *Administration Console*.

1.  Open a page of the external application in your browser and view the certificate. See your browser documentation for instructions.
2.  Export the certificate into **Base-64 encoded X.509 \(.cer\)** format.
3.  Open the exported certificate in a text editor and copy the entire certificate, including the Begin Certificate and End Certificate lines.
4.  Go to the SAP Build Work Zone, advanced edition *Administration Console* and select *External Integrations* \> *External Solutions*. Choose *Trusted Certificate Authorities* at the top of the *External Applications* page.
5.  Paste the copied certificate into the *Trusted Certificate Authorities* text box, and choose *Submit*.

    The unrecognized certificate is registered with SAP Build Work Zone, advanced edition, enabling your connection to your external application.


