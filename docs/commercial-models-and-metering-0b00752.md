<!-- loio0b00752b4dec4752bece9d99f0168520 -->

# Commercial Models and Metering

Information about the commercial models for licensing SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone, about the metrics used to monitor and charge usage, and about monitoring.



<a name="loio0b00752b4dec4752bece9d99f0168520__section_c12_zjx_hgb"/>

## Commercial Models

The following commercial models are supported:


<table>
<tr>
<th valign="top">

Product



</th>
<th valign="top">

Commercial Model



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

SAP Build Work Zone, advanced edition 



</td>
<td valign="top">

Consumption-based



</td>
<td valign="top">

You are entitled to activate SAP Build Work Zone, advanced edition.

You prepay for cloud credits, which are then balanced against the consumption of SAP Build Work Zone, advanced edition.



</td>
</tr>
<tr>
<td valign="top">

SAP SuccessFactors Work Zone 



</td>
<td valign="top">

Subscription-based



</td>
<td valign="top">

You are entitled to use SAP SuccessFactors Work Zone.

You prepay a fixed price for the duration of the subscription period, according to the number of licenses that you purchase.



</td>
</tr>
</table>



<a name="loio0b00752b4dec4752bece9d99f0168520__section_fzq_gqd_kgb"/>

## Metrics

For SAP Build Work Zone, advanced edition, the following metrics are used to monitor and charge usage:


<table>
<tr>
<th valign="top">

Metric



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

**Active Users**



</td>
<td valign="top">

An 'active user' is an authenticated, internal, and unique individual who accessed SAP Build Work Zone, advanced edition at any time during a calendar month.

> ### Note:  
> For SAP SuccessFactors Work Zone, the **Users** metric is used.



</td>
</tr>
<tr>
<td valign="top">

**Connections**



</td>
<td valign="top">

A 'connection' is an individual user session to a customer’s site. Within a single connection the user can browse an unlimited number of pages belonging to that site.

A user's 'connection' \(session\) is active until one of the following occurs:

-   The user logs off from the site.

-   The user closes the web browser.

-   The 'connection' \(session\) times out due to user inactivity. The timeout duration is 15 minutes by default and can be configured to a maximum of 30 minutes. For more information, see [Site Settings](site-settings-e2bfc3d.md)




</td>
</tr>
</table>

> ### Note:  
> Make sure that every authenticated user who is external to your organization is assigned to the `Workzone_User_Type_public` Identity Authentication user group that corresponds to the `Workzone_External_User` role collection on SAP BTP. For more information, see [Prerequisites](prerequisites-9e78b62.md) and [About Roles and Role Assignment](about-roles-and-role-assignment-f38de6b.md).
> 
> The metrics are metered separately, depending on the user’s role assignment. An Active User \(or User\) is reported unless the user is assigned to the external role and then a Connection is reported.



<a name="loio0b00752b4dec4752bece9d99f0168520__section_jwy_m5n_lgb"/>

## Monitoring

Usage monitoring is done via the SAP BTP cockpit.

For more information, see [Monitoring Usage and Consumption Costs](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/de6f0db8919f4e6f97e54bc4ddaf2ab8.html).



<a name="loio0b00752b4dec4752bece9d99f0168520__section_mfn_1cv_pmb"/>

## Included Services - SAP Build Work Zone, advanced edition

The SAP Build Work Zone, advanced edition license includes the following services:


<table>
<tr>
<th valign="top">

Services



</th>
</tr>
<tr>
<td valign="top">

SAP Build Work Zone, advanced edition 



</td>
</tr>
<tr>
<td valign="top">

UI theme designer

For more information, see [UI theme designer](https://help.sap.com/viewer/product/UI_THEME_DESIGNER/Cloud/en-US).



</td>
</tr>
<tr>
<td valign="top">

HTML5 Applications managed by SAP

For more information, see [Developing HTML5 Applications and Extensions](https://help.sap.com/docs/WZ_STD/8c8e1958338140699bd4811b37b82ece/c1b9d6facfc942e3bca664ae06387e9b.html).



</td>
</tr>
<tr>
<td valign="top">

SAP Mobile Services \(runtime\)

For more information, see [SAP Mobile Services Documentation](https://help.sap.com/doc/f53c64b93e5140918d676b927a3cd65b/Cloud/en-US/docs-en/index.html).



</td>
</tr>
<tr>
<td valign="top">

SAP Cloud Identity Services:

-   Identity Authentication service \(IAS\).

    For more information, see [SAP Cloud Identity Services - Identity Authentication](https://help.sap.com/docs/IDENTITY_AUTHENTICATION).

-   Identity Provisioning service \(IPS\).

    For more information, see [SAP Cloud Identity Services - Identity Provisioning](https://help.sap.com/docs/IDENTITY_PROVISIONING).




</td>
</tr>
</table>

> ### Note:  
> These services are restricted to authenticated users.



<a name="loio0b00752b4dec4752bece9d99f0168520__section_lbc_4dy_2wb"/>

## Included Services - SAP SuccessFactors Work Zone

The SAP SuccessFactors Work Zone license includes the following services:


<table>
<tr>
<th valign="top">

Services



</th>
</tr>
<tr>
<td valign="top">

SAP SuccessFactors Work Zone 



</td>
</tr>
<tr>
<td valign="top">

UI theme designer

For more information, see [UI theme designer](https://help.sap.com/viewer/product/UI_THEME_DESIGNER/Cloud/en-US).



</td>
</tr>
<tr>
<td valign="top">

HTML5 Applications managed by SAP

For more information, see [Developing HTML5 Applications and Extensions](https://help.sap.com/docs/WZ_STD/8c8e1958338140699bd4811b37b82ece/c1b9d6facfc942e3bca664ae06387e9b.html).



</td>
</tr>
<tr>
<td valign="top">

SAP Mobile Services \(runtime\)

For more information, see [SAP Mobile Services Documentation](https://help.sap.com/doc/f53c64b93e5140918d676b927a3cd65b/Cloud/en-US/docs-en/index.html).



</td>
</tr>
<tr>
<td valign="top">

SAP Cloud Identity Services:

-   Identity Authentication service \(IAS\).

    For more information, see [SAP Cloud Identity Services - Identity Authentication](https://help.sap.com/docs/IDENTITY_AUTHENTICATION).

-   Identity Provisioning service \(IPS\).

    For more information, see [SAP Cloud Identity Services - Identity Provisioning](https://help.sap.com/docs/IDENTITY_PROVISIONING).




</td>
</tr>
<tr>
<td valign="top">

A license bundle of the following SAP BTP services, with a limited number of users:

-   SAP Business Application Studio

-   SAP Build Process Automation

-   SAP Custom Domain




</td>
</tr>
</table>

> ### Note:  
> These services are restricted to authenticated users.

**Related Information**  


[SAP Business Technology Platform Service Description Guide and Agreement](https://www.sap.com/about/agreements/policies/cloud-platform.html)

