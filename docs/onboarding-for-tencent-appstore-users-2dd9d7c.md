<!-- loio2dd9d7cc682f44c091d70afa0a95d461 -->

# Onboarding for Tencent Appstore Users

Users of Android devices sold in Mainland China can download the SAP Build Work Zone mobile app from the Tencent Appstore. You have to provide them with the link for the registration of the mobile app.

If a user has an Android device sold in Mainland China and has downloaded the SAP Build Work Zone, advanced edition app from the Tencent Appstore, the scanning of the QR code for the registration with the camera of their phone usually doesn't work. As an administrator, you have to provide the link in the QR code as follows:

1.  Open SAP Build Work Zone, advanced edition on a desktop computer and in the User Actions menu and choose *Settings* \> *Mobile Application*.

2.  Choose *Android* and choose *Registration*.

3.  To get the link in the QR code for the registration, you can use one of the following options:

    -   Parse the link with a third-party QR code scanner.

    -   Get the link through the inspect function of a web browser.

        For example, in Google Chrome for desktop, right-click on the QR code and choose *Inspect*.


4.  Send the registration link to your users in an email.

    The users to have the app installed first. When they open the email on their mobile phone, they can choose the link the email to register for the mobile app.


If the link in the email doesn't work for your users, you can do the following:

1.  Generate an HTML file such as the following:

    > ### Note:  
    > The following sample code is just an example. For your own HTML file, you have to take the values that you find when you inspect the QR code using the inspect function of a web browser.

    > ### Sample Code:  
    > ```
    > <html>
    >  
    > <head>
    > <meta http-equiv=Content-Type content="text/html; charset=UTF-8">
    > </head>
    >  
    > <body lang=en-CN link="#0563C1" vlink="#954F72" lang=EN-US
    > style='font-size:16.0pt;font-family:sans-serif'>
    > <div>
    > <a target="_blank"
    > href="dwpmobile://?AppId=com.sap.mobile.platform.workzone&ClientId=cfb755ab-269d-44fc-9da1-4a2d67f24454&SapCloudPlatformEndpoint=https://swzqa.mobile.bwpvalidation.workzone.cfapps.sap.hana.ondemand.com&AuthorizationEndpointUrl=https://swzqa.mobile.bwpvalidation.workzone.cfapps.sap.hana.ondemand.com/oauth2/api/v1/authorize&RedirectUrl=https://swzqa.mobile.bwpvalidation.workzone.cfapps.sap.hana.ondemand.com&TokenUrl=https://swzqa.mobile.bwpvalidation.workzone.cfapps.sap.hana.ondemand.com/oauth2/api/v1/token">The Registration Link</a>
    > <hr>
    > <p>The OnBoarding Url is</p>
    > <p>dwpmobile://?AppId=com.sap.mobile.platform.workzone&ClientId=cfb755ab-269d-44fc-9da1-4a2d67f24454&SapCloudPlatformEndpoint=https://swzqa.mobile.bwpvalidation.workzone.cfapps.sap.hana.ondemand.com&AuthorizationEndpointUrl=https://swzqa.mobile.bwpvalidation.workzone.cfapps.sap.hana.ondemand.com/oauth2/api/v1/authorize&RedirectUrl=https://swzqa.mobile.bwpvalidation.workzone.cfapps.sap.hana.ondemand.com&TokenUrl=https://swzqa.mobile.bwpvalidation.workzone.cfapps.sap.hana.ondemand.com/oauth2/api/v1/token
    > </p>
    > </div>
    > </body>
    >  
    > </html>
    > ```

2.  Send the HTML file to your users as an attachment in an email or share it with them in another way.


