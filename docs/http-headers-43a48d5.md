<!-- loio43a48d5b471e432aa7fd6e9c8bb44f78 -->

# HTTP headers

HTTP headers are used to specify several aspects of an API call's operation.

The HTTP headers used by the SAP Build Work Zone, advanced edition OData API include:

-   **Authorization: OAuth \{OAuth1.0a\_protocol\_parameters\}** This provides user authorization using OAuth 1.0a, for example:

    ```sh
    Authorization: OAuth oauth_consumer_key="J2iLG8a8xZPtqBIfHjIm", oauth_nonce="RPUt7ytQ9w",
    oauth_signature_method="HMAC-SHA1", oauth_timestamp="1316135320", oauth_version="1.0",
    oaccess token="vbXkQoSkIqyYIxwI2I2u", oauth_signature="P5scFJf6CZlBBMELB9kb%2FvM0ktQ%3D"
    ```

-   **Authorization: Bearer \{OAuth\_bearer\_token\}** This provides user authorization using OAuth 2.0, for example:

    ```sh
    Authorization: Bearer As3UvIaYEvDXoeREtmSz3qeCpnNvrrHZhVMswcBV
    ```

-   **Accept: \{application/json|application/atom+xml\}** This header allows you to specify what is an acceptable response to your API call: the XML or JSON format. This option is preferred to using a query option of `?$format=json`. Note that the default format for OData API calls is XML, so that does not need to be specified unless you want to use JSON. To do so, specify that responses be in JSON format in the HTTP `Accept` header. For example:

    ```
    Accept: application/json
    ```

    The XML option, while not required, would be:

    ```
    Accept: application/atom+xml
    ```

-   **ContentType: \{MIME\_type\}** Informs the API that you are sending content in a specific format in the request. This must be specified as the MIME type for the content that you are submitting. Valid options include:

    -   `application/json`
    -   `application/atom+xml`
    -   `text/html`
    -   `text/html;type=wiki`
    -   `text/html;type=blog`
    -   `image/png`
    -   `image/jpg`
    -   `video/mp4`
    -   `application/vnd.ms-powerpoint`
    -   `application/vnd.openxml-formats-officedocument.presentationalml.presentation`

    For example:

    ```sh
    ContentType: image/png
    ```

    The above examples are all valid, but the list of supported MIME types is far from complete.

-   **SAP-JAM-CONTENT-ADMINISTRATION: \{true\}** This header allows company administrators to enable content administration on their company for this request. With content administration enabled, company administrators can perform CRUD operations to all workspaces and content within their company regardless of workspace membership.
    -   **Example 1** - Show all Content Items in a workspace that the company administrator is not a member of.

        ```
        
        Request Url: GET {{api_url}}/Groups('{{Id}}')/AllContentItems
        Header: Authorization: Bearer {OAuth_bearer_token}
        Header: SAP-JAM-CONTENT-ADMINISTRATION: true
        
        ```

    -   **Example 2** - Search for all Content Items in a workspace that the company administrator is not a member of.

        ```
        
        Request Url: GET {{api_url}}/Search?Query='{{search_item}}'
        Header: Authorization: Bearer {OAuth_bearer_token}
        Header: SAP-JAM-CONTENT-ADMINISTRATION: true
        
        ```

    -   **Example 3** - Delete an item in a workspace that the company administrator is not a member of.

        ```
        
        Request Url: DELETE {{api_url}}/ContentItems(Id='{{Id}}',ContentItemType='{{Type}}')
        Header: Authorization: Bearer {OAuth_bearer_token}
        Header: SAP-JAM-CONTENT-ADMINISTRATION: true
        
        ```


-   **Slug: \{file\_name\_without\_extension\}** "Slug" is an HTTP header used in the OData API as the name of the file used in SAP Build Work Zone, advanced edition. In an upload \(a POST\), the Slug header would be set as "`profilePhoto`" if that is the name you want the resource to appear as in SAP Build Work Zone, advanced edition. In an update \(a PATCH\) or a download \(a GET\), the Slug header would be set as "`profilePhoto`" if you want to update \(re-upload\) or download a file of that name in SAP Build Work Zone, advanced edition. For example:

    ```
    Slug: profilePhoto
    ```


