<!-- loioe6dd6645a74d41a5a9376da80390012b -->

# Passing Information to the Backend Using a Destination

Developers can enhance the destination behavior to pass URL query parameters or HTTP headers to the backend.



## Motivation

When you need to pass confidential information to a backend, and it can't be passed through the client application, configure the destination to pass information via URL query parameters or headers in an HTTP request.



<a name="loioe6dd6645a74d41a5a9376da80390012b__section_zss_fjh_llb"/>

## Procedure

1.  In the SAP BTP cockpit, create in your subaccount a destination to the desired backend.
2.  Add the following additional parameters to the destination:


    <table>
    <tr>
    <th valign="top">

    Field Name


    
    </th>
    <th valign="top">

    Value


    
    </th>
    <th valign="top">

    Comments


    
    </th>
    <th valign="top">

    Example


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    HTML5.DynamicDestination


    
    </td>
    <td valign="top">
    
    true


    
    </td>
    <td valign="top">
    
    **Mandatory**


    
    </td>
    <td valign="top">
    
    `HTML5.DynamicDestination:true`


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    sap.header.<Header-Name\>


    
    </td>
    <td valign="top">
    
    <Header-Value\>


    
    </td>
    <td valign="top">
    
    Optional \(zero or more\)

    <Header-Name\> is the header name that will be replaced.


    
    </td>
    <td valign="top">
    
    `sap.header.CustomHeader:CustomValue`

    `sap.header.AnotherCustomHeader:AnotherCustomValue`


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    sap.query


    
    </td>
    <td valign="top">
    
    <Query-Value\>


    
    </td>
    <td valign="top">
    
    Optional \(zero or one\)

    URL must not be encoded.


    
    </td>
    <td valign="top">
    
    If you want to add the URL query parameter `s=5&api-key=111-222-333`, you need to enter `sap.query:s=5&api-key=111-222-333`


    
    </td>
    </tr>
    </table>
    

