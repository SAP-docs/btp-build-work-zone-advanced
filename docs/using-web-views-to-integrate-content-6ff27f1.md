<!-- loio6ff27f180c304423a9eced4607c3ac56 -->

# Using Web Views to Integrate Content

SAP Build Work Zone, advanced edition content such as workspaces, workpages and more can be integrated in the Joule Work mobile app as web views.

As an administrator, you can create URL apps in the Content Manager using the web view URLs. Then, users can access these apps via the in-app browser in the Joule Work mobile app.

Do the following steps:

1.  In the SAP Build Work Zone, advanced edition Content Manager, create a URL application for each web view URL pointing to a workspace, workpage, or other type of content.

    For more information, see [Configure Apps](configure-apps-4ba745b.md)and [URL and Dynamic URL Apps](url-and-dynamic-url-apps-3254887.md).

2.  Still in the Content Manager, create a group and assign all the applications to this group. You can name this group "Workspaces".

    For more information, see [Assign Apps to Groups](assign-apps-to-groups-6f60d52.md).

3.  Create a role and assign the applications to this role. Assign the same role to the site. Finally, in the SAP BTP cockpit, assign the role to the relevant users.

    For more information, see [Assign Content to a Role](assign-content-to-a-role-baeaf6e.md), [Assign Roles to Your Site](assign-roles-to-your-site-7afe670.md).


