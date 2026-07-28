<!-- loio0176e2975d5a464c88c3c042a31e59e7 -->

# Using the Common Super Domain

SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone, support the `cloud.sap` common super domain.



To reduce the likelihood of issues related to third-party cookie handling and browser cross-domain restrictions for integration scenarios across systems, SAP recommends exposing SAP Build Work Zone, SAP Cloud Identity Services \(IAS\), and integrated backend systems under a common super domain whenever possible. A common super domain can be achieved either through SAP-provided Common Super Domain or using custom domains.

The following are the the domains that you can use instead of using the default domain. It works both on a desktop and on a mobile device:


<table>
<tr>
<th valign="top">

Product

</th>
<th valign="top">

Domain Name

</th>
</tr>
<tr>
<td valign="top">

SAP Build Work Zone, advanced edition 

</td>
<td valign="top">

<subdomain\>.<DC\>.**workzone-advanced.cloud.sap** 

</td>
</tr>
<tr>
<td valign="top">

SAP SuccessFactors Work Zone 

</td>
<td valign="top">

<subdomain\>.<DC\>.**workzone-hr.cloud.sap** 

</td>
</tr>
<tr>
<td valign="top">

SAP Build Work Zone, advanced edition 

</td>
<td valign="top">

<subdomain\>.<DC\>. **workzone-advanced.sapcloud.cn** 

</td>
</tr>
<tr>
<td valign="top">

SAP SuccessFactors Work Zone 

</td>
<td valign="top">

<subdomain.\><DC\>.**workzone-hr.sapcloud.cn** 

</td>
</tr>
</table>

To switch from the default domain \(ondemand.com\), to the common super domain \(cloud.sap\), simply go to the *Administration Console*, and in the *Overview* section, select the common super domain option.

After switching domains, the following happens:

-   The DWS URL and and the site runtime URL will be updated accordingly in the *Overview* screen - this applies to both the `ondemand.com` and the `cloud.sap` domains.

-   Email notifications will be updated according to the selected domain type. Only the selected domain can be used for email notifications.


**Examples:**

-   For SAP Build Work Zone, advanced edition: **<code>https://&lt;subdomain&gt;.&lt;DC&gt;.<b>hana.ondemand.com</b>/site?siteId=&lt;alias&gt;#workzone-home</code>** will change to **<code>https://&lt;subdomain&gt;.&lt;DC&gt;.<b>workzone-advanced.cloud.sap</b>/site?siteId=&lt;alias&gt;#workzone-home</code>**

-   For SAP SuccessFactors Work Zone: **<code>https://&lt;subdomain&gt;.&lt;DC&gt;.<b>hana.ondemand.com</b>/site?siteId=&lt;alias&gt;#workzone-home</code>** will change to **<code>https://&lt;subdomain&gt;.&lt;DC&gt;.<b>workzone-hr.cloud.sap</b>/site?siteId=&lt;alias&gt;#workzone-home</code>**
-   For SAP Build Work Zone, advanced edition: **`https://<subdomain>.workzone.portal.cn40.apps.platform.sapcloud.cn/site?siteId=<alias>#workzone-home`** will change to **`https://<subdomain>.<DC>.workzone-advanced.sapcloud.cn/site?siteId=<alias>#workzone-home`**
-   For SAP SuccessFactors Work Zone: **`https://<subdomain>.workzonehr.portal.cn40.apps.platform.sapcloud.cn/site?siteId=<alias>#workzone-home`** will change to **`https://<subdomain>.<DC>.workzone-hr.sapcloud.cn/site?siteId=<alias>#workzone-home`**

The domain configured for Identity Authentication must be identical to the domain you're using inSAP Build Work Zone, advanced edition or SAP SuccessFactors Work Zone.



<a name="loio0176e2975d5a464c88c3c042a31e59e7__section_ohd_ymb_hdc"/>

## What you should know

-   At runtime, if you decide to work with the common super domain, make sure that you update links, adjust the default browser start page, and more - regardless of which domain you are changing over to. Also make sure that all your integrated applications support this domain.

-   When creating a subscription to SAP Build Work Zone, advanced edition or to SAP SuccessFactors Work Zone in the SAP BTP cockpit, the URL will automatically point to the default domain. This default domain can't be changed, but will not cause any issue with the common super domain.


