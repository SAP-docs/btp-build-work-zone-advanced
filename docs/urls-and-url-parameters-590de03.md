<!-- loio590de03916cd4398a6e270d27ab16a10 -->

# URLs and URL Parameters

OData APIs are accessed via a URL that calls a specific endpoint and has the required URL parameters properly set. There are different forms of URL for each of several specific types of operation.

The most basic API call specifies an entity, but not a specific resource. This is done for POST operations where a new resource has not yet been assigned a unique ID bySAP Build Work Zone, advanced edition, and in collection-valued GET requests, from which you want to retrieve a collection \(or feed\) of the available resources of that entity type.



<a name="loio590de03916cd4398a6e270d27ab16a10__serviceroot"/>

## Service Root

Identifies the data center or server of an OData service and location of the API in that data center or server. A generalized form of the service root URI is shown for theSAP Build Work Zone, advanced edition OData API.



<a name="loio590de03916cd4398a6e270d27ab16a10__resourcepath"/>

## Resource Path

Identifies the resource to be interacted with specified by its unique ID.

Note that the combination of the HTTP method and a generalized form of the resource path is used as the signature of the endpoints in the SAP Build Work Zone, advanced edition OData API.



<a name="loio590de03916cd4398a6e270d27ab16a10__jamnumber"/>

## Data Center

SAP Build Work Zone, advanced edition is located in a data center. Your organization's subscription to SAP Build Work Zone, advanced edition must appear in the URL of your API calls.



<a name="loio590de03916cd4398a6e270d27ab16a10__uuid"/>

## Unique IDs

To identify a specific resource, the SAP Build Work Zone, advanced edition OData API uses 22-character unique identifiers for the various accessible objects in SAP Build Work Zone, advanced edition.

For most entities, the unique ID alone is sufficient to identify a specific resource, but for some entities two attribute-value pairs are required. These one or two properties are commonly termed the "key" for the resource, and the key value, or values, must be set in the URL of an API call to indicate exactly which resource to perform the API call operation on. The entities that require two attribute-value pairs to identify a specific resource, and the attributes that they use are as follows:

-   `ContentItem(Id='{Id}',ContentItemType='{ContentItemType}')`, where the '\{ContentItemType\}; can be "Page", "BlogEntry", "Document", "Tool", or "Poll".
-   `ContentListItem(Id='{Id}',ContentListItemType='{ContentListItemType}')`, where the \{ContentListItemType\} can be "Page", "BlogEntry", "Document", "Tool", or "Poll".
-   `EventResponse(RepondentId='{RespondentId}',EventId='{EventId}')`
-   `Folder(Id='{Id}',FolderType='{FolderType}')`, where the \{FolderType\} can be "Folder" or "PrivateFolder".
-   `GroupExternalObject(GroupId='{GroupId}',ExternalObjectId='{ExternalObjectId}')`
-   `GroupMembership(GroupId='{GroupId}',MemberId='{MemberId}')`
-   `GroupTemplate(Id='{Id}',GroupTemplateType='{GroupTemplateType}')`, where the \{GroupTemplateType\} can be "system" or "custom".
-   `Kudo(Id='{Id}',KudoType='{KudoType}')`, where the \{KudoType\} can be "system" or "custom".
-   `ObjectReference(Id='{Id}',Type='{Type}')`, where the \{Type\} can be "Member", "Group", "WallComment", "Event", "Task", "MemberKudo", "Comment", "FeedEntry", "ForumItem", or "ContentItem".
-   `TaskAssignment(AssigneeId='{AssigneeId}',TaskId='{TaskId}')`
-   `ThumbnailImage(Id='{Id}',ThumbnailImageType='{ThumbnailImageType}')`, where currently the only valid value for \{ThumbnailImageType\} is "48x48".
-   `ThumbnailKudoImage(Id='{Id}',ThumbnailImageType='{ThumbnailImageType}')`, where currently the only valid value for \{ThumbnailImageType\} is "48x48".

