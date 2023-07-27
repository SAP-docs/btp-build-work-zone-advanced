<!-- loioe736d637660b40bfbdb17fc35344b733 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Upgrade a Content Package

When there's a new version of a content package, you need to upgrade it.

When there’s a new version of a content package available, the status of your content packages changes to Upgrade Available. There are 2 scenarios when a new version is available:


<table>
<tr>
<td valign="top">

For globally provided content packages



</td>
<td valign="top">

In this case, the provider of the content package \(SAP or a third party\), has uploaded a newer version to the content repository.

> ### Note:  
> The provider of a global content package can modify the package and upload it as a local version to test it before publishing to the content repository.



</td>
</tr>
<tr>
<td valign="top">

For locally provided content packages



</td>
<td valign="top">

In this case, the content package that was created locally has been updated, and then manually uploaded again using the *Upload Content Package* button.

> ### Note:  
> You can't upload a content package with the same or lower version than what you have.



</td>
</tr>
</table>

In both scenarios, you can determine when to be notified when a major, minor, or patch upgrade is available. The developer of the content package can set one of these options as the default or you can customize the notification by selecting one of the other options available.

> ### Note:  
> If the upgrade fails, click *Download Report* to view the error log and try resolving the problem. Sometimes, the provider of a content package provides a link to get support. If this is the case, you'll see a *Get Support* button next to the error message.


<table>
<tr>
<th valign="top">

Version update option



</th>
<th valign="top">

What does it mean?



</th>
</tr>
<tr>
<td valign="top">

Default value



</td>
<td valign="top">

In this case, the developer of the content package has set one of the options below as the default option. The user can then override this default value by selecting one of the options in the rows below. This affects the current version of the content package and any future versions of it.



</td>
</tr>
<tr>
<td valign="top">

Automatic update for all versions



</td>
<td valign="top">

Each time there's a new version - whether it's a major, minor, or a patch update, the content package is upgraded automatically. You won't get notified that a new version is available, but you'll see that the version number of the content package has changed.



</td>
</tr>
<tr>
<td valign="top">

Automatic update for Minor and Patch versions only



</td>
<td valign="top">

When there are minor or patch updates, the content package is upgraded automatically without a notification. You'll see that the version number of the content package has changed.

When there’s a major update, an *Upgrade Available* banner displays at the top of your content package and you can manually install.



</td>
</tr>
<tr>
<td valign="top">

Automatic update for Patch version only



</td>
<td valign="top">

When there’s only a patch update, the content package is upgraded automatically without a notification. You'll see that the version number of the content package has changed. When there are major or minor updates, an *Upgrade Available* banner displays at the top of your content package and you can manually install.



</td>
</tr>
<tr>
<td valign="top">

Manual update



</td>
<td valign="top">

Each time there's a new version - whether it's a major, minor, or a patch update, an *Upgrade Available* banner displays at the top of your content package and you’ll need to manually install.



</td>
</tr>
</table>

When there's a new version of the content package available \(global or local\), click :arrows_clockwise: on the content package tile.

> ### Note:  
> When you select to upgrade an installed content package, before you actually initiate the upgrade process, you'll get a popup window showing the details of what's been changed in the upgraded content package. You can either continue with the upgrade or cancel it.

