<!-- loioc064ed8eab9643b5b5e0b380e2653bba -->

# OData terminology

OData terminology is a bit confusing as it is drawn from its various constituent technologies, which don't always use the same terms.

To illustrate these issues, the common OData terms, as well as some approximate equivalents from Atom \(XML\), JSON, and HTTP usage are shown in the following table.


<table>
<tr>
<th valign="top">

OData \(with definition\)



</th>
<th valign="top">

Atom \(XML\)



</th>
<th valign="top">

JSON



</th>
<th valign="top">

HTTP



</th>
</tr>
<tr>
<td valign="top">

**property**: an attribute-value pair that describes a single quality of a resource



</td>
<td valign="top">

property



</td>
<td valign="top">

property



</td>
<td valign="top">

\(no equivalent\)



</td>
</tr>
<tr>
<td valign="top">

**entity, resource, or object**: a network-accessible data object or service that can be identified by a URI; typically a resource is described by a predefined set of properties \(from HTTP\)



</td>
<td valign="top">

entry \(also used in OData\)



</td>
<td valign="top">

object



</td>
<td valign="top">

resource \(entity differs\)



</td>
</tr>
<tr>
<td valign="top">

**EntityType**: the abstract data model of a type of resource



</td>
<td valign="top">

\(no equivalent\)



</td>
<td valign="top">

\(no equivalent\)



</td>
<td valign="top">

\(no equivalent\)



</td>
</tr>
<tr>
<td valign="top">

**collection**: a set of resources, often returned to a GET request for a certain type of resource



</td>
<td valign="top">

feed



</td>
<td valign="top">

array of objects



</td>
<td valign="top">

\(no equivalent\)



</td>
</tr>
</table>

Additional terms relevant to OData API usage are:

-   **Collection-valued API calls**: are API GET calls to an entity that do not specify a single resource, such as `[GET] /Groups`. These calls will return a feed or collection of resources. For example, the Groups that the currently logged-in user has access to.
-   **Binary Large Objects \(BLOB\)**: are binary data that is stored as a single entity \(a file\), typically graphics, videos, office documents, and PDFs.

    The OData specification describes [Creating Media Link Entries \(MLEs\)](http://www.odata.org/documentation/odata-version-2-0/operations#CreatingMediaLinkEntries) in section 2.5 of the Operations page.

    Note that API clients should be able to follow redirect responses, which are required to improve the performance of Content Distribution Networks \(CDN\).


For more information, see [OData Terminology](http://www.odata.org/documentation/odata-version-2-0/terminology/).

