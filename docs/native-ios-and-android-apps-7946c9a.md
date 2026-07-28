<!-- loio7946c9a5801d48bba0f63de3ca02877f -->

# Native iOS and Android Apps

The properties required to configure a native iOS or Android app, which can be viewed and launched from the Joule Work mobile app client.



## Property Description

The following table describes the values of the properties that are required to configure a native app.


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

URL to Install App

</td>
<td valign="top">

The URL required to install the native app.

The user is referred to this link if the app is not installed on the device of the user. The URL would typically lead to the Apple App Store, Google Play, or an Enterprise App Store.

</td>
</tr>
<tr>
<td valign="top">

URL to Launch App

</td>
<td valign="top">

The URL required to launch the native app.

</td>
</tr>
</table>

The following table provides example URLs of SAP SuccessFactors Mobile app screens for both iOS and Android:


<table>
<tr>
<th valign="top">

Operating System

</th>
<th valign="top">

URL to Install App

</th>
<th valign="top">

URL to Launch App

</th>
</tr>
<tr>
<td valign="top">

iOS

</td>
<td valign="top">

[https://apps.apple.com/de/app/successfactors/id426562526](https://apps.apple.com/de/app/successfactors/id426562526) 

</td>
<td valign="top">

`bizx://?urlType=deeplink&amp;deeplinkType=profile`

</td>
</tr>
<tr>
<td valign="top">

Android

</td>
<td valign="top">

[https://play.google.com/store/apps/details?id=com.successfactors.successfactors](https://play.google.com/store/apps/details?id=com.successfactors.successfactors) 

</td>
<td valign="top">

`bizx://?urlType=deeplink&amp;deeplinkType=profile`

</td>
</tr>
</table>

> ### Note:  
> In the Visualization tab, the *Device Types* – *Desktop*, *Mobile*, *Tablet* – are all selected, because native apps can run on Mac desktops, mobile phones, and tablets.

**Related Information**  


[Setting Up the Joule Work Mobile App](setting-up-the-joule-work-mobile-app-3257133.md "In this topic, we explain how to set up the Joule Work mobile app on SAP Build Work Zone, advanced edition and SAP SuccessFactors Work Zone.")

