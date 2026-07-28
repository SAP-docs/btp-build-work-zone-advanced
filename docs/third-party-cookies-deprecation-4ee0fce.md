<!-- loio4ee0fcef7bca410895b040715a8821f6 -->

# Third Party Cookies Deprecation

Actions for site administrators required due to the third party cookies deprecation on Chrome and Edge browsers.



## Overview

Browser manufacturers are ending support for third-party cookies. Starting in April 1st 2024, users might face issues with their web applications when running in Chrome due to Chrome's third-party cookie deprecation. Microsoft Edge is built on Chromium and therefore expected to follow the Chrome approach shortly after.

Third-party cookies are used for tracking, advertising, session management, SSO, and personalization. At SAP, they are used for session management and Single Sign-On \(SSO\). SAP Build Work Zone, advanced edition serves as a central entry point and can embed different applications \(from potentially different domains\) side-by-side in an iFrame. This architecture relies on third-party cookies.

**Who is not affected by this change?** 

-   Sites that render content running on SAP-managed domains such as `ondemand.com` or `cloud.sap``sapcloud.cn`.

    > ### Note:  
    > Sites that render content on SAP-managed domains but are integrated into a custom SAP Build Work Zone, advanced edition instance or in other SAP products that are using other domains can be affected.

-   Sites that integrate content from SAP BTP content providers.

**Who might be affected by this change?**

-   Sites that are using a full custom domain.
-   Sites that integrate content from remote content providers that are using a non-SAP domain or that manually integrated content that runs on a non-SAP domain. Hint: [Security Guidelines for Content Providers](security-guidelines-for-content-providers-37ea9ee.md).
-   Sites that integrate solutions that are using a local approuter \(such as launchpad modules\).



<a name="loio4ee0fcef7bca410895b040715a8821f6__section_rjq_2f2_cbc"/>

## Short-Term Solution \(Until December 2024\)

To allow applications more time to adjust to the third party cookies deprecation, customers can apply to participate in the first-party deprecation trial, and request Google to issue them a token that will temporarily re-enable third-party cookies until December 27th, 2024.

For more information, see [Request more time to prepare with the third-party cookie deprecation trial for top-level sites](https://developers.google.com/privacy-sandbox/3pcd/temporary-exceptions/first-party-deprecation-trial).

When you have the token details, provide them to SAP by opening a support ticket on component EP-WZ-DMN.



<a name="loio4ee0fcef7bca410895b040715a8821f6__section_j5y_gf2_cbc"/>

## Long-Term Solution

The long term solution must be implemented by the end of December 2024 and should be based on *Cookies Having Independent Partitioned State* \(CHIPS, also known as Partitioned cookies\). CHIPS allows developers to opt a cookie into partitioned storage, with a separate cookie jar per top-level site. Doing so will allow cookies to be set by third-party services, but only read within the context of the top-level site where they were initially set. For more information, see [CHIPS](https://developer.mozilla.org/en-US/docs/Web/Privacy/Privacy_sandbox/Partitioned_cookies).



<a name="loio4ee0fcef7bca410895b040715a8821f6__section_y5x_m3x_r2c"/>

## Applications with Local Approuter

Providers of solutions \(such as launchpad modules\) that are using a local approuter, which is not managed by SAP, must handle the cookies in advance, to make sure their solution will not be blocked when running in an iframe.

The cookies are configured as an environment variable of the approuter. For more information, see [Environment Variables](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/ba527058dc4d423a9e0a69ecc67f4593.html).



<a name="loio4ee0fcef7bca410895b040715a8821f6__section_xqv_rbg_cbc"/>

## Related Blogs and Guides


<table>
<tr>
<th valign="top">

Recommended Approach

</th>
<th valign="top">

Blog Post

</th>
<th valign="top">

How-to Guide/Documentation

</th>
</tr>
<tr>
<td valign="top">

Check if the solution is affected

</td>
<td valign="top">

[Are You Affected by the Third-Party Cookie Deprecation?](https://community.sap.com/t5/technology-blogs-by-sap/sap-btp-and-third-party-cookies-deprecation/ba-p/13665375)

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Test for breakage

</td>
<td valign="top">

[How to Test Your Solution for Breakage](https://community.sap.com/t5/technology-blogs-by-sap/how-to-test-your-solution-for-breakage/ba-p/13709290)

</td>
<td valign="top">

[Preparing and Testing Your Solution for Third-Party Cookie Deprecation](https://help.sap.com/docs/btp/preparing-and-testing-your-solution-for-third-party-cookie-deprecation/what-is-purpose-of-this-document)

</td>
</tr>
<tr>
<td valign="top">

Apply temporary work-around \(optional\)

</td>
<td valign="top">

[Getting and Applying a Deprecation Trial Token for the Third-Party Cookie Deprecation](https://community.sap.com/t5/technology-blogs-by-sap/getting-and-applying-a-deprecation-trial-token-for-the-third-party-cookie/ba-p/13724225)

</td>
<td valign="top">

[Getting and Applying a Deprecation Trial Token for the Third-Party Cookie Deprecation](https://help.sap.com/docs/BTP/d574d80a71444a0a92ac74e58a6da3c0/bbbcae216c3149869126b5929ae53001.html)

</td>
</tr>
<tr>
<td valign="top">

Apply permanent solution

</td>
<td valign="top">

[How to Prepare Your Application for the Blockage of Third-Party Cookies.](https://community.sap.com/t5/technology-blogs-by-sap/how-to-prepare-your-application-for-the-blockage-of-third-party-cookies/ba-p/13733311)

</td>
<td valign="top">

[Implementing a Permanent Solution for the Third-Party Cookie Deprecation](https://help.sap.com/docs/BTP/555a605e60a04f1d92df1e64ab38cdfc/0ccd3faf742540f1a120b1befdb27381.html)

</td>
</tr>
<tr>
<td valign="top">

FAQ

</td>
<td valign="top">

 

</td>
<td valign="top">

[Frequently Asked Questions - Third-Party Cookie Deprecation](https://help.sap.com/docs/BTP/89a39acf7e8f47df8d59f4d5994f56df/a4e5cf0d4b654a31b0e298ccc0d6a94d.html)

</td>
</tr>
</table>



<a name="loio4ee0fcef7bca410895b040715a8821f6__section_wjp_1sw_tbc"/>

## Additional Information

SAP note: [3409306](https://me.sap.com/notes/3409306).

