<!-- loio7b1bb579c02d435ebe590f85c8f502a1 -->

# Use of Curl Commands

This tutorial uses curl commands to summarize the information that must be passed to make an effective API call. A **curl command** \(sometimes pronounced "see-URL"\) provides a concise view of exactly what elements have to be passed in the API call. This is most helpful if you are using `lib-curl` for your encoded API calls, although other options are available.

The curl command options are always shown is the same order so that you can quickly evaluate what the different requirements are for each call. These options and their order are:

-   `-i` — \(include \[the HTTP header\]\) **\[curl only\]**: includes the HTTP responses, some server information, and some request and response data in the response. \(Note that none of this information is shown in any of the examples in this tutorial.\)
-   `-H "Authorization: Bearer <!--[An OAuth2.0 access token has been removed from here.]-->"` — \(header\) **\[Required\]**: the SAP Build Work Zone, advanced edition OData API requires either OAuth 1.0a or 2.0 authentication to respond to an API call.
-   `-H "Content-Type: application/{atom+xml|json}"` — \(header\) **\[Required for POST and PATCH requests\]**: indicates the MIME type of the body of the request or of the file to be uploaded.
-   `-H "Accept: application/{atom+xml|json}"` — \(header\) **\[Optional\]**: indicates the acceptable Content-Types for the response. OData APIs default to XML, so if you want JSON, you must either specify it in this header or set that as a query option in the URL.
-   `-H "Stub: {file_name}"` — \(header\) **\[Required for API calls that upload of download files \(POSTs or PATCHes and GETs\)\]**: indicates the filename \(less the extension\) that will be used in SAP Build Work Zone, advanced edition for an uploaded file.
-   `-X {POST|PATCH|DELETE}` — \(request\) **\[Required for POSTs, PATCHes, and DELETEs\]**: used to indicate some other HTTP method than GET, which is the default if this option is not specified.
-   `"{the_API_call_URL}"` \(URL\) — **\[Required\]**: this must be the full URL of the API call.
-   `-d` — \(data\) **\[Required for POSTs and PATCHes\]**: this is the data used to create \(POST\) or update \(PATCH\) a resource. The `-d` option is typically formed in one of the following ways:
    -   `-d "{ \"Name\":\"Customer Requests Discussions Group\" }"` — a short bit of JSON data included in the curl command.
    -   `-d "<Name>Customer Requests Discussion Group</Name>"` — a short bit of XML data included in the curl command.
    -   `-d@C:/{path_to_payload_file}/{payload_file_name}.json` — a longer bit of JSON content sent in a payload file.
    -   `-d@C:/{path_to_payload_file}/{payload_file_name}.xml` — a longer bit of XML content sent in a payload file.

-   `-x <proxy.myorg.com:8080>` — \(proxy\) **Required only if your network is behind a web proxy.** Should show the host, subdomain, domain, and port of the proxy. The proxy option is not shown in any examples in this tutorial, but it may be required to work in your organization.

