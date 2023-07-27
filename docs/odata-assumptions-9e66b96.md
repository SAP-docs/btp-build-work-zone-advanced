<!-- loio9e66b961c48643c88ed7958ccf092403 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# OData Assumptions

Information related to OData and business record editors.



## OData Versions

The Business Record Editor \(BRE\), the Business Record Viewer \(BRV\), and the Business Record Browser \(BRB\) all assume that the external application provides an OData version 2.0 API. For example, `$format=json` must be supported. See [OData documentation](https://www.odata.org/documentation/).

The new BRV in SAP Build Work Zone, advanced edition supports OData v.2 data feeds, with a limited set of OData v.4 annotations \(in a separate resource URL\).

The expectation of the OData data source is that it will behave responsibly. That is, entities and properties can be added, but not removed. Properties can be deprecated \(for example, made nullable\). For the most part the API should be backwards compatible with previous functionality. The same approach is taken in the SAP Build Work Zone, advanced edition OData API.



## Timeouts

When making calls to the external application, the official timeout on external calls is 5 seconds for opening a connection and 30 seconds on reading from that call. Timing out on the same request twice will result in a three minute wait before the next retry is performed.



## Users Who Don't Have Access and External Users

Users who don't have access to the external application and external users are able to see the primary external object link but they can't see any data. Additionally, the featured objects should be visible. Essentially, any live data should not be available, such as the lists of related objects \(but the navigation could exist\).



## Business Record Editor \(BRE\)

The BRE is responsible for importing external XML annotations and storing them locally within SAP Build Work Zone, advanced edition.

Current maximums:

-   Identity: 20 fields, maximum.
-   LineItem: 10 fields, maximum.
-   Quickview/Overview: 7 fields, maximum. Generated if missing as the first 7 items in the identity section.
-   Facets: a total of 5 facets/tabs:
    -   Detail Facet: 20 fields, maximum.
    -   Collection Facet: 10 fields, maximum.


SAP Build Work Zone, advanced edition parses the following annotation terms for a given record type:

-   `UI.HeaderInfo` \(required\)
    -   The Title property is required. All other properties are optional.

-   `UI.Identification` \(required\)
    -   Must contain at least one parseable record that can be displayed in the BRV.

-   UI.LineItem \(required\)
    -   Must contain at least one parseable record that can be displayed in the BRB.

-   `UI.Facets` 
    -   SAP Build Work Zone, advanced edition tries to parse records of type `UI.ReferenceFacet` or `UI.CollectionFacet` within the `UI.Facets` collection.
    -   The facet is expected to have a valid Label PropertyValue.
    -   A `UI.ReferenceFacet` is expected to have a Target Property with an AnnotationPath.
        -   SAP Build Work Zone, advanced edition accepts an AnnotationPath of the form `"@UI.FieldGroup#Qualifier"` or `"Navigation/@UI.LineItem"` or `"@Term/@UI.LineItem"`.
        -   The first case must refer to a `UI.FieldGroup` annotation belonging to the same entity type with the defined Qualifier.
        -   The second case refers to a `UI.LineItem` annotation belonging to the navigation's entity type. Note that the navigation must be a collection.
        -   The third case refers to an annotation term that references a collection from a linked annotation.

    -   A `UI.CollectionFacet` is expected to contain at least one `UI.ReferenceFacet` that follows the previous rule.
        -   SAP Build Work Zone, advanced edition will attempt to parse the first `UI.ReferenceFacet` sub-facet that follows this pattern and will display its content with the `UI.CollectionFacet`'s label.
        -   All other subfacets in the `UI.CollectionFacet` will be ignored.



SAP Build Work Zone, advanced edition will try to parse Apply elements that use the "`odata.concat`" Function.

SAP Build Work Zone, advanced edition will try to parse `Measures.Unit` and `Measures.ISOCurrency` annotation terms.



## Linked Annotations

SAP Build Work Zone, advanced edition has very limited support for parsing linked annotations from other OData services.

SAP Build Work Zone, advanced edition tries to import linked annotation documents by analyzing the XPath:

```
//edmx:Reference[@Uri and edmx:IncludeAnnotations/@TargetNamespace]
```

SAP Build Work Zone, advanced edition tries to import the associated metadata resources by analyzing the XPath:

```
//edmx:Reference[@Uri and edmx:Include/@Namespace='TargetNamespace' and edmx:Include/@Alias]
```

The URI attributes for both the annotations and metadata must be fully qualified URIs. Relative URIs are not currently supported.

Any types that are referenced from the linked annotation must have a term defined under the main annotation schema with the following format:

```
<Term Name="TermIdentifier" Type="Collection(MetadataAlias.ForeignEntityType)"/>
```

When you want to show a collection of this foreign entity type in a facet, you must create a special annotation to define the URI of the collection following this format:

```
<Annotation Term="SchemaAlias.TermIdentifier">
    <UrlRef>
        <Apply Function="odata.fillUriTemplate">
            <String>https://pattern...'{P0}'...pattern</String>
            <LabeledElement Name="P0">
                <Apply Function="odata.UriEncode">
                    <Path>NavigationPath</Path>
                </Apply>
            </LabeledElement>
        </Apply>
    </UrlRef>
</Annotation>
```

Defining the URI using any other method is not supported.

The facet must reference this annotation by using:

```
<PropertyValue AnnotationPath="@SchemaAlias.TermIdentifier/@UI.LineItem" Property="Target"/>
```

The foreign entity type must have a `UI.LineItem` annotation defined in the linked annotation document.



## Business Record Viewer \(BRV\)

-   The viewer assumes that the external annotation has been imported to SAP Build Work Zone, advanced edition. Any unsupported features are simply filtered out at import time \(see above\).
-   The viewer only supports OData responses in JSON format, so all requests have the `$format=json` parameter appended.
-   No `$expand` parameters are used, so if the annotations references any properties that aren't contained within the external object, for example, properties of navigation, the BRV will display an error message instead.
-   Table content supports pagination of 20 items per page using `$top=20` and `$skip` to move between pages.
-   If no `UILink` or `CRMUILink` is provided, there will be no permalink provided. In this case, the UI in the BRV will hide the link for "View in XXX".

> ### Note:  
> We currently do not support "Precision" and "Scale" field in the property value. For all decimal types, we display the content as given without modification. For example, "1000.000" will be display as "1000.000".

> ### Note:  
> For the SuccessFactors Learning \(LMS\) external application, we added a workaround to hide the "show more" button in the Business Record facet viewer. LMS does not currently support paging for facet collections."



## Business Record Browser \(BRB\)

The URL for the BRB is the URL from "External Type" on the object type with $ to the \# removed. For example, the following URL:

```
https://example.com/odata/v1/c4c.svc/$metadata#CorporateAccountCollection
```

would translate to:

```
https://example.com/odata/v1/c4c.svc/CorporateAccountCollection
```

> ### Note:  
> The object type is defined in the "External Applications" section of admin for a company.

Assumptions on this endpoint and how the list gets shown:

-   `$skip` and `$top` are supported on the above endpoint:
    -   Potentially, it also needs to support `$filter` and `$orderby` \(see below\).
    -   `$orderby` needs to support both `asc` \(ascending\) and `desc` \(descending\) options. This is assumed on sort fields.

-   `lineItem` is defined in the annotation:
    -   The first field of the line item is the "title"; it shows up first.
    -   The second field is the second column.
    -   All other fields show up under the title in that column, unless they are marked as sortable \(see below\).

-   The BRB instantiates `ex_objs`, which are links back to the parent system. Since we only want to have one link back to the system, it must be unique. To achieve this, the result that is returned by the endpoint must have URLs that are consistent elsewhere in the application.
    -   There are two possible formats for even the most simple OData URL:

        ```
        https://example.com/odata/v1/c4c.svc/CorporateAccountCollection('00163E03A0701ED28B9DAF815866301D')
        ```

        ```
        https://example.com/odata/v1/c4c.svc/CorporateAccountCollection(Id='00163E03A0701ED28B9DAF815866301D')
        ```

        Either one or the other must be used throughout the application.

    -   They should be made consistent with any calls made to APIs such as `POST /ExternalObjects`.
    -   A property called "`Name`" exists that we can use when instantiating an `ex_obj`.

-   Non-Compounded data fields will have a navigation field which we can use as a path. For example, "&Name"
-   Compounded data fields are specified by the params and pattern tags.
    -   In the params list, there should be a navigation, which is used to build up the value and path.
    -   There is no recursion in the params tag. If there was recursion, we will definitely will not have room on screen to display compounded data fields.
    -   Paths are generated by walking the params and building the string using the navigation. For example, "`&ExpectedValue/Content &ExpectedValue/Currency"`.
    -   We do not support recursively generating compounded data field. It would not be feasible as we don't have sufficient screen real estate to render them.

-   If a Date field uses the `Date(xx)` decoration, it will be rendered using the long form in the thing inspector with the following format: "`%B %d, %Y, %I:%M:%S %p`". The quick hover card will use the short form with the following format: "`%b %d, %Y, %I:%M:%S %p`"
-   The date string is expressed in the time zone of the OData API user associated with the OAuth token.

**To make the columns of your business record sortable**:

1.  Open the *Admin Console* \> *External Applications* section.
2.  In the row for your application, click *Action* and select *Manage Record Types* from the drop-down menu.
3.  In the row for the business record to which you want to add a sort property, click *Sort Fields*.
4.  Add the sort fields you want in the *Sort Fields* text box.

    Click *Show Fields Hint* to display a list of the properties available for your sort order. You can copy and paste these values into the *Sort Fields* text box. Ensure that each entry in the text box begins with an ampersand \(&\) and is separated from the next field by a comma.

    Ensure that your OData service supports "`$orderby=thePropertyYouJustAdded`".

5.  When you have set the sort order that you want, click *Update*.

**To apply filters to your business record**:

1.  Open the *Admin Console* \> *External Applications* section.
2.  In the row for your application, click *Action* and select *Manage Record Types* from the drop-down menu.
3.  In the row for the business record to which you want to add a filter, click *Filters*.
4.  In the filters catalog for the selected business record, click *New Filter*.
5.  Enter a *Name* for the filter, add properties in the *Filter* text box.

    Ensure that the properties you add are `$filterable` in your OData service.

6.  Select the *Enabled* check box to make it immediately available, and click *Submit* to save the filter.

**To make your business record searchable**:

1.  Open the *Admin Console* \> *External Applications* section.
2.  In the row for your application, click *Action* and select *Manage Record Types* from the drop-down menu.
3.  In the row for the business record to which you want to add search capabilities, click *Edit*.
4.  In the *Edit Record Type* dialog box, select the *Show Search* check box, and set the *Hint* \(the example text that will appear in the empty search text box\) and the *Property* that users searches will search against.

    If the property is a string, it must support `startswithfor` "`Edm.Int32`", "`Edm.Int64`", "`Edm.Int16`", "`Edm.Decimal`", "`Edm.Single`", "`Edm.Double`".

    In the search operation, we just check for equality; for example: `startswith(AccountID,'100')` means that our string search starts from the start of a string \(not an inner search\).

    See `convert_search_string_to_odata_query` for more details.




## Related Business Record \(Related External Objects\)

When a business record has a one to many relationship with other business records through navigation paths, they are considered related. This is determined by parsing the metadata to find associated navigation paths to other business records. When relationships are found via the `navigation_path`, we add an entry in the `related_items` section of the view definition with the `type`, `navigation`, `entityType`, and `entityCollectionName`.

An example would look something like this:

```
"relatedItems": [
    {
        "type": "relatedItem",
        "navigation": "Opportunity",
        "entityType": "Opportunity",
        "entityCollectionName": "OpportunityCollection"
    },
    ..
}
```

When viewing a workspace page with a business record, we check if any of the related items specified in the `relatedItems` in the `view_definition` were registered previously with the client integration. If found, the related objects will be added to the related list, which is viewable by selecting the <span class="SAP-icons"></span> Page navigator icon in the workspace header.

We currently assume the following:

-   Related navigation do not use complex keys.
-   Supported related objects are defined by a metadata `navigation_path` field.
-   For performance purposes, we do not update related business records, including the business records that have no related record. Currently, admin users will have to go to the SAP Build Work Zone, advanced edition *Admin* \> *External Applications* section to manually re-import the `view_definition` to update and refresh the metadata and the annotations.
-   Related objects that are defined by using the extra "term" field from the annotation are not currently supported.
-   Related objects are also navigated to using only a single key `odata_link`.
-   Navigation to related objects can have filters. For example, a related object with a navigation of Opportunity may have a navigation URI of:

    ```
    "https://domain/EntitySet('00163E03A0701')/Opportunity?$format=json&$orderby=ChangedOn+desc&$top=20&$skip=20"
    ```

-   When determining what sort property to use when navigating a related Object, the related object's view definition is used to look up the sort properties.



## Related Objects for CRM:

We added more complex support for CRM objects by adding support for linked metadata and complex navigation to the `relatedItem` section of the view definition. CRM allows related external objects to be of different object types than the main external object in the group. `linkedMetadataUri` was added to allow identification of the object type to navigate to. A more complex navigation, with interpolated strings, was also added.

For example:

```
{
    "type": "relatedItem",
    "navigation": {
        "type": "interpolatedString",
        "pattern": "https://example.com/odata/ESJI_SD_SRV;o=QI3CLNT503_T/CustomerCollection(ObjectID='@{0}')/Quotations",
        "params": [
            {
                 "type": "oDataProperty",
                 "oDataType": "Edm.String",
                 "navigation": "CustomerNo"
            }
        ]
    },
        "entityType": "Quotation",
        "entityCollectionName": "QuotationCollection",
        "linkedMetadataUri": "https://example.com/odata/ESJI_SD_SRV;o=QI3CLNT503_T/$metadata#QuotationCollection"
    }
],
```

In this example, to work out what the navigation path is, retrieve the `CustomerNo`. Make a data call using the `linkedMetadataUri` to determine which external object type end point to call. Once the `CustomerNo` is retrieved from the data call, set the `ObjectID` as the `CustomerNo` to create the full URL. The full URL is then used to make a data call to get the related object.

For example, if `CustomerNo=5` is returned, then the URL we would call, constructed from this navigation pattern, would be:

```
"https://example.com/odata/ESJI_SD_SRV;o=QI3CLNT503_T/CustomerCollection(ObjectID='5')/Quotations"
```

For CRM, anytime there is linked metadata in the facet, two calls must be made to retrieve the related information.



## Featured business records

To support featured business records, the remote URI is called to get the data to support more complex filtering. To retrieve data for the list of the featured business record from the external site, we build a URI with a filter that selects all the business record ID keys. When building the filter, pay attention to single key vs multiple compounded keys. When the business record has a single key in the `odata_link`, use the property key to construct the filter with the ID. However, when a featured business record has multiple keys in the `odata_link`, it is not necessary to use the property key name with the filter.

Here are some examples of how the URI is created:

-   Retrieve one featured business record with a single key format, with a property key of "`OpportunityUUID`":
    -   `odata_link:` 

        ```
        https://example.com/OpportunityCollection('111111')
        ```

    -   `uri:` 

        ```
        https://example.com/OpportunityCollection(OpportunityUUID%20eq%20111111')
        ```


-   Retrieve multiple featured business record with a single key with a property key of "`OpportunityUUID`":
    -   featured business record 1 with `odata_link:` 

        ```
        https://example.com/OpportunityCollection('111111')
        ```

    -   featured business record 2 with `odata_link:` 

        ```
        https://example.com/OpportunityCollection('222222')
        ```

    -   `uri:` 

        ```
        https://example.com/OpportunityCollection(OpportunityUUID%20eq%20111111'%20or%20
            OpportunityUUID%20eq%20'222222')
        ```


-   Retrieve a featured business record with multiple keys, using the property keys already provided in the multi-key format, as follows:
    -   `odata_link:` 

        ```
        https://example.com/OpportunityCollection(ObjectID='111111',ObjectType="666666")
        ```

    -   `uri:` 

        ```
        https://example.com/OpportunityCollection(ObjectID%20eq%20111111'%20and%20ObjectType%20eq%20'666666')
        ```

    -   `uri with multiple objects with keys` 

        ```
        https://example.com/OpportunityCollection(ObjectID%20eq%20111111'%20and%20ObjectType%20
            eq%20'666666'%20or%20ObjectID%20eq%2022222'%20and%20ObjectType%20eq%20'666666')
        ```



Using filters is the most efficient way to get a list of items from the external application, as it requires only a single call to get the specified results quickly. This does require that the request must be limited to the maximum number of characters allowed in the URI request. Also, the request must be limited in terms of the volume of data that is returned.



## Examples

Assuming that it is acceptable for the application to expose Opportunities, Accounts, and Service Tickets, the following endpoints will be called.

-   **Getting Annotations:** This URI is from the `ex_obj_object` table.

    ```
    https://example.com/odata/v1/c4c.svc/AnnotationCollection('aa')/Content/$value
    ```

-   **Getting MetaData:** This URI is from the `ex_obj_object` table.

    ```
    https://example.com/odata/v1/c4c.svc/$metadata#ServiceRequestCollection
    ```

-   **Retrieving corporate account information from the Thing Inspector:** 

    ```
    https://example.com/odata/v1/c4c.svc/CorporateAccountCollection('00163E03A0701ED28B9DB004EAB8301D')/
        Opportunity?$format=json&$orderby=ChangedOn%20desc&$skip=0&$top=20
    ```

-   **Getting a list of objects for Opportunities using filters:** 

    ```
    https://example.com/odata/v1/c4c.svc/OpportunityCollection?$filter=
        (ObjectID%20eq%20'00163E03A0701ED28BCEC7F4AA474109’%20or
        %20ObjectID%20eq%20'00163E03A0701ED28BCEC8A91C8DE109’%20or
        %20ObjectID%20eq%20'00163E03A0701ED28BCFF0A51EBEC395’%20or
        %20ObjectID%20eq%20'00163E03A0701ED28BCFF155FFEDA395’%20or
        %20ObjectID%20eq%20'00163E03A0701EE28BE049992A5DA8DB')&$format=json
    ```


