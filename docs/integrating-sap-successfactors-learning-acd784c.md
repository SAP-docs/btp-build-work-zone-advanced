<!-- loioacd784c3d8804d7786bbeb0e5c4df0ca -->

# Integrating SAP SuccessFactors Learning

You can integrate SAP SuccessFactors Learning with SAP Build Work Zone, advanced edition.



SAP Build Work Zone, advanced edition supports external users who sign up for accounts through learning sites.



### Step 1: Configure the SAP SuccessFactors HCM Suite to work with SAP Build Work Zone, advanced edition

In your SAP SuccessFactors Human Capital Management \(HCM\) Suite, obtain the SAP SuccessFactors Learning OAuth token information required to enter in your SAP Build Work Zone, advanced edition configuration.

1.  Enable SAP Build Work Zone, advanced edition:

    1.  Log on to the SAP SuccessFactors HCM Suite and, from the main menu, select *Admin Center*.
    2.  In *Learning*, go to the *Learning Administration*.
    3.  From the top menu bar, choose *System Administration*, expand the *Configuration* section, and choose *System Configuration*.

        The `LMS_ADMIN` configuration file opens.

    4.  In the `LMS_ADMIN` configuration file, search for `jamIntegrationEnabled`, ensure that it’s set to *true*, and choose *Apply Changes*.

