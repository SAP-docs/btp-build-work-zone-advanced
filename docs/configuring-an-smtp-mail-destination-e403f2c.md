<!-- loioe403f2cdc66647239f00106db5f578c1 -->

# Configuring an SMTP Mail Destination

Configure an SMTP Mail destination for email notifications.



<a name="loioe403f2cdc66647239f00106db5f578c1__prereq_gx4_pnx_3zb"/>

## Prerequisites

> ### Note:  
> This option is only applicable to the SAP Notification service mechanism. If you are using the default notification mechanism, skip this procedure.

Make sure that your subaccount has a *Destination Administrator* role.



## Procedure

1.  Open the SAP BTP cockpit and select your subaccount.

2.  From the side navigation panel, go to *Destinations* \> *New Destination*.

3.  Configure the mail destination:

    1.  For an **Internet mail destination** with **BasicAuthentication** use the following properties:

        **Required and optional BTP destination properties with BasicAuthentication:**


        <table>
        <tr>
        <th valign="top">

        Field
        
        </th>
        <th valign="top">

        Value
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *Name*
        
        </td>
        <td valign="top">
        
        `SAP_Business_Notifications_Mail`
        
        </td>
        <td valign="top">
        
         
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Type*
        
        </td>
        <td valign="top">
        
        `MAIL`
        
        </td>
        <td valign="top">
        
         
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Proxy type*
        
        </td>
        <td valign="top">
        
        `Internet`
        
        </td>
        <td valign="top">
        
         
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Authentication*
        
        </td>
        <td valign="top">
        
        `BasicAuthentication`


        <table>
        <tr>
        <th valign="top">

        Property
        
        </th>
        <th valign="top">

        Value
        
        </th>
        <th valign="top">

        Details
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        User
        
        </td>
        <td valign="top">
        
        String
        
        </td>
        <td valign="top">
        
        Email address to use for authentication.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Password
        
        </td>
        <td valign="top">
        
        String
        
        </td>
        <td valign="top">
        
        Password to use for authentication.
        
        </td>
        </tr>
        </table>
        

        
        </td>
        <td valign="top">
        
         
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.from*
        
        </td>
        <td valign="top">
        
        String
        
        </td>
        <td valign="top">
        
        Sender Email address
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.host*
        
        </td>
        <td valign="top">
        
        String
        
        </td>
        <td valign="top">
        
        The SMTP server to connect to
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.port*
        
        </td>
        <td valign="top">
        
        Integer
        
        </td>
        <td valign="top">
        
        The SMTP server port to connect to
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.timeout* \(optional\)
        
        </td>
        <td valign="top">
        
        Integer
        
        </td>
        <td valign="top">
        
        The socket read timeout value in milliseconds. If not provided, the default value is set to 3000ms.

        Allowed values: 0-5000
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.connectiontimeout* \(optional\)
        
        </td>
        <td valign="top">
        
        Integer
        
        </td>
        <td valign="top">
        
        The socket connection timeout value in milliseconds. If not provided, the default value is set to 3000ms.

        Allowed values: 0-5000
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.writetimeout* \(optional\)
        
        </td>
        <td valign="top">
        
        Integer
        
        </td>
        <td valign="top">
        
        The socket write timeout value in milliseconds. If not provided, the default value is set to 3000ms.

        Allowed values: 0-5000
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.ssl.trust* \(optional\)
        
        </td>
        <td valign="top">
        
        space separated list of strings
        
        </td>
        <td valign="top">
        
        If not provided, the default value equals to '\*'.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.starttls.required* \(optional\)
        
        </td>
        <td valign="top">
        
        boolean
        
        </td>
        <td valign="top">
        
        If not provided, the default value is set to `true`.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.ssl.checkserveridentity* \(optional\)
        
        </td>
        <td valign="top">
        
        boolean
        
        </td>
        <td valign="top">
        
        If not provided, the default value is set to `true`.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.sender.name* \(optional\)
        
        </td>
        <td valign="top">
        
        String
        
        </td>
        <td valign="top">
        
        Allows you to explicitly set the email senders name.If left unspecified, the email from *mail.smtp.from* is used.
        
        </td>
        </tr>
        <tr>
        <td valign="top" align="center" colspan="3">
        
        **Non-modifiable by the end user configurations**
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *encoding*
        
        </td>
        <td valign="top">
        
        UTF-8
        
        </td>
        <td valign="top">
        
        \-
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.auth*
        
        </td>
        <td valign="top">
        
        true
        
        </td>
        <td valign="top">
        
        Attempt to authenticate the user using the `AUTH` command
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.starttls.enable*
        
        </td>
        <td valign="top">
        
        true
        
        </td>
        <td valign="top">
        
        Enables the use of the `STARTTLS` command \(if supported by the server\) to switch the connection to a TLS-protected connection before issuing any login commands. If the server does not support `STARTTLS`, the connection continues without the use of TLS.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.auth.mechanisms*
        
        </td>
        <td valign="top">
        
        The default is `LOGIN PLAIN DIGEST-MD5 NTLM` 
        
        </td>
        <td valign="top">
        
        The default value includes all the authentication mechanisms supported by the current implementation except `XOAUTH2`.
        
        </td>
        </tr>
        </table>
        
    2.  For an **Internet mail destination** with **OAuth Client Credentials Flow** use the following properties:

        **Required and optional BTP destination properties with OAuth Client Credentials Flow:**


        <table>
        <tr>
        <th valign="top">

        Property
        
        </th>
        <th valign="top">

        Value
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *Destination Name*
        
        </td>
        <td valign="top">
        
        `SAP_Business_Notifications_Mail`
        
        </td>
        <td valign="top">
        
         
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Type*
        
        </td>
        <td valign="top">
        
        `MAIL`
        
        </td>
        <td valign="top">
        
         
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Proxy Type*
        
        </td>
        <td valign="top">
        
        `Internet`
        
        </td>
        <td valign="top">
        
         
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Authentication*
        
        </td>
        <td valign="top">
        
        `OAuth2ClientCredentials`


        <table>
        <tr>
        <th valign="top">

        Property
        
        </th>
        <th valign="top">

        Value
        
        </th>
        <th valign="top">

        Details
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        `ClientId`
        
        </td>
        <td valign="top">
        
        String
        
        </td>
        <td valign="top">
        
        Client ID used to retrieve the access token.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `ClientSecret`
        
        </td>
        <td valign="top">
        
        String
        
        </td>
        <td valign="top">
        
        Client secret for the Client ID.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `TokenServiceURLType`
        
        </td>
        <td valign="top">
        
        String
        
        </td>
        <td valign="top">
        
        Either **Dedicated** \(if the `TokenServiceURL` serves only a single tenant\), or **Common** \(if the `TokenServiceURL` serves multiple tenants\).
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `TokenServiceURL`
        
        </td>
        <td valign="top">
        
        String
        
        </td>
        <td valign="top">
        
        URL of the token service, against which token retrieval is performed.
        
        </td>
        </tr>
        </table>
        

        
        </td>
        <td valign="top">
        
         
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.from*
        
        </td>
        <td valign="top">
        
        String
        
        </td>
        <td valign="top">
        
        Email address used for the `SMTP MAIL` command. This sets the envelope return address.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.host*
        
        </td>
        <td valign="top">
        
        String
        
        </td>
        <td valign="top">
        
        The SMTP server to connect to.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.port*
        
        </td>
        <td valign="top">
        
        int
        
        </td>
        <td valign="top">
        
        The SMTP server port to connect to.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.username*
        
        </td>
        <td valign="top">
        
        String
        
        </td>
        <td valign="top">
        
        Username to use for OAuth authentication.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.timeout* \(optional\)
        
        </td>
        <td valign="top">
        
        int
        
        </td>
        <td valign="top">
        
        Socket read timeout value in milliseconds. If not provided, defaults to 3000ms. Allowed values: min = 0; max = 5000.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.connectiontimeout* \(optional\)
        
        </td>
        <td valign="top">
        
        int
        
        </td>
        <td valign="top">
        
        Socket connection timeout value in milliseconds. If not provided, defaults to 3000ms. Allowed values: min = 0; max = 5000.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.writetimeout* \(optional\)
        
        </td>
        <td valign="top">
        
        int
        
        </td>
        <td valign="top">
        
        Socket write timeout value in milliseconds. If not provided, defaults to 3000ms. Allowed values: min = 0; max = 5000.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.ssl.trust* \(optional\)
        
        </td>
        <td valign="top">
        
        A comma-separated list of strings
        
        </td>
        <td valign="top">
        
        Defaults to '\*' if not provided. If a value is not provided, trust is based on the certificate provided by the server, which must be part of the SAP JVM default truststore.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.starttls.required* \(optional\)
        
        </td>
        <td valign="top">
        
        boolean
        
        </td>
        <td valign="top">
        
        Defaults to true if not provided. Requires the use of the `STARTTLS` command. If the server doesn't support the `STARTTLS` command, or the command fails, the connect method will fail.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.ssl.checkserveridentity* \(optional\)
        
        </td>
        <td valign="top">
        
        boolean
        
        </td>
        <td valign="top">
        
        Defaults to true if not provided. Checks the server identity as specified by RFC 2595.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.sender.name* \(optional\)
        
        </td>
        <td valign="top">
        
        String
        
        </td>
        <td valign="top">
        
        Allows you to explicitly set the sender's name for the email, but if left unspecified, it gracefully falls back to using the sender information specified in `mail.smtp.from` for the email sender name.
        
        </td>
        </tr>
        <tr>
        <td valign="top" align="center" colspan="3">
        
        **Non-modifiable by the end user configurations:**
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *encoding*
        
        </td>
        <td valign="top">
        
        UTF-8
        
        </td>
        <td valign="top">
        
        \-
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.auth*
        
        </td>
        <td valign="top">
        
        true
        
        </td>
        <td valign="top">
        
        Attempt to authenticate the user using the `AUTH` command.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.starttls.enable*
        
        </td>
        <td valign="top">
        
        true
        
        </td>
        <td valign="top">
        
        Enables the use of the `STARTTLS` command \(if supported by the server\) to switch the connection to a TLS-protected connection before issuing any login commands. If the server does not support `STARTTLS`, the connection continues without the use of TLS.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.auth.mechanisms*
        
        </td>
        <td valign="top">
        
        The default is `XOAUTH2`
        
        </td>
        <td valign="top">
        
        The default value for a destination with OAuth2ClientCredentials authentication is `XOAUTH2`.
        
        </td>
        </tr>
        </table>
        
        > ### Note:  
        > Make sure that the destination specified with the type `MAIL` is publicly visible on the Internet. If the destination is situated behind a proxy or a host that restricts external IPs, it should permit either all incoming traffic or define specific IP ranges from which notifications originate. In the current context, these IP ranges pertain to the notification service. For the relevant IP ranges associated with the SAP BTP Cloud Foundry environment across different landscapes, see column *NAT IPs \(egress, IPs for requests from a Cloud Foundry app\) in* [Regions and API Endpoints Available for the Cloud Foundry Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/regions-and-api-endpoints-available-for-cloud-foundry-environment).
        > 
        > Additionally, you must be aware of what the landscape of the notification service that your application is consuming is. Make sure that the IP ranges that you are going to add to the allowlist in the host align with the ones that the notification service would use when making calls to the customer's application. This will ensure proper configuration and seamless communication for effective email processing.

    3.  For an **On-Premise mail destination** use the following properties:

        **Required and optional BTP destination properties with BasicAuthentication:**


        <table>
        <tr>
        <th valign="top">

        Property
        
        </th>
        <th valign="top">

        Value
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *Name*
        
        </td>
        <td valign="top">
        
        `SAP_Business_Notifications_Mail`
        
        </td>
        <td valign="top">
        
         
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Type*
        
        </td>
        <td valign="top">
        
        `MAIL`
        
        </td>
        <td valign="top">
        
         
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Proxy type*
        
        </td>
        <td valign="top">
        
        `On-Premise`
        
        </td>
        <td valign="top">
        
         
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Authentication*
        
        </td>
        <td valign="top">
        
        `BasicAuthentication`
        
        </td>
        <td valign="top">
        
         
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.from*
        
        </td>
        <td valign="top">
        
        String
        
        </td>
        <td valign="top">
        
        Sender Email address
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.host*
        
        </td>
        <td valign="top">
        
        String
        
        </td>
        <td valign="top">
        
        The SMTP server to connect to. For an On-Premise destination, said host refers to the virtual host registered within the SAP Cloud Connector associated with the particular system.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.port*
        
        </td>
        <td valign="top">
        
        Integer
        
        </td>
        <td valign="top">
        
        The SMTP server port to connect to. For an On-Premise destination, said port refers to the port of the virtual host registered within the SAP Cloud Connector associated with the particular system.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *LocationId* \(optional\)
        
        </td>
        <td valign="top">
        
        String
        
        </td>
        <td valign="top">
        
        The field conveys information about the `LocationId` of the SAP Cloud Connector registered in the subaccount. If this `LocationId` is not provided, the system will default to using any available Cloud Connector. However, if there are several Cloud Connectors affiliated with your subaccount, please make sure to provide the `LocationId`. Doing so will assists you in ensuring a consistent performance by allowing the system to accurately select the correct Connector.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.timeout* \(optional\)
        
        </td>
        <td valign="top">
        
        Integer
        
        </td>
        <td valign="top">
        
        The socket read timeout value in milliseconds. If not provided, the default value is set to 3000ms.

        Allowed values: 0-10000
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.connectiontimeout* \(optional\)
        
        </td>
        <td valign="top">
        
        Integer
        
        </td>
        <td valign="top">
        
        The socket connection timeout value in milliseconds. If not provided, the default value is set to 3000ms.

        Allowed values: 0-10000
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.writetimeout* \(optional\)
        
        </td>
        <td valign="top">
        
        Integer
        
        </td>
        <td valign="top">
        
        The socket write timeout value in milliseconds. If not provided, the default value is set to 3000ms.

        Allowed values: 0-10000
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.starttls.required* \(optional\)
        
        </td>
        <td valign="top">
        
        Boolean
        
        </td>
        <td valign="top">
        
        Indicates whether the server should always use the `STARTTLS` command when connecting to a server. If not provided, the default value is set to `true` \(e.g. Always use `STARTTLS` to start the connection\). If your SMTP server doesn't support `STARTTLS`, this property should be set to `false`.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.sender.name* \(optional\)
        
        </td>
        <td valign="top">
        
        String
        
        </td>
        <td valign="top">
        
        Allows you to explicitly set the email sender's name. If left unspecified, the email from *mail.smtp.from* is used.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.ssl.trust* \(optional\)
        
        </td>
        <td valign="top">
        
        String
        
        </td>
        <td valign="top">
        
        **Specification:** Hosts are specified using a comma-separated list.

        **Purpose:** These hosts are used to validate the certificate chain provided by the client SMTP server when a connection is made.

        **Validation Criteria:** The validation checks if the host exists within the subject name and subject alternative names of the certificates within the chain.

        **Default Value:** If not provided, the default value is \*, which utilizes the hosts from the SAP JVM default trust store certificates.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *mail.smtp.ssl.checkserveridentity* \(optional\)
        
        </td>
        <td valign="top">
        
        Boolean
        
        </td>
        <td valign="top">
        
        Defaults to true if not provided. Checks the server identity as specified by RFC 2595 using the hosts from *mail.smtp.ssl.trust* property.
        
        </td>
        </tr>
        </table>
        
        > ### Note:  
        > When configuring a mail destination keep in mind the following:
        > 
        > -   The *mail.smtp.timeout*, *mail.smtp.connectiontimeout*, *mail.smtp.writetimeout* properties, should be set to higher values than the default, as the proxy adds an additional layer of communication, thus it slows down the communication between the Notification service and the actual SMTP.
        > 
        > -   The *mail.smtp.starttls.required*, should be adjusted accordingly to your SMTP server configuration and communication host/port. Within SMTP servers it is common for the same host to have multiple ports, on which `STARTTLS` could be either enabled or disabled.
        > 
        > -   The *mail.smtp.ssl.trust* and *mail.smtp.ssl.checkserveridentity* properties need to be configured accordingly when the connection is supposed to use TLS and the certificates which your SMTP server uses are either self-signed or are not issued from a trusted authority.

        > ### Note:  
        > When configuring an On-Premise system that has to be accessed through the SAP Cloud Connector, the following should be kept in mind:
        > 
        > -   In order to add a subaccount to your Cloud Connector instance the following documentation could be followed [Managing Subaccounts](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/managing-subaccounts).
        > 
        > -   In order to register your SMTP server you should navigate to your **Subaccount**. For more information, refer to the [Configure Access Control \(TCP\)](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/configure-access-control-tcp) documentation.
        > 
        > -   The destination should be used with `Back-end type: Non-SAP System` and `Protocol: TCP/TCP over SSL (If the host has SSL validation)`.
        > 
        > -   When using a proxy, the internal host/port is responsible for addresses that can be accessed with the host on which the Cloud Connector is hosted on. The virtual host/port is used for routing of the connectivity proxy.
        > 
        > -   If your communication is based on Self-Signed certificates, or certificates that are not trusted by the Cloud Connector, the following procedure should be followed [Configure Trust](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/configure-trust).
        > 
        > 
        > If everything is set-up correctly, the check on the internal host should be successful. \(e.g. the status of the system should be **Reachable**.\)



