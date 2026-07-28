<!-- loioda266508e0594a36a619b3eeeea849e9 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Using Security Headers

Improve the security of your sites by adding HTTP security headers to protect against clickjacking, cross-site scripting, XSS, and other attacks.



<a name="loioda266508e0594a36a619b3eeeea849e9__section_mbl_ljn_drb"/>

## Introduction

HTTP security headers provide an extra layer of security by restricting actions that the browser and server allow once your site is running. To protect the data, you can add one or more of the supported HTTP security headers.

Some security header values are already predefined by SAP. You can use browser developer tools to view these values.

> ### Note:  
> If you add a new security header or edit an existing one, note that by changing a value of a header you'll be overriding the predefined values.
> 
> For example, in the case of the `content-security-policy` header, you may want to add more values in addition to the predefined values. Rather than override the predefined values, you can use developer tools to copy the predefined values and add additional domains.
> 
> You can use a stricter value after validating that it covers `https://portal-service.cfapps.<your-datacenter>.hana.ondemand.com`.



<a name="loioda266508e0594a36a619b3eeeea849e9__section_i1t_nyx_nbc"/>

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

5.  Enter valid values for the headers.

    For more information, see [HTTP Headers.](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)

6.  Use the :heavy_plus_sign:to add additional headers.

7.  Click *Save*.




<a name="loioda266508e0594a36a619b3eeeea849e9__section_xzv_2xp_k1c"/>

## Supported security headers

The following table provides information about the supported security headers:


<table>
<tr>
<th valign="top">

Security Header

</th>
<th valign="top">

Supported?

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`Content-Security-Policy`

</td>
<td valign="top">

Yes, but not fully

</td>
<td valign="top">

To load a site safely, you have the option to define the `Content-Security-Policy` security header. This header includes a standardized set of directives that help reduce security risks by controlling which content sources can be trusted and which should be blocked.

This header is relevant only for SAP's out-of-the-box HTML pages loaded in a browser; either main frame or iFrame.

For other content sources, like CSS, JS files, or data requests, this header is ignored.

> ### Note:  
> Strict policies are currently not fully supported. A strict policy is a policy that doesn't use unsafe keywords such as `unsafe-eval` and `unsafe-inline` directives.



</td>
</tr>
<tr>
<td valign="top">

`Content-Security-Policy-Report-Only`

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Used to view security violations in your site.

Once the header is added, you can view all the errors in the console of your browser. The policy isn't enforced, but any violations are reported to a provided URI.

</td>
</tr>
<tr>
<td valign="top">

`Permissions-Policy`

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Allows web developers to selectively enable, disable, and modify the behavior of certain APIs and web features in the browser.

> ### Note:  
> Any browser settings that you may have defined in the Site Settings, will be overridden by the values in this security policy.



</td>
</tr>
<tr>
<td valign="top">

`Referrer-Policy`

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Controls how much referrer information \(sent via the `Referer` header\) should be included with requests.

</td>
</tr>
</table>

