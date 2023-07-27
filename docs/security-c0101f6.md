<!-- loioc0101f63988f4624870d77fb02d2fefe -->

# Security

On the *Compliance & Security* \> *Security* screen, you configure security options that specifically apply to SAP Build Work Zone, advanced edition.




<table>
<tr>
<th valign="top">

Task



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

Set browser authentication by email



</td>
<td valign="top">

Select *Require email authentication for new browsers* to decrease the possibility of someone gaining access to a user's account without access to their email account.

If enabled, users are sent an email validation each time they log on from a browser or computer that they haven't used before.



</td>
</tr>
<tr>
<td valign="top">

Configure email settings



</td>
<td valign="top">

-   Select or deselect *Allows users to create content and respond to activities via e-mail*.
-   Select or deselect *Allows sending automated email notifications to users*.

    Even if this option is disabled, the system still sends emails for workspace invites and warning emails to company administrators regarding their external user limit, as with disk storage usage.




</td>
</tr>
<tr>
<td valign="top">

Restrict IP addresses from where the users can log on



</td>
<td valign="top">

1.  In the *IP Restrictions* section, choose *Only these IP addresses*.

    Users can log on from only the internet protocol \(IP\) addresses that you configure, for example, only within your organization's network.

    > ### Note:  
    > Limiting access to *Only these IP addresses* doesn’t exclude usage of any of the external features, such as external workspaces or inviting external users to a workspace.

2.  In the *IP Restriction* column, enter an outgoing IP address \(IPv4\) or IP address range \(CIDR\) for your organization.
3.  Choose *Add a new IP Address* to add an additional address or address range.



</td>
</tr>
<tr>
<td valign="top">

Display a warning message when navigating to an external domain



</td>
<td valign="top">

Navigating outside the organization’s domain may cause a security risk. When selecting this option, a warning message will be displayed when trying to open an external link.

To avoid this warning message from being displayed when navigating to a trusted domain, add your trusted domains to the internal domains list.

> ### Note:  
> Add a comma between the names.



</td>
</tr>
</table>

