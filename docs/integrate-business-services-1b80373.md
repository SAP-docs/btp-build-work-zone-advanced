<!-- loio1b80373be4fc4cbb8a7529495c9c9d62 -->

# Integrate Business Services

The managed application router supports integration with business services for SAP BTP, which are a flavor of reuse-services.

A business services exposes a set of attributes that enables the managed application router to serve business service UI and/or data. For more information, see [Prepare Business Services](prepare-business-services-bf7d98c.md).



<a name="loio1b80373be4fc4cbb8a7529495c9c9d62__section_d2t_2hz_kmb"/>

## Prerequisites

This section describes how the managed application router accesses the business service UI and/or data.

-   Create a service instance of the business service.

-   Create a destination pointing to the business service instance.

    > ### Sample Code:  
    > ```
    > modules:
    > - name: hello-world-destination-content
    >   type: com.sap.application.content
    >   requires:
    >   
    >   ...
    >   
    >   - name: <business-service-resource-name>
    >     parameters:
    >       service-key:
    >         name: <business-service-instance-key>
    >   ...
    > 
    >   parameters:
    >     content:
    >       subaccount:
    >         destinations:
    > 	        ...
    > 
    >         - Name: <destination-name pointing to business-service-instance>
    >           Authentication: OAuth2UserTokenExchange
    >           ServiceInstanceName: <business-service-instance-name>
    >           ServiceKeyName: <business-service-instance-key>
    >           	...
    > 
    >         existing_destinations_policy: update
    >  ...
    > 
    > resources:
    > 
    >   ...
    > 
    > - name: <business-service-resource-name>
    >   type: org.cloudfoundry.managed-service
    >   parameters:
    >     service: <business-service-name>
    >     service-name: <business-service-instance-name>
    >     service-plan: <business-service-plan>
    > 
    >   ...
    > ```

-   The business service UI must be stored in HTML5 Application Repository and it must be defined as *public* to be accessible from the application router.




<a name="loio1b80373be4fc4cbb8a7529495c9c9d62__section_wbg_mgz_kmb"/>

## Accessing Business Service Data

To access business service data, configure in the the `xs-app.json` file the following attributes:

-   `service` - configure a route that references a specific:

    ```
    sap.cloud.service
    ```

    or

    ```
    sap.cloud.service.alias
    ```

-   `endpoint` - configure the endpoint that is used to get the service URL.


> ### Sample Code:  
> ```
> "routes": [ 
> 
>     { 
> 
>       "source": "^/odata/v2/(.*)$", 
> 
>       "target": "$1", 
> 
>       "service": "<business-service-sap-cloud-service>", 
> 
>       "endpoint": "<business-service-endpoint>" 
> ```



<a name="loio1b80373be4fc4cbb8a7529495c9c9d62__section_c5y_23z_kmb"/>

## Accessing Business Service UI

To access the business service UI stored in HTML5 Application Repository, run the application. For more information, see [Run Applications Standalone](run-applications-standalone-a3eceb5.md).

