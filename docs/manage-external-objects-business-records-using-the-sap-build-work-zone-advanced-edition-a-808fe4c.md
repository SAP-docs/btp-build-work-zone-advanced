<!-- loio808fe4ca0cf54be3a97f8595592ca14e -->

# Manage "external objects" \(business records\) using the SAP Build Work Zone, advanced edition API

Up to this point in the guide, we have only discussed exposing external objects in the SAP Build Work Zone, advanced edition interface, via OData services and annotations. However, External Objects can also be created and added to a workspace as either the workspace’s primary or related object. Feed entries can also be posted to External Object feeds, and retrieved by an external application whose users have access to the feed’s external object.



## Creating an External Object

External Objects are created in SAP Build Work Zone, advanced edition through an HTTP POST operation to the OData collection given by the URL: `/api/v1/OData/ExternalObjects`. For the API Reference page for this API call, see [POST/ExternalObjects](https://jam2.sapjam.com/work_zone/ODataDocs/ui#post__externalobjects).

The format of the POST request is provided by the OData v2 standard. SAP Build Work Zone, advanced edition accepts both JSON and XML requests. The parameters that are supported in the POST body are listed in the following API doc: [Request/Response Schema](https://jam2.sapjam.com/work_zone/ODataDocs/ui#external_externalobject_schema).

The OData response body for the POST request will include the SAP Build Work Zone, advanced edition ID for the external object. This ID should be used in subsequent External Object calls to the OData API.



## Creating a Workspace with an External Object

Once the External Object is created in SAP Build Work Zone, advanced edition, it can be linked to a workspace. The object can either be linked as the workspace's "Primary" object, or it can be added into the set of "Featured" objects in the workspace.

Since a workspace can only have a single primary object, and since the object cannot be changed once the workspace is created, linking an object to a workspace as that workspace’s "Primary" object can only be done at workspace creation time. Workspaces are created through an HTTP POST operation to the OData collection given by the URL: `/api/v1/OData/Groups`. For the API Reference page for this API call, see [POST/Groups](https://jam2.sapjam.com/work_zone/ODataDocs/ui#post__groups).

The details of creating a workspace with the SAP Build Work Zone, advanced edition OData API can be found in the API Guide. To include a link to an External Object as the workspace’s primary object, the POST body should include the full URI to the SAP Build Work Zone, advanced edition representation of the External Object, following the OData standard for posting links. For example, the POST body for creating a workspace with a primary external object in JSON format should look like this:

```
{
    "Name":"Example Workspace",
    "Description":"This workspace has a primary external object",
    "GroupType":"private_internal",
    "PrimaryExternalObject":{"__metadata":{"uri": "https://<jam_uri>/api/v1/OData/ExternalObjects('<id>')" } }
}
```



## Featuring an External Object in a Workspace

External Objects can also be “Featured” into an existing workspace. To feature an object into an existing workspace, POST the object’s URI to the URL, using the OData “InsertLink Request” format:

```
/api/v1/OData/Groups('workspace_id')/$links/FeaturedExternalObjects
```

In JSON, for example, the POST body would simply be:

```
{
    uri": "https://<jam_uri>/api/v1/OData/ExternalObjects('<id>')"
}

```



## SAP Build Work Zone, advanced edition OData API calls related to External Objects

The follow links point to the individual API calls and the sections in the SAP Build Work Zone, advanced edition OData API Reference that relate to external objects:

-   The [External](https://jam2.sapjam.com/work_zone/ODataDocs/ui#external_externalapplication_introduction) section in the API Reference.
-   The [\[POST\] /Groups](https://jam2.sapjam.com/work_zone/ODataDocs/ui#post__groups) API call creates workspaces, including creating a workspace with a primary external object.
-   The [\[GET\] /Groups\('\{id\}'\)](https://jam2.sapjam.com/work_zone/ODataDocs/ui#get__groups_) API call retrieves the information about the specified workspace.
-   The [GroupExternalObject](https://jam2.sapjam.com/work_zone/ODataDocs/ui#group_groupexternalobject_introduction) section about external objects in a workspace.
-   The [OData Activity API Calls](https://jam2.sapjam.com/work_zone/ODataDocs/ui#post__activities) are used to communicate external object Activity messages.

