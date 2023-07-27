<!-- loioac120ecdf905415f96277936fba418ad -->

# Understanding the OData $metadata file

The OData `$metadata` file is a CSDL file that is made available to clients to help them discover an OData API's structure and organization.



<a name="loioac120ecdf905415f96277936fba418ad__csdl"/>

## CSDL

The Conceptual Schema Definition Language \(CSDL\) is an XML-based language that describes the entities, relationships, and functions that make up the conceptual model of a data-driven application.

-   [CSDL Specification](https://learn.microsoft.com/en-us/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)



<a name="loioac120ecdf905415f96277936fba418ad__metadata"/>

## OData $metadata

While the `$metadata` file is primarily intended for client application use, it does provide human-readable information on the remote application's API. The sections of information that provides are as follows:

-   **EntityType:** Describes each entity, its properties \(including information on its data type, and whether it is nullable in POSTs, filterable or sortable in collection-valued GETs, and whether it is updatable \[can be PATCHed\]\), and its navigations.
-   **Association:** Provides details on each navigation available in the API, including its role, type, and multiplicity. \(Role can be "Creator" while type is "Member", for example; multiplicity indicates the number of resources that can be involved at each "end" of the association or navigation.\)
-   **EntitySet:** Provides a concise listing of all the entities available in the API, with information on their name, entity type, and whether they are creatable, updatable, or deletable.
-   **AssociationSet:** Provides further details on navigations, including whether each navigation is creatable, updatable, or deletable.
-   **FunctionImport \(Service Operations\):** Provides information on each service operation available in the API, including their name, HTTP method, the entity that they act on, the name and data type of any required parameters and the type of data that they return, if any \(such as data type, entity type, and whether the return is a collection\).

