<!-- loioda266508e0594a36a619b3eeeea849e9 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Using Security Headers

Improve the security of your sites by adding HTTP security headers to protect against clickjacking, cross-site scripting, XSS, and other attacks.



<a name="loioda266508e0594a36a619b3eeeea849e9__section_mbl_ljn_drb"/>

## Introduction

HTTP security headers provide an extra layer of security by restricting actions that the browser and server allow once your site is running. To protect the data, you can add one or more of the supported HTTP security headers.

> ### Note:  
> If you add a new security header or edit an existing one, note that by changing a value of a header you'll be overriding the predefined values.
> 
> For example, in the case of the `content-security-policy` header, you may want to add more values in addition to the predefined values. Rather than override the predefined values, you can use developer tools to copy the predefined values and add additional domains.
> 
> **Important**: We recommend that you constantly review and test the effect of each configured header separately to check for any changes provided by SAP. We also strongly suggest that you add `https://*.hana.ondemand.com` to the `connect-src` attribute of the CSP header.
> 
> You can use a stricter value after validating that it covers `https://portal-service.cfapps.<your-datacenter>.hana.ondemand.com`.



<a name="loioda266508e0594a36a619b3eeeea849e9__section_ksw_qkn_drb"/>

## How to configure the security headers

You can add security headers to your site from your subaccount settings as follows:

1.  From the Site Manager, click :gear: to open the subaccount settings screen.

2.  Click the *Security Headers* tab.

3.  Click *Edit* on the right side of the screen.

4.  Select a security header from the dropdown list in the dialog box.

    > ### Note:  
    > The security headers that are available for selection are:
    > 
    > -   `content-security-policy`
    > 
    > -   `content-security-policy-report-only`
    > 
    > -   `referrer-policy`
    > 
    > -   `permissions-policy`
    > 
    >     > ### Note:  
    >     > If you use the `permissions-policy`, any browser settings that you may have defined in your *Site Settings*, will be overridden by the values provided in this security policy. For example, in the Site Settings, I can enable *Browser Feature Access*, meaning that apps can use features such as the camera. However, if I set the permission of the header that the camera **can't** run, the camera won't be able to run in the browser.
    > 
    > 
    > For more information about these security headers, see [Security](https://help.sap.com/viewer/ad4b9f0b14b0458cad9bd27bf435637d/Cloud/en-US/d7b1a89c9a0f46bd9b1e2b6ca70add66.html) .

5.  Enter valid values for the headers.

    For more information, see [HTTP Headers.](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)

6.  Use the :heavy_plus_sign:to add additional headers.

7.  Click *Save*.


