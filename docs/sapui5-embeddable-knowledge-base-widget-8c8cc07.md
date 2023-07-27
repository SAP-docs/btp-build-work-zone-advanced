<!-- loio8c8cc0736d904eccad21d1a7473a8f07 -->

# SAPUI5 Embeddable Knowledge Base Widget

A highly customizable widget that can be embedded in SAPUI5 compatible applications to provide in-context access to relevant knowledge.



This widget supports:

-   Knowledge Base Articles as well as other content types such as wikis, documents, etc.
-   Customizations such as widget size, columns, sort options, labels, etc.



For example, when embedded in a service ticket application, the widget can provide the following benefits:

-   Recommend relevant KBAs depending on the context of the service ticket.
-   Provide advanced search with filters for category, tag, group, author, and multiple sort by options.
-   Enable users to directly view KBAs from within the service ticket experience.
-   Supports attaching the URL of a KBA to a service ticket and other KBA attributes supported by the `defaultColumns` property of this widget.



Use the instructions in the following tables to configure your knowledge base widget.



## Properties


<table>
<tr>
<th valign="top">

Name



</th>
<th valign="top">

Type



</th>
<th valign="top">

Default Value



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

DWSInstance



</td>
<td valign="top">

object



</td>
<td valign="top">

 



</td>
<td valign="top">

Parameters for configuring SAP Build Work Zone, advanced edition as a knowledge base repository.

The `DWSInstance` is required for searching Knowledge Base Articles or otherSAP Build Work Zone, advanced edition content. `contentSyndicationInstance` is the public community that has content syndication enabled for providing public links to the selected Knowledge Base.

The DWSInstance is required for searching Knowledge Base Articles or otherSAP Build Work Zone, advanced edition content. contentSyndicationInstance is the public community that has content syndication enabled for providing public links to the selected Knowledge Base.

1.  Generate an OAuth2 Bearer token.
2.  Use the OAuth2 Bearer token to generate a single use token.
3.  Use each single use token as shown in the examples below.

Example 1 - SAP Build Work Zone, advanced edition

```
DWSInstance: {
  uri: "https://{DWSInstance_domain}",
  singleUseToken: "{DWSInstance_singleUseToken}"
}
											
```

Example 2 - Communities

```
DWSInstance: {
  uri: "https://{DWSInstance_domain}",
  singleUseToken: "{DWSInstance_singleUseToken}",
  contentSyndicationInstance: {
    uri: "https://{contentSyndicationInstance_domain}",
    singleUseToken: "{contentSyndicationInstance_singleUseToken}",
    publicGroup: "{publicGroup_UUID}"
    }
}
											
```

> ### Note:  
> "publicGroup" must be a public workspace which has been configured as a content syndication target for the SAP Build Work Zone, advanced edition site.



</td>
</tr>
<tr>
<td valign="top">

contentTypes



</td>
<td valign="top">

string



</td>
<td valign="top">

\[kb, blog, wiki, document\]



</td>
<td valign="top">

Specify types of content in SAP Build Work Zone, advanced edition which can be searched in the widget. Available content types:

-   kb
-   blog
-   wiki
-   document



</td>
</tr>
<tr>
<td valign="top">

defaultColumns



</td>
<td valign="top">

string



</td>
<td valign="top">

\[title, group, author, updatedAt\]



</td>
<td valign="top">

Specify what columns of SAP Build Work Zone, advanced edition content to be displayed as search result. Available columns:

-   title
-   group
-   type
-   author
-   createdAt
-   updatedBy
-   updatedAt
-   likesCount
-   viewsCount
-   rating
-   tags
-   categories \(only for Knowledge Base Articles\)



</td>
</tr>
<tr>
<td valign="top">

jamGroups



</td>
<td valign="top">

string



</td>
<td valign="top">

empty string



</td>
<td valign="top">

If provided, search will be limited to these workspaces only. Default is empty so that the widget will search all available content in SAP Build Work Zone, advanced edition for the user.



</td>
</tr>
<tr>
<td valign="top">

defaultSearchMode



</td>
<td valign="top">

string



</td>
<td valign="top">

none



</td>
<td valign="top">

supported values:

-   none \(returns nothing if the searchFieldValue property is empty\).
-   all \(returns all the results if the searchFieldValue property is empty\).



</td>
</tr>
<tr>
<td valign="top">

widgetTitle



</td>
<td valign="top">

string



</td>
<td valign="top">

Suggestions from SAP Build Work Zone, advanced edition



</td>
<td valign="top">

Title of the widget.



</td>
</tr>
<tr>
<td valign="top">

widgetWidth



</td>
<td valign="top">

sap.ui.core.CSSSize



</td>
<td valign="top">

100%



</td>
<td valign="top">

Width of the widget.



</td>
</tr>
<tr>
<td valign="top">

widgetHeight



</td>
<td valign="top">

sap.ui.core.CSSSize



</td>
<td valign="top">

100%



</td>
<td valign="top">

Height of the widget.



</td>
</tr>
<tr>
<td valign="top">

previewWidth



</td>
<td valign="top">

sap.ui.core.CSSSize



</td>
<td valign="top">

1000px