2.  To enable external users for SAP Build Work Zone, advanced edition, configure SAP SuccessFactors Platform and Learning as explained in [Offering Learning to the Extended Enterprise](https://help.sap.com/viewer/0bbc2f10849d4ead870477a29921746a/latest/en-US/46f4c0c8c557460a96d2e161625e5fc4.html).
3.  Get the OAuth information that is required for your SAP Build Work Zone, advanced edition configuration:
    1.  In the *System Administration* \> *Configuration* section, choose *OAuth Token Server*.

    2.  Choose *Generate a new client secret*.

        A new field displays under the *Client ID* field, labeled *Newly Generate Client Secret*.

        > ### Note:  
        > You can generate a new client secret at any time, but it’s the last generated client secret that you copy and paste into your SAP Build Work Zone, advanced edition configuration. Any newly generated client secret must be updated in all configurations in which this string is recorded as a newly generated client secret. The secret supersedes older secrets, and the client secret is typically required to establish a secure data connection.

    3.  Copy and save the following information to add to your SAP Build Work Zone, advanced edition configuration:

        -   **Client ID**
        -   **Newly Generated Client Secret**

        Make sure that you copy the information exactly, and don’t add any spaces before or after.





### Step 2: Register SAP SuccessFactors Learning as an External Application in SAP Build Work Zone, advanced edition

In SAP Build Work Zone, advanced edition, create an external application entry to register your external application. It’s required to set up a secure data connection with SAP SuccessFactors Learning as external business application.

1.  In the *Administration Console*, select *External Integrations* \> *External Solutions*.
2.  On the *External Applications* page, choose *Add Application* and select *SAP SuccessFactors Learning*.

    In the form, enter the following data:


    <table>
    <tr>
    <th valign="top">

    Setting


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Name*


    
    </td>
    <td valign="top">
    
    Enter a recognizable name, such as one that names the external application and its dedicated use. The name appears in the navigation and other locations.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *OAuth 2.0 Client Id*


    
    </td>
    <td valign="top">
    
    Enter the value from the OAuth token server page's *Client ID* field.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Secret*


    
    </td>
    <td valign="top">
    
    Enter the value from the OAuth token server page's *Newly Generated Client Secret* field.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Service Provider*


    
    </td>
    <td valign="top">
    
    Enter the fully qualified domain name \(FQDN\) of your SAP SuccessFactors Learning service and the port number. For example, `e0363.scdemo.successfactors.com:443`.

    A way to determine the FQDN is to log on to SAP SuccessFactors Learning on the web. In the browser, copy the base URL for the page. The base URL is everything between the `https://` protocol and before the next slash, which indicates the path. The path field is prefilled and can’t be edited.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Service Provider Name*


    
    </td>
    <td valign="top">
    
    This field is prefilled and can’t be edited.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Administrative Area*


    
    </td>
    <td valign="top">
    
    Select the administrative area in which you want SAP SuccessFactors Learning to be available. The default is *Company*, which makes it available to all work spaces.


    
    </td>
    </tr>
    </table>
    
3.  Choose *Create*.



### Step 3: Add an OAuth Client

To authorize SAP SuccessFactors Learning to access the SAP Build Work Zone, advanced edition API, you register SAP SuccessFactors Learning as an OAuth client for SAP Build Work Zone, advanced edition.

1.  In the *Administration Console*, in the *External Integrations* section, on the *OAuth Clients* page, choose *Add OAuth Client*.

    The *Register a new OAuth Client* form opens.

2.  Enter the following:


    <table>
    <tr>
    <th valign="top">

    Setting


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Name*


    
    </td>
    <td valign="top">
    
    You can keep the same name as you would have kept for your business record \(for example, LMS or Learning\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Integration URL*


    
    </td>
    <td valign="top">
    
    The URL for your Learning administration. Navigate to LMS admin and obtain the URL from the address bar.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *X509 Certificate \(Base64\)*


    
    </td>
    <td valign="top">
    
    Obtain under LMS admin settings from the LMS OAuth settings.


    
    </td>
    </tr>
    </table>
    



### Step 4: Register the SAP SuccessFactors Learning records in SAP Build Work Zone, advanced edition

For SAP SuccessFactors Learning, the following learning record types are supported: Item, Curriculum, Scheduled Offering, and Curriculum Assignment.

1.  In the *Administration Console*, on the *External Integrations* \> *External Applications* page, next to the SAP SuccessFactors Learning application for which you want to add records, choose *Action*, and select *Manage Record Types*.

    The *Manage <company\_name\> Learning Record Types* screen opens.

2.  Select the method for adding record types that you want to use:
    -   Select *Import Default Types* to retrieve the learning record types from the LMS server.

        The SAP Build Work Zone, advanced edition service immediately attempts to download the record types.

        An *Import Learning Record Types* page displays the results of the import attempt.

        If your SAP SuccessFactors Learning configuration is correct, all available record types import without problems. If you encounter problems, check your SAP SuccessFactors Learning configuration.

    -   Select *Import From File* if you receive a learning record types configuration file from SAP Build Work Zone, advanced edition Support or your contact.

        This option uses your browser file upload capability and configures your learning record types after they upload successfully.

    -   Select *Add Record Type*.

        The *Add Record Type* dialog box opens.

        1.  Choose *Add Record*.
        2.  Enter the appropriate values, as shown in the following tables, for the learning record type that you’re adding.

            **Values for the Item Learning Record Type**


            <table>
            <tr>
            <th valign="top">

            Setting


            
            </th>
            <th valign="top">

            Value


            
            </th>
            </tr>
            <tr>
            <td valign="top">
            
            Name


            
            </td>
            <td valign="top">
            
            Item


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            External Type


            
            </td>
            <td valign="top">
            
            `https://www.plateau.com/odata/v1/lms.svc/$metadata#ItemCollection`


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Annotation URL


            
            </td>
            <td valign="top">
            
            `https://www.plateau.com/odata/v1/lms.svc/AnnotationCollection`


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Can be featured or unfeatured in groups


            
            </td>
            <td valign="top">
            
            true


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Can be primary object in top-level group


            
            </td>
            <td valign="top">
            
            true


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Can be primary object in subgroup


            
            </td>
            <td valign="top">
            
            true


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Filter Feed


            
            </td>
            <td valign="top">
            
            true


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Feed History


            
            </td>
            <td valign="top">
            
            true


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Show Search


            
            </td>
            <td valign="top">
            
            true


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            \(Search\) Hint


            
            </td>
            <td valign="top">
            
            Title


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            \(Search\) Property


            
            </td>
            <td valign="top">
            
            Title


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Can be mentioned in feed posts


            
            </td>
            <td valign="top">
            
            true


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Primary \(Search\) Property


            
            </td>
            <td valign="top">
            
            Title


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Secondary \(Display Property


            
            </td>
            <td valign="top">
            
            Description


            
            </td>
            </tr>
            </table>
            
            **Values for the Curriculum Learning Record Type**


            <table>
            <tr>
            <th valign="top">

            Setting


            
            </th>
            <th valign="top">

            Value


            
            </th>
            </tr>
            <tr>
            <td valign="top">
            
            Name


            
            </td>
            <td valign="top">
            
            Curriculum


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            External Type


            
            </td>
            <td valign="top">
            
            `https://www.plateau.com/odata/v1/lms.svc/$metadata#CurriculumCollection`


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Annotation URL


            
            </td>
            <td valign="top">
            
            `https://www.plateau.com/odata/v1/lms.svc/AnnotationCollection`


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Can be featured or unfeatured in groups


            
            </td>
            <td valign="top">
            
            true


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Can be primary object in top-level group


            
            </td>
            <td valign="top">
            
            true


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Can be primary object in subgroup


            
            </td>
            <td valign="top">
            
            true


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Filter Feed


            
            </td>
            <td valign="top">
            
            true


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Feed History


            
            </td>
            <td valign="top">
            
            true


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            ExternalShow Search


            
            </td>
            <td valign="top">
            
            true


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            \(Search\) Hint


            
            </td>
            <td valign="top">
            
            Title


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            \(Search\) Property


            
            </td>
            <td valign="top">
            
            Title


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Can be mentioned in feed posts


            
            </td>
            <td valign="top">
            
            true


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Primary \(Search\) Property


            
            </td>
            <td valign="top">
            
            Title


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Secondary \(Display Property


            
            </td>
            <td valign="top">
            
            Description


            
            </td>
            </tr>
            </table>
            
            **Values for the Scheduled Offering Learning Record Type**


            <table>
            <tr>
            <th valign="top">

            Setting


            
            </th>
            <th valign="top">

            Value


            
            </th>
            </tr>
            <tr>
            <td valign="top">
            
            Name


            
            </td>
            <td valign="top">
            
            Scheduled Offering


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            External Type


            
            </td>
            <td valign="top">
            
            `https://www.plateau.com/odata/v1/lms.svc/$metadata#ScheduleOfferingCollection`


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Annotation URL


            
            </td>
            <td valign="top">
            
            `https://www.plateau.com/odata/v1/lms.svc/AnnotationCollection`


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Can be featured or unfeatured in groups


            
            </td>
            <td valign="top">
            
            true


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Can be primary object in top-level group


            
            </td>
            <td valign="top">
            
            true


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Can be primary object in subgroup


            
            </td>
            <td valign="top">
            
            true


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Filter Feed


            
            </td>
            <td valign="top">
            
            false


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Feed History


            
            </td>
            <td valign="top">
            
            false


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Show Search


            
            </td>
            <td valign="top">
            
            false


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Can be mentioned in feed posts


            
            </td>
            <td valign="top">
            
            false


            
            </td>
            </tr>
            </table>
            
            **Values for the Curriculum Assignment Learning Record Type**


            <table>
            <tr>
            <th valign="top">

            Setting


            
            </th>
            <th valign="top">

            Value


            
            </th>
            </tr>
            <tr>
            <td valign="top">
            
            Name


            
            </td>
            <td valign="top">
            
            Curriculum Assignment


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            External Type


            
            </td>
            <td valign="top">
            
            `https://www.plateau.com/odata/v1/lms.svc/$metadata#CurriculumAssignmentCollection`


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Annotation URL


            
            </td>
            <td valign="top">
            
            `https://www.plateau.com/odata/v1/lms.svc/AnnotationCollection`


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Can be featured or unfeatured in groups


            
            </td>
            <td valign="top">
            
            false


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Can be primary object in top-level group


            
            </td>
            <td valign="top">
            
            false


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Can be primary object in subgroup


            
            </td>
            <td valign="top">
            
            false


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Filter Feed


            
            </td>
            <td valign="top">
            
            false


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Feed History


            
            </td>
            <td valign="top">
            
            false


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Show Search


            
            </td>
            <td valign="top">
            
            false


            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            Can be mentioned in feed posts


            
            </td>
            <td valign="top">
            
            false


            
            </td>
            </tr>
            </table>
            
        3.  Save your entries.

            The record type that you just added is listed in the *<External\_App\_Name\> Record Types* catalog.




> ### Note:  
> Unlike other business record integrations, an SAP SuccessFactors Learning integration doesn’t allow you to set filtering. Filters are already provided for SAP SuccessFactors Learning Instructor-Led, Online, and Other Learning courses.
> 
> Similarly, setting a sort order in which the external data is arranged in a particular external application data object has no relevance.
> 
> As you don’t set filters or sort fields for SAP SuccessFactors Learning, you can now create a workspace for your SAP SuccessFactors Learning business records.

> ### Note:  
> For a curriculum without courses, the business record browser displays a hover card or attribute showing an error, because the LMS API returns an error. Return to the SAP SuccessFactors HCM Suite and select *Admin Center* from the main menu, and add courses to the curriculum.

As a learning administrator, you can also integrate learning programs with SAP Build Work Zone, advanced edition workspaces and their content. For information about the SAP Build Work Zone, advanced edition tile within the SAP SuccessFactors Learning Program, see [Associating Learning Programs with SAP Jam Groups](https://help.sap.com/docs/SAP_SUCCESSFACTORS_LEARNING/5fae31b1299d4033b665edabea7b9087/0144ea8efb944abe9cdbebb878ad9c84.html) in the *SuccessFactors Learning Administration Help*.

**Related Information**  


[Add an OAuth Client](add-an-oauth-client-b3c804e.md)

