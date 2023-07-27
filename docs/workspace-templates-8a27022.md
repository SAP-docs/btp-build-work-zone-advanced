<!-- loio8a27022a34b446e99261304d80d9109b -->

# Workspace Templates

Workspace templates enable users to create workspace content quickly and consistently.

The following out-of-the-box workspace templates are available by default.

> ### Note:  
> Additional templates can be created manually or become available via content packages.


<table>
<tr>
<th valign="top">

Template



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

*Account Management Template*

Available from Business Records page.



</td>
<td valign="top">

Designed to support collaboration and decision-making for a single account. Displays up-to-date account information, including opportunities and service requests.

> ### Note:  
> This template is available for SAP Cloud for Customer only.



</td>
</tr>
<tr>
<td valign="top">

*Customer Engagement Template* 



</td>
<td valign="top">

Designed to support vendor and customer engagements to help close a sales opportunity for example.



</td>
</tr>
<tr>
<td valign="top">

*Education Center Template* 



</td>
<td valign="top">

Designed for subject-matter experts and students to collaborate and discuss training courses and to create and share content and knowledge.

Users can use search, activity feeds, tags, most-viewed, most-liked, and featured content to find the experts or content they need.



</td>
</tr>
<tr>
<td valign="top">

*Help and Support Template* 



</td>
<td valign="top">

Designed as an internal-facing Q&A for members and experts to help each other on a particular topic of interest.

Most sections of the template would be questions within forums.



</td>
</tr>
<tr>
<td valign="top">

*Knowledge Sharing Template* 



</td>
<td valign="top">

Designed for experts and coaches to help them connect and share knowledge on a particular topic.



</td>
</tr>
<tr>
<td valign="top">

*Mentoring and Coaching Template* 



</td>
<td valign="top">

Designed for mentors and mentees to connect and have private conversations.



</td>
</tr>
<tr>
<td valign="top">

*Planning and Implementation Template* 



</td>
<td valign="top">

Designed with multiple tags to quickly create workspaces intended for collaboration teams managing date-driven deliverables, goals, and milestones.



</td>
</tr>
<tr>
<td valign="top">

*Professional Services Project Room Template* 



</td>
<td valign="top">

Designed to support an extended project team to drive and coordinate planning, implementation, and rollout of a project.

Team members make decisions, discuss requirements, and make decisions.



</td>
</tr>
<tr>
<td valign="top">

*Team Collaboration Template* 



</td>
<td valign="top">

Designed to help members stay organized and share resources with their team.



</td>
</tr>
<tr>
<td valign="top">

*Topic-based Collaboration Template*



</td>
<td valign="top">

Designed so that members can collaborate and share knowledge around a specific topic of interest.



</td>
</tr>
<tr>
<td valign="top">

*Training Room Template* 



</td>
<td valign="top">

Designed so that instructors and participants can work together before, during, and after a training event.



</td>
</tr>
</table>



## Creating and managing workspace templates

You can manage the workspace templates in the Administration Console by navigating to *Area & Workspace Configuration* \> *Workspace Templates*.

Company administrators can enable or disable any out-of-the-box templates. When enabled, they’re available to the entire company.

Area administrators can enable any out-of-the-box template if the company administrator hasn't already enabled it for the entire company. In this case they would need to copy the template to their area, and then customize it for their area.


<table>
<tr>
<th valign="top">

Task



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

Create a workspace template from an existing template



</td>
<td valign="top">

It’s often faster to use an existing workspace template as a basis for creating a new workspace template.

1.  On the *Workspace Template* page, choose *Actions* \> *Copy*.

2.  Enter the name of the new workspace template, adjust the settings, if required, and choose *Save*.




</td>
</tr>
<tr>
<td valign="top">

Create a workspace template from scratch



</td>
<td valign="top">

1.  Choose *New Template*.

2.  On the *New Template* screen, define your settings and save your entries.

    -   *Language*: This is the language that the template is written in. By specifying a language, end users only see the template when they create a workspace if it matches their individual preferred language/locale. By not specifying a language, the template is always visible when creating a workspace.
    -   *Business Records*: By specifying a business object type, it means that the template is built specifically for that type. The template is only available to end users when they create a workspace based on a business object instance of that type.
    -   *Administrative area*: Select an administrative area to restrict the use of a template to a selected area.

3.  To assign content to the workspace template, on the *Workspace Template* page, choose *Edit*.




</td>
</tr>
<tr>
<td valign="top">

Show and hide a workspace template



</td>
<td valign="top">

By default, newly created custom workspace templates are hidden from the users. Make the workspace template visible so that users can create workspaces from the template catalog.

In contrast, before you can delete a custom template that you no longer need, you have to hide it.

-   In the row with the template, use the toggle button.




</td>
</tr>
<tr>
<td valign="top">

Import and export workspace templates



</td>
<td valign="top">

-   To import a template, on the *Workspace Template* page, choose *Import a template*.

    You receive an email notification when the import process is complete. Any processing errors are noted in the email.

-   To export custom templates, on the *Workspace Template* page, choose *Actions* \> *Export*. The workspace template is extracted into a ZIP file that you can download.


> ### Note:  
> The export/import functionality isn’t designed for long-term/permanent, offline storage of custom templates. You may need to re-export and reimport a custom template if they’re no longer compatible due to ongoing changes or improvements to templates.

> ### Note:  
> Don’t delete a custom template from the source environment until it’s successfully imported into the target environment.



</td>
</tr>
<tr>
<td valign="top">

Choose which administrative areas can use the template



</td>
<td valign="top">

You can move a custom workspace template between administrative areas and the company level to determine where the template can be used.

1.  On the *Workspace Template* page, for a template, choose *Actions* \> *Properties*.

2.  On the *Properties* screen, choose the administrative area the custom workspace template belongs to.




</td>
</tr>
<tr>
<td valign="top">

Create a workspace from a template



</td>
<td valign="top">

You can create workspaces from any published workspace template.

Choose *Actions* \> *Create a Workspace*.



</td>
</tr>
<tr>
<td valign="top">

Delete a custom workspace template



</td>
<td valign="top">

You can delete a custom workspace template when it’s hidden.

Choose *Actions* \> *Delete*.

> ### Note:  
> Deleting templates is permanent. You can’t recover a deleted template.



</td>
</tr>
<tr>
<td valign="top">

You can add various workpages as placeholders to the template and then add content or forum pages later using the page designer.



</td>
<td valign="top">

You can add the following placeholder items to a template:

-   *Home Page*: create one or more home pages for the template. Add text, images, and dynamic widgets using the page designer.
-   *Content*: upload documents, photos, videos, or create wikis, business decision tools, folders, and private folders. You can copy and move content items within the template.

    > ### Note:  
    > Company or area administrators can mark documents, wiki pages, and blog posts as mirror items in a custom workspace template. When they update and publish the changes to the original source document, all mirrored items are automatically updated for all workspaces. The source document resides in the custom workspace template. As a workspace administrator, when you create a workspace using a template with content marked as mirror items \(this content is mirrored instead of copied to the new workspace\).

-   *Forums*
-   *Links*



</td>
</tr>
</table>

