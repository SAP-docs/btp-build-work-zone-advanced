<!-- loio97a7ee5b10b3488e872ca84131c8c0ef -->

# Overview of Custom Domains

Using the SAP Custom Domain service, administrators can configure a custom domain for exposing a site instead of using the default domain.



<a name="loio97a7ee5b10b3488e872ca84131c8c0ef__section_wzx_yqd_qwb"/>

## What is a Custom Domain?

Instead of using the default domain that is assigned to your subaccount, you can purchase a custom domain with a unique name that is easily recognizable by your users, making them more secure about accessing your site.

For example, if your default domain is `subaccount.workzone.cfapps.eu10.hana.ondemand.com` or`subaccount.workzonehr.cfapps.eu10.hana.ondemand.com`, you can purchase the domain `mycompany.com`, create a custom domain `sales.mycompany.com`, and securely expose your site under this custom domain.

For example, if your default subaccount is `subaccount.workzone.portal.cn40.apps.platform.sapcloud.cn` or `subaccount.workzonehr.portal.cn40.apps.platform.sapcloud.cn`, you can purchase the domain `mycompany.com`, create a custom domain `sales.mycompany.com`, and securely expose your site under this custom domain.

Using the same domain for a site as well as for all the embedded content including Identity Authentication, enables broader integration scenarios, by avoiding third-party cookies with the respective security drawbacks.

> ### Note:  
> If you decide to use a custom domain, make sure that you update links and inform end users to update their bookmarks. If users want to still use the default `ondemand.com` domain, the URL will not be redirected.



To set up your custom domain, refer to this topic: [Set Up a Custom Domain](set-up-a-custom-domain-50bcb51.md)

> ### Note:  
> After completing the setup, you must rerun the onboarding configurator and use your custom domain instead of the default domain. Using a non-custom domain such as `ondemand.com` is not supported once you've already configured a custom domain. For more information, see [Rerunning the Configurator](rerunning-the-configurator-872b96a.md).



To set up your custom domain, refer to this topic: [Set up a Custom Domain - SAP Authentication and Trust Management \(XSUAA\)](set-up-a-custom-domain-sap-authentication-and-trust-management-xsuaa-ae475bf.md).



<a name="loio97a7ee5b10b3488e872ca84131c8c0ef__section_qyn_25j_nbc"/>

## Third-Party Cookie Deprecation

Sites that are using a full custom domain might be affected by the third party cookies deprecation on Chrome and Edge browsers.

To avoid this situation, customers can apply to participate in the first-party deprecation trial, and request Google to issue them a token that will temporarily re-enable third-party cookies until December 27th, 2024.

For more information, see [Third Party Cookies Deprecation](third-party-cookies-deprecation-4ee0fce.md).

