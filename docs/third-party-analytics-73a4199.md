<!-- loio73a4199fff3b474db0694f03adc2c2d3 -->

# Third-Party Analytics

You can use traffic analytics on page view level to gather metrics such as the number of page visitors by unit of time, usage patterns, or content interaction.

In the *Administration Console* under *Analytics* \> *Third Party Analytics*, you enable a supported third-party clickstream analytics solution.

> ### Note:  
> Google Analytics is currently supported.



<a name="loio73a4199fff3b474db0694f03adc2c2d3__section_h2j_5lj_4kb"/>

## About Google Analytics

Google Analytics works by including a block of Google’s JavaScript code on pages in SAP Build Work Zone, advanced edition. When users visit and navigate in SAP Build Work Zone, advanced edition, the JavaScript code references a JavaScript file, which then executes the tracking operation for analytics. The tracking operation retrieves data about the page request and sends this information to the analytics server.

Google Analytics can provide information such as:

-   How much time a user spends on your site
-   How much time a user spends on each page \(includes page title and URL\)
-   The sequence in which pages were visited
-   Geographic location of the user
-   Browser, operating system, and device usage

    > ### Note:  
    > Although Google Analytics can collect IP addresses from the user, they aren’t made available to Google Analytics tools.


> ### Note:  
> Choose the option *Remove PII from page title* if you want to prevent Google Analytics from collecting personally identifiable information \(PII\), such as the users' names, from page titles, such as the titles of profile pages and inbox items.

For more information about Google Analytics, see the Google Analytics documentation.



