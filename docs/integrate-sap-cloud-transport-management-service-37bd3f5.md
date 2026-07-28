<!-- loio37bd3f5c677a49c4a778ada12ee35ef0 -->

# Integrate SAP Cloud Transport Management Service

The steps required to integrate the SAP Cloud Transport Management service so that it can be used to transport content between subaccounts, which may even reside on different environments or data centers.



<a name="loio37bd3f5c677a49c4a778ada12ee35ef0__section_tdz_d32_1rb"/>

## Overview

You use the SAP Cloud Transport Management service to transport content between a source subaccount, where the content currently resides, and a target subaccount, where you would like the content to reside as well. For example, you may need to transport content from a DEV subaccount first to a QA subaccount and later to a PROD subaccount.

> ### Note:  
> To facilitate role management and allow strict access control, we recommend running SAP Cloud Transport Management as a shared service, by setting it up on a central administrative subaccount. For more information, see the *Transport Management* section in the [Delivering Applications](https://help.sap.com/docs/btp/best-practices/delivering-applications?version=Cloud&q=%22administrative%20subaccount%22) topic of the *Best Practices for SAP BTP* guide.

To learn more about SAP Cloud Transport Management service, see [What Is Cloud Transport Management](https://help.sap.com/viewer/7f7160ec0d8546c6b3eab72fb5ad6fd8/Cloud/en-US/5fef9d6b1cb047b2b18d9eb57aa15352.html).



## Procedure

In the SAP BTP cockpit:

1.  Repeat the following steps for every subaccount that provides a transport target, such as DEV, TST, and PRD:

    1.  In the target subaccount, go to the *Instances and Subscriptions* screen and create a subscription and a service instance \(you must have a space in your subaccount to be able to do this\) to the SAP Build Work Zone, advanced edition. The subscription is made to the `standard(Application)` plan, and the instance is created for the `standard` plan.

        A subscription to SAP Build Work Zone, advanced edition is created as part of the onboarding process. See [Getting Started](https://help.sap.com/viewer/b03c84105ff74f809631e494bd612e83/Cloud/en-US/627b9e36a3da430199133c6ca0db45d8.html) 

        For more information about creating a service instance, see [Creating Service Instances in Cloud Foundry](https://help.sap.com/viewer/09cc82baadc542a688176dce601398de/Cloud/en-US/6d6846def3c443aa9f83d127353147ce.html)

    2.  Create a service key for the instance you created \(this is required for creation of a destination on the source system\). For more information, see [Creating Service Keys in Cloud Foundry](https://help.sap.com/viewer/09cc82baadc542a688176dce601398de/Cloud/en-US/6fcac08409db4b0f9ad55a6acd4d31c5.html)

2.  In the subaccount that hosts the Cloud Transport Management service, perform the following:
    1.  Create a subscription and a service instance \(you must have a space in your subaccount to be able to do this\) to the Cloud Transport Management service.

    2.  Create a service key for the instance \(this is required for creation of destinations\).
    3.  To be able to access the SAP Transport Management service, verify that you are assigned to the relevant role collections. For more information, see [Initial Setup](https://help.sap.com/viewer/7f7160ec0d8546c6b3eab72fb5ad6fd8/Cloud/en-US/66fd7283c62f48adb23c56fb48c84a60.html) 

3.  To see the “Transport Selected Content” option in the Site Manager, you need to configure a destination in the source subaccount; typically this is DEV.
    1.  In the source subaccount *Connectivity* \> *Destinations*, create a new destination. Destination name **must** be `ctms_destination`.
    2.  Use the following parameters from the Transport Management service key:


        <table>
        <tr>
        <th valign="top">

        Destination Parameter
        
        </th>
        <th valign="top">

        Value in the service key
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        URL
        
        </td>
        <td valign="top">
        
        `uri`
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Client ID
        
        </td>
        <td valign="top">
        
        `uaa/clientid`
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Client Secret
        
        </td>
        <td valign="top">
        
        `uaa/clientsecret`
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Token Service URL
        
        </td>
        <td valign="top">
        
        `uaa/url` + `/oauth/token` \(add at the end\)

        For example:

        `https://<org-unit>.authentication.eu20.hana.ondemand.com/oauth/token`
        
        </td>
        </tr>
        </table>
        
    3.  You must use the Authentication type `OAuth2ClientCredentials`.
    4.  In the additional parameters, add the parameter `node-name` and set the value with the name of the initial transport node configured in the Transport Management service \(usually DEV\). This internally invokes the API [/nodes/export](https://api.sap.com/api/TMS_v2/resource) and the transport request is added to the queues of the follow-on node provided as the parameter name.

4.  In the subaccount that hosts the Cloud Transport Management service, create a destination to each target SAP Build Work Zone, advanced edition tenant. Use the values from the service key you've created in step 1. For example, DEV, TST, and PRD.
    1.  In *Connectivity* \> *Destinations*, create a new destination.
    2.  Use the following parameters from the service key:


        <table>
        <tr>
        <th valign="top">

        Destination Parameter
        
        </th>
        <th valign="top">

        Value in the service key
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        URL
        
        </td>
        <td valign="top">
        
        `endpoints/portal-service` + `/cdm_import_service` \(add at the end\)

        For example:

        `https://portal-service.cfapps.eu20.hana.ondemand.com/cdm_import_service`
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Client ID
        
        </td>
        <td valign="top">
        
        `uaa/clientid`
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Client Secret
        
        </td>
        <td valign="top">
        
        `uaa/clientsecret`
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Token Service URL
        
        </td>
        <td valign="top">
        
        `uaa/url`
        
        </td>
        </tr>
        </table>
        
    3.  You must use the Authentication type `OAuth2ClientCredentials`.

5.  To ensure role collections creation during the transport of content, use the SAP BTP CLI to obtain API credentials, to be able to access the APIs of the Identity Authentication service. For example:

    ```
    $ btp create security/api-credential --name my-credential --subaccount <subaccount id>
    ```

    The response will show the credentials in the following format:

    ```
    Name: my-credential
    Client ID: <client id>
    Credential Type: secret
    Client Secret: <secret>
    Read-only: false
    Token URL: https://<host>.authentication.<data center>.hana.ondemand.com/oauth/token
    API URL: https://api.authentication.<data center>.hana.ondemand.com
    ```

6.  Using these credentials, configure a destination to Identity Authentication:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Value
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Name*
    
    </td>
    <td valign="top">
    
    `xsuaa-apiaccess`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Type*
    
    </td>
    <td valign="top">
    
    HTTP
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *URL*
    
    </td>
    <td valign="top">
    
    `<API URL>`

    Copy this value from the value of `API URL` in the output of the CLI command.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Proxy Type*
    
    </td>
    <td valign="top">
    
    Internet
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Authentication*
    
    </td>
    <td valign="top">
    
    OAuth2ClientCredentials
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Client ID*
    
    </td>
    <td valign="top">
    
    `<Client ID>`

    Copy this value from the value of `Client ID` in the output of the CLI command.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Client Secret*
    
    </td>
    <td valign="top">
    
    `<Client Secret>`

    Copy this value from the value of `Client Secret` in the output of the CLI command.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service URL Type*
    
    </td>
    <td valign="top">
    
    Dedicated
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Token Service URL*
    
    </td>
    <td valign="top">
    
    `<Token URL>`

    Copy this value from the value of `Token URL` in the output of the CLI command.
    
    </td>
    </tr>
    </table>
    
    Make sure that the option *Use default JDK truststore* is selected.

7.  In the Transport Management service, configure transport nodes to represent your landscape.

    ctms\_nodes1

    The destination should match the destination which was created earlier. Also ensure that the content type is “Application Content”. This will determine the subaccount to which the Transport Management service will push the contents.

    ctms\_nodes

    For more information about how to create transport node, see [Create Transport Nodes](https://help.sap.com/viewer/7f7160ec0d8546c6b3eab72fb5ad6fd8/Cloud/en-US/f71a4d5550cd453ea824d5b5c677969d.html)

8.  Create routes to indicate the path for the flow of contents in the landscape.

    ctms\_routes1

    For more information about how to create routes, see [Create Transport Routes](https://help.sap.com/viewer/7f7160ec0d8546c6b3eab72fb5ad6fd8/Cloud/en-US/dddb74937a014aea8d3d76d740180597.html)


