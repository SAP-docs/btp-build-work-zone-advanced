<!-- loioc1b9d6facfc942e3bca664ae06387e9b -->

# Developing HTML5 Applications \(Legacy Flow\)

SAP BTP enables you to access and run HTML5 applications in a cloud environment without the need to maintain your own runtime infrastructure.



HTML5 applications consist of static content that runs on a browser. You develop your applications - either in SAP Business Application Studio, or in your own IDE \(integrated development environment\) - and deploy them to the HTML5 Application Repository.

Depending on your backend application setup, you either configure the destinations during development, or define them after deploying the application. Finally, you can define a custom domain and run the application.

> ### Note:  
> SAP Build Work Zone, advanced edition developers can switch to a more advanced scenario of developing integrated HTML5 business solutions, that can be consumed across subaccounts in a single tenant or across tenants. The MTA of a business solution, contains a `cdm.json` file with all the site design-time definitions, and runtime and design-time destinations. Upon deployment, consumers can subscribe to the business solution and define it as a content provider in the subaccount. For more information, see [Developing Business Solutions](developing-business-solutions-1f79942.md).



<a name="loioc1b9d6facfc942e3bca664ae06387e9b__section_b1v_1mt_5lb"/>

## Managed Application Router

The managed application router is the HTML5 Applications Runtime capability provided by SAP Build Work Zone, advanced edition, to which you must be subscribed.

The managed application router is used to serve static content, authenticate users, rewrite URLs, and forward or proxy requests to other micro services while propagating user information.

In SAP BTP, one or more HTML5 Applications are associated to an SAP Cloud Service \(`sap.cloud.service`\). An SAP Cloud Service represents a business solution that is delivered as a product, for example, a CRM or an HR solution.

An SAP Cloud Service has a common authentication/authorization model containing all the roles and scopes required to access the different parts of the solution. This authentication/authorization model is represented by an XSUAA \(SAP Authorization and Trust Management\) service instance. In the configuration of this service instance, you can model roles and scopes that can be later on used to restrict access in the routes configuration file \(`xs-app.json`\).

When you create a project in SAP Business Application Studio \(or your IDE of choice\), you must provide the SAP Cloud Service value.

> ### Note:  
> This documentation covers running HTML5 Applications using the application router managed by SAP. For advanced cases, SAP BTP also enables you to maintain your own standalone application router in your own space. For more information about this option, see the [HTML5 Applications](https://help.sap.com/viewer/product/HTML5_APPLICATIONS/Cloud/en-US) product page.

**Related Information**  


[What is the HTML5 Application Repository?](what-is-the-html5-application-repository-0e1c52b.md "The HTML5 Application Repository centrally stores the applications' static content on the SAP BTP.")

[Basic Development Flow](basic-development-flow-ea482cc.md "After subscribing to SAP Build Work Zone, advanced edition, you receive a single point-of-entry for your applications running on SAP BTP. You develop and build HTML5 Applications in an IDE, and deploy them to the HTML5 Application Repository, so that you can access and launch them during runtime.")

[Run Applications](run-applications-95eb38f.md "Run your HTML5 applications either standalone or in SAP Build Work Zone, advanced edition.")

