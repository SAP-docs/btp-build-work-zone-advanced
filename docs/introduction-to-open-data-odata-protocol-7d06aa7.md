<!-- loio7d06aa71c08f475bb9663a873e859b69 -->

# Introduction to Open Data \(OData\) Protocol

This section provides an introduction to the Open Data \(OData\) protocol, which is a highly formalized implementation of the Representational State Transfer \(REST\) protocol.

The Open Data \(OData\) protocol is based on the Atom Publishing protocol. It provides a very formalized, well-defined approach to creating a ReSTful web API. The OData specification requires that APIs be available in either XML \(AtomPub\) or JSON formats. The SAP Jam OData API conforms to the OData version 2 specification, although it is subject to change in the ways allowed by the OData version 4 specification, with regard to adding new properties, navigations, and entity types. Every effort is made not to break backwards compatibility, but security issues that require a breaking change will be made.

The key specifications used in OData API development and usage are listed here for your reference:

1.  [odata.org](https://www.odata.org/)
2.  [OASIS-OPEN](https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=odata)
3.  [RFCs](https://www.ietf.org/standards/rfcs/)

This section contains the following pages of information:

-   Related information:
    -   [OData terminology](odata-terminology-c064ed8.md): is drawn from Atom \(XML\), JSON, and HTTP, although the usage is not always the same.
    -   [HTTP Methods](http-methods-ca47453.md)
    -   [HTTP headers](http-headers-43a48d5.md)
    -   [URLs and URL Parameters](urls-and-url-parameters-590de03.md)
    -   [Response Payload Data](response-payload-data-1bc51e9.md)
    -   [Understanding the OData $metadata file](understanding-the-odata-metadata-file-ac120ec.md): The OData `$metadata` file is a CSDL file that is made available to clients to help them discover an OData API's structure and organization.
    -   [Use of Curl Commands](use-of-curl-commands-7b1bb57.md): This tutorial uses curl commands to summarize the information that must be passed to make an effective API call. A **curl command** \(sometimes pronounced "see-URL"\) provides a concise view of exactly what elements have to be passed in the API call. This is most helpful if you are using `lib-curl` for your encoded API calls, although other options are available.