For the specification reference, see [https://www.odata.org/documentation/](https://www.odata.org/documentation/).



<a name="loio590de03916cd4398a6e270d27ab16a10__navigations"/>

## Navigations

Navigations are URL extensions from the base entity to closely related entities. They can be named according to their "role", for example, one navigation from the Group entity is to a "Creator", which is the role, but which returns the "Member" information on the individual who created the workspace. Every entity has a predefined set of navigations. For example, the Group entity has the following navigations:

-   Role: AllContentItems \(Entity: ContentItem\)
-   Role: AllDiscussions \(Entity: Discussion\)
-   Role: AllFolders \(Entity: Folder\)
-   Role: AllIdeas \(Entity: Idea\)
-   Role: AllQuestions \(Entity: Question\)
-   Role: ContentItems \(Entity: ContentItem\)
-   Role: ContentListItems \(Entity: ContentListItem\)
-   Role: Creator \(Entity: Member\)
-   Role: FeaturedExternalObjects \(Entity: ExternalObject\)
-   Role: FeedEntries \(Entity: FeedEntry\)
-   Role: Folders \(Entity: Folder\)
-   Role: Forums \(Entity: Forum\)
-   Role: Memberships \(Entity: GroupMembership\)
-   Role: ParentGroup \(Entity: Group\)
-   Role: PrimaryExternalObject \(Entity: ExternalObject\)
-   Role: PrimaryGadgetObject \(Entity: GroupGadgetObject\)
-   Role: ProfilePhoto \(Entity: Image\)
-   Role: SubGroups \(Entity: Group\)
-   Role: Tasks \(Entity: Task\)
-   Role: Template \(Entity: GroupTemplate\)
-   Role: UpcomingEvents \(Entity: Event\)



<a name="loio590de03916cd4398a6e270d27ab16a10__queryoptions"/>

## Query Options

Query options are URL parameters that are added to the end of the URL.

There are three general types of query options:

-   **System query options**: are indicated with a preceding dollar sign "$".
-   **Custom query options**: are not used in the SAP Build Work Zone, advanced edition OData API, and so they are not discussed any further here.
-   **Service operation parameters**: are the required parameters for service operations, which are discussed at greater length below.

The SAP Build Work Zone, advanced edition OData API supports OData system query options with a number of limitations to ensure system responsiveness.

For more information about the following bullets, see [https://www.odata.org/documentation/](https://www.odata.org/documentation/):

-   There can be at most one Collection-valued navigation in an OData request.
-   There can be at most 3 `$expand` operations in one API call. Using `$expand` on a Collection valued navigation of a Collection is not allowed.

    Use `$expand` to include details on any property for which there are available navigations.

-   Using `$filter` is currently only supported for select properties of the following entities:

    -   **ContentItem:** ContentItemType
    -   **ContentListItem:** Name
    -   **ExternalObject:** Exid, ObjectType
    -   **Folder:** Name
    -   **FeedEntry:** Read
    -   **ForumItem:** ForumItemType
    -   **Group:** Id, Name, IsActive, GroupType
    -   **GroupExternalObject:** LinkType
    -   **GroupMembership:** MemberType
    -   **Idea:** Status
    -   **Notification:** Category, EventType
    -   **Question:** HasBestAnswer
    -   **Task:** IsOverdue
    -   **TaskAssignment:** Status

    Use `$filter` to limit the entries returned according to their content.

-   SAP Build Work Zone, advanced edition will never return arbitrarily large collections. Either server-driven paging \(use `$skiptoken`\) or client-driven paging \(use `$skip`\) will apply. Certain endpoints only support server-driven paging \(`$skiptoken`\). In general, a maximum of 20 items will be returned, unless a value of `$top` is specified \(and supported\), in which case the maximum value is 100.
    -   Use `$skip` to offset the set of entries returned.
    -   Use `$skiptoken` to offset the set of entries returned.
    -   Use `$top` to set the number of entries returned.

-   For FeedEntries and Notifications API calls, `$skip`, `$top`, and `$count` are not available. Also, `$count` is not available for GroupMembership API calls, and `$orderby` is not available for FeedEntries and Notifications, but it will be selectively available where the items are sortable in the SAP Build Work Zone, advanced edition user interface.
    -   Use `$skip` to offset the set of entries returned.
    -   Use `$top` to set the number of entries returned.
    -   Use `$count` to discover how many entries there are.
    -   Use `$orderby` to set the criteria that the returned entries are ordered by.




<a name="loio590de03916cd4398a6e270d27ab16a10__serviceOperations"/>

## Service Operations

In practice, a service operation is any endpoint that performs a required task that does not fit with the usual POST, GET, PATCH, or DELETE operations. InSAP Build Work Zone, advanced edition's implementation, service operations are signified by using underscores between words in the endpoint name rather than showing the name in camel-case. There are, however, at least four exceptions: `[GET] /Self`, `[GET] /Company`, `[GET] /Search`, and `[GET] /SearchSummary`.

For more information about service operations you can check the $metadata file. Each service operation is described to some extent in that file.

For the technical specification for a service operation, see [https://www.odata.org/documentation/](https://www.odata.org/documentation/).



<a name="loio590de03916cd4398a6e270d27ab16a10__linksBetweenEntries"/>

## Links Between Entries

The OData specification allows for the creation of links between entries.

For example, in the SAP Build Work Zone, advanced edition OData API, currently logged-in Member can be set as "Following" another specified Member by setting a "$link" from the Member to be followed to "Following", which will take the Id of the currently logged-in Member as the "follower".

There are a small number of such operations available in the SAP Build Work Zone, advanced edition OData API, but they are important operations. They include:

-   `[POST] /Members('{id}')/$links/Following`
-   `[DELETE] /Members('{id}')/$links/Following('{id1}')`
-   `[POST] /Questions('{id}')/$links/BestAnswer`
-   `[DELETE] /Questions('{id}')/$links/BestAnswer`
-   `[POST] /Groups('{id}')/$links/FeaturedExternalObjects`
-   `[DELETE] /Groups('{id}')/$links/FeaturedExternalObjects('{id1}')`
-   `[POST] /Events('{id}')/$links/Invitees`
-   `[POST] /Tasks('{id}')/$links/Attachments`
-   `[DELETE] /Tasks('{id}')/$links/Attachments('{id1}')`
-   `[POST] /Tasks('{id}')/$links/PendingFollowers`

