<!-- loio102e32c8f84842bfa7fa02740cf3718e -->

# HTML5 Business Solutions as Content Providers

Integrated HTML5 business solutions can be consumed across subaccounts in the same tenant or across different tenants.



<a name="loio102e32c8f84842bfa7fa02740cf3718e__section_m2c_zfd_ncc"/>

## Overview

This scenario enables providers of HTML5 business solutions \(SaaS\) to share their business solutions with their consumers. Consumers can access the business solution through destinations \(if they are on the same tenant\) or through a subscription. Once the business solution is added as a content provider on the consumers subaccounts, consumers can access the business solution through their Channel Manager and choose which content they would like to add to their sites . If the business solution contains also a site entity, consumers can access the site directly from their Site Directory. Consumers can also integrate the business solution content side by side with local and federated content from other content providers.

Any updates made by the business solution provider are automatically reflected in the site.

To use this scenario, both the provider and consumer must have a subscription to SAP Build Work Zone, advanced edition.





## Consumption Options


<table>
<tr>
<th valign="top">

 

</th>
<th valign="top">

Details

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

Single-tenant consumption via destinations

</td>
<td valign="top">

This flow enables consumption of business solutions across subaccounts that belong to the same tenant. The business solution provider creates an app and deploys it to its subaccount. Then, the consumer creates destinations that point to the provider subaccount and runs the business solution remotely, on the provider subaccount.

It is important to note that this flow is supported only when both the provider and the consumer are using the same Identity Authentication tenant, to avoid security issues.

</td>
<td valign="top">

[Single-Tenant Business Solution](single-tenant-business-solution-c4fb037.md)

</td>
</tr>
<tr>
<td valign="top">

Multitenancy consumption via subscription

</td>
<td valign="top">

This flow enables consumption of the business solutions across subaccounts that belong to different tenants. The business solution provider creates a multitenant app and deploys it to its subaccount. Upon deployment, the business solution app becomes available for subscription in the Service Marketplace of the SAP BTP cockpit. The consumer can then subscribe to the business solution app and consume it on its own subdomain.

The subscription option is also available when the subaccounts belong to the same tenant. It's up to the administrator to decide whether to consume the business solution through a subscription or through reusing the destination details.

</td>
<td valign="top">

[Multi-tenant Business Solution](multi-tenant-business-solution-f8a4a63.md)

</td>
</tr>
</table>