</td>
<td valign="top">

Width of content preview panel.



</td>
</tr>
<tr>
<td valign="top">

previewHeight



</td>
<td valign="top">

sap.ui.core.CSSSize



</td>
<td valign="top">

700px



</td>
<td valign="top">

Height of content preview panel.



</td>
</tr>
<tr>
<td valign="top">

showAdvancedSearch



</td>
<td valign="top">

boolean



</td>
<td valign="top">

false



</td>
<td valign="top">

Set or get the visibility state of the Advanced Search section which contains custom keyword search and filters.



</td>
</tr>
<tr>
<td valign="top">

advancedSearchTitle



</td>
<td valign="top">

string



</td>
<td valign="top">

Advanced Search



</td>
<td valign="top">

Text of the Advanced Search section.



</td>
</tr>
<tr>
<td valign="top">

searchFieldPlaceholder



</td>
<td valign="top">

string



</td>
<td valign="top">

Search



</td>
<td valign="top">

Text inside custom keyword search box.



</td>
</tr>
<tr>
<td valign="top">

filterFields



</td>
<td valign="top">

string



</td>
<td valign="top">

\[types, groups, authors, categories\]



</td>
<td valign="top">

Specify the filters in Advanced Search section. Available filter fields:

-   types
-   groups
-   authors
-   categories
-   tags



</td>
</tr>
<tr>
<td valign="top">

sortFields



</td>
<td valign="top">

string



</td>
<td valign="top">

\[relevance, date\]



</td>
<td valign="top">

Specify sorting field and method. Available sort fields:

-   relevance
-   date
-   rating



</td>
</tr>
<tr>
<td valign="top">

actionColumnTitle



</td>
<td valign="top">

string



</td>
<td valign="top">

Action



</td>
<td valign="top">

Specify the title of column which display action buttons.



</td>
</tr>
<tr>
<td valign="top">

pageSize



</td>
<td valign="top">

int



</td>
<td valign="top">

20



</td>
<td valign="top">

Specify the title of column which display action buttons.



</td>
</tr>
<tr>
<td valign="top">

searchFieldValue



</td>
<td valign="top">

string



</td>
<td valign="top">

empty string



</td>
<td valign="top">

 



</td>
</tr>
</table>



## Aggregations


<table>
<tr>
<th valign="top">

Name



</th>
<th valign="top">

Cardinality



</th>
<th valign="top">

Type



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

buttons



</td>
<td valign="top">

0..n



</td>
<td valign="top">

sap.m.Button



</td>
<td valign="top">

The buttons in the action column.

If this aggregation is not set, the action column will be hidden. When you press the button, the, "selectedItem" parameter will be sent back to the event. "selectedItem" will contain the info for content.



</td>
</tr>
</table>



## Example for selectedItem

```

{
  "wzContentInfo": {
    "id": "GqBoZJElcNOXWpknW783Pg",
    "type": "Article",
    "title": "SAP Build Work Zone Content Sample",
    "content": "Content of SAP Build Work Zone Content Sample",
    "group": {
      "group_name": "Collaboration Content",
      "group_id": "x9z4xtZ26gpIqQYICVU5dX"
    },
    "tags": [],
    "categories": [],
    "creator": {
      "creator_name": "Carla Grant",
      "creator_id": "uD0JJ6GaHNbJPoHdRVlgTo"
    },
    "created_at": "2022-12-19T02:59:59Z",
    "updated_at": "2022-12-19T03:00:00Z",
    "is_deleted": false,
    "locale": null,
    "last_updated_by": {
      "updator_name": "Andrew Anderson",
      "updator_id": "uD0JJ6GaHNbJPoHdRVlgTo"
    },
    "href": "http://{DWSInstance_domain}/articles/GqBoZJElcNOXWpknW783Pg",   
    "views_count": 5,
    "likes_count": 0,
    "rating": 0
  },
  "syndicatedContentInfo": {
    "id": "IY7g2Qj38o5qOfErhYyGBu",
    "href": "http://{contentSyndicationInstance_domain}/articles/IY7g2Qj38o5qOfErhYyGBu",
    "group": {
      "group_name": "Community Group",
      "group_id": "YNvrWwb3igrJ5rEBqEQcHE"
    }
  }
}				
			
```



## How to setup the widget

1.  The widget library URL is at: `https://{DWSInstance_domain}/widget/jamWidget`
2.  Add the library to the project's resourceRoots:

    ```
    window["sap-ui-config"] = {
      ...
      
      resourceRoots: {
        "app": "app",
        "jam.widget": "https://{DWSInstance_domain}/widget/jamWidget" 
      },
      
      ...
    };											
    ```

3.  The widget id is "wzKBWidget". Render the widget as a standard SAPUI5 project:

    ```
    <mvc:View ...
        xmlns:jamWidget="jam.widget" >      
        
        <jamWidget:wzKBWidget id="wzKBWidget" DWSInstance="{/DWSInstance}" widgetWidth="auto" 
          widgetHeight="600px" pageSize="10" defaultColumns="title,group" >
          <Button text="Attach" press="handleAttach" >
        </jamWidget:wzKBWidget>
    
    </mvc:View>				
    ```


