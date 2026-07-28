<!-- loio3db887a26f6e44bd929f4ccdb9e7f5d7 -->

# Set Up Your Development Environment

You need an IDE \(integrated development environment\) to develop your applications.

> ### Recommendation:  
> We recommend using SAP Business Application Studio for optimal integration with SAP BTP functions:
> 
> In SAP Business Application Studio, you only have to do the following:
> 
> 1.  Set up a Fiori dev space \(see [SAP Business Application Studio: Managing Your Dev Spaces](https://help.sap.com/viewer/9d1db9835307451daa8c930fbd9ab264/Cloud/en-US/4142f786f3d345699c3d5fbebda5ded6.html)\).
> 
> 2.  Create a SAP Fiori project from a template \(see [SAP Business Application Studio: Create an SAP Fiori Project](https://help.sap.com/viewer/9d1db9835307451daa8c930fbd9ab264/Cloud/en-US/46664de4d6944471b6c29a0681bfd0fc.html)\).

If you choose to use another IDE, create a project in the following way:



<a name="loio3db887a26f6e44bd929f4ccdb9e7f5d7__section_p21_24b_vlb"/>

## Prerequisites

-   Cloud Foundry Command Line Interface \(`cf CLI`\) is installed locally, see [Download and Install the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/4ef907afb1254e8286882a2bdef0edf4.html).

-   The MultiApps plug-in for the `cf CLI` to deploy MTAs is installed locally, see [Install the MultiApps Plug-in in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/27f3af39c2584d4ea8c15ba8c282fd75.html).

-   The Cloud MTA Build Tool \(MBT\) is installed, see [Cloud MTA Build Tool: Download](https://sap.github.io/cloud-mta-build-tool/download/)

-   `Node.js` is installed locally.

    Configure the npm registry to use the @sap scope with the following command:

    `npm config set @sap:registry https://registry.npmjs.org`




<a name="loio3db887a26f6e44bd929f4ccdb9e7f5d7__section_zfs_n45_wlb"/>

## CF CLI Plugin for HTML5 Applications

The CF HTML5 Applications Repository CLI Plugin is a plugin for the Cloud Foundry CLI tool that aims to provide easy command line access to interact with the HTML5 Application Repository service. It allows you to:



-   Inspect HTML5 applications of current space

-   List files of a specific HTML5 application

-   View HTML5 applications managed by SAP BTP

-   Download a single file, application or the whole bucket of applications uploaded with the same service instance of the `html5-apps-repo` service

-   Push one or multiple applications using existing service instances of the `app-host` plan, or create new ones for you on-the-fly


For more information, see [CF HTML5 Applications Repository CLI Plugin](https://sap.github.io/cf-html5-apps-repo-cli-plugin/).



<a name="loio3db887a26f6e44bd929f4ccdb9e7f5d7__section_ywc_34b_vlb"/>

## Project Structure

> ### Note:  
> A sample hello world application can be found [here](https://github.com/SAP-samples/multi-cloud-html5-apps-samples).

Use the following structure for the project:

```
myDevProject
- HTML5Module
    xs-app.json
    index.html
    manifest.json
- HTML5Module2
...
xs-security.json
mta.yaml

```



### `manifest.json` \(application descriptor\)

For general information about the application descriptor, see [Descriptor for Applications, Components, and Libraries](https://help.sap.com/viewer/468a97775123488ab3345a0c48cadd8f/latest/en-US/be0cf40f61184b358b5faedaec98b2da.html)

> ### Sample Code:  
> ```
> {
> 	"sap.app": {
> 		"id": "<namespace>.<HTML5Module>",
> 		"applicationVersion": {
> 			"version": "1.0.0"
> 		}	
> 	},
> 	"sap.cloud":{
> 		"public": true,
> 		"service": "<namespace>.<my-service>"
> 	}
> }
> 
> ```

For example:

> ### Sample Code:  
> ```
> {
> 	"sap.app": {
> 		"id": "sales.orders",
> 		"applicationVersion": {
> 			"version": "1.0.0"
> 		}	
> 	},
> 	"sap.cloud":{
> 		"public": true,
> 		"service": acme.crm
> 	}
> }
> 
> ```



### `xs-app.json` \(routing configuration\)

The routing configuration sets up the integration with the HTML5 Application Repository, see [Configure Application Routing \(xs-app.json\)](configure-application-routing-xs-app-json-a0c76f4.md)\)

> ### Sample Code:  
> ```
> {
>   "routes": [
>     {
>       "source": "^(.*)$",
>       "target": "$1",
>       "service": "html5-apps-repo-rt",
>       "authenticationType": "xsuaa"	
>     }
>   ]
> }  
> 
> ```



### `xs-security.json` \(security configuration\)

The security configuration provides authentication and authorization.

> ### Sample Code:  
> ```
> {
>   "xsappname": "acme.crm",
>   "tenant-mode": "dedicated",
>   "description": "Security-profile-of-called-application",
>   
>   "role-templates": [
>     {
>       "name": "Token_Exchange",
>       "description": "UAA",
>       "scope-references": [
>         "uaa.user"
>       ]
>     }
>   ]
> }
> 
> ```



### `mta.yaml` \(deployment configuration\)

> ### Sample Code:  
> ```
> _schema-version: "3.2"
> ID: hello-world
> version: 0.0.1
> modules:
> - name: hello-world-destination-content
>   type: com.sap.application.content
>   requires:
>   - name: uaa_hello-world
>     parameters:
>       service-key:
>         name: uaa_hello-world-key
>   - name: hello-world_html_repo_host
>     parameters:
>       service-key:
>         name: hello-world_html_repo_host-key
>   - name: hello-world-destination-service
>     parameters:
>       content:
>         instance:
>           destinations:
>           - Name: my_service_hello_world_html_repo_host
>             ServiceInstanceName: hello-world-html5-app-host-service
>             ServiceKeyName: hello-world_html_repo_host-key
>             sap.cloud.service: my.service
>           - Authentication: OAuth2UserTokenExchange
>             Name: my_service_uaa_hello_world
>             ServiceInstanceName: hello-world-xsuaa-service
>             ServiceKeyName: uaa_hello-world-key
>             sap.cloud.service: my.service
>           existing_destinations_policy: update
>       content-target: true
>   build-parameters:
>     no-source: true
> - name: hello-world_ui_deployer
>   type: com.sap.application.content
>   path: .
>   requires:
>   - name: hello-world_html_repo_host
>     parameters:
>       content-target: true
>   build-parameters:
>     build-result: resources
>     requires:
>     - artifacts:
>       - HTML5Module-content.zip
>       name: HTML5Module
>       target-path: resources/
> - name: HTML5Module
>   type: html5
>   path: HTML5Module
>   build-parameters:
>     builder: custom
>     commands:
>     - npm run build
>     supported-platforms: []
> resources:
> - name: hello-world-destination-service
>   type: org.cloudfoundry.managed-service
>   parameters:
>     config:
>      HTML5Runtime_enabled: true
>       init_data:
>         instance:
>           destinations:
>           - Authentication: NoAuthentication
>             Name: ui5
>             ProxyType: Internet
>             Type: HTTP
>             URL: https://ui5.sap.com
>           existing_destinations_policy: update
>       version: 1.0.0
>     service: destination
>     service-name: hello-world-destination-service
>     service-plan: lite 
> - name: hello-world_html_repo_host
>   type: org.cloudfoundry.managed-service
>   parameters:
>     service: html5-apps-repo
>     service-name: hello-world-html5-app-host-service
>     service-plan: app-host
> - name: uaa_hello-world
>   type: org.cloudfoundry.managed-service
>   parameters:
>     path: ./xs-security.json
>     service: xsuaa
>     service-name: hello-world-xsuaa-service
>     service-plan: application
> build-parameters:
>   before-all:
>   - builder: custom
>     commands:
>     - npm install
> 
> ```

If a business service is required, configure it in the `mta.yaml` file.

If your backend application is part of the same mta, add the backend application \(and a destination configuration that points to it\) to the `mta.yaml` file.

**Related Information**  


[Configure Destinations \(HTML5\)](configure-destinations-html5-fab4035.md "A destination defines the back-end connectivity. In its simplest form, a destination is a URL to which requests are forwarded. There must be a destination for every single app (microservice) that is a part of the business application.")

[SAP Business Application Studio Developer Guide](https://help.sap.com/viewer/9d1db9835307451daa8c930fbd9ab264/Cloud/en-US/84be8d91b3804ab5b0581551d99ed24c.html)

