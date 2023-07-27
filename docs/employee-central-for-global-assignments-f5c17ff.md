<!-- loiof5c17ff9467340fc8897d729b623b4fe -->

# Employee Central for Global Assignments

When expatriate employees are sent from their office to offices in other countries on global assignments, you can set up automatic invitations to workspaces for expatriate employees.



> ### Note:  
> This feature is relevant only to SAP SuccessFactors Work Zone.

Such a workspace can, for example, provide expatriate employees with information about the business etiquette in the foreign countries, offer tips about living in that country, or provide information that is relevant to their work in the remote location.

After the Employee Central integration is configured, an employee who is sent on global assignment is invited automatically to workspaces that are associated with the location, and this behavior persists into the future. Any employees who were previously sent on global assignment in Employee Central aren't invited to the workspaces retroactively.

Three types of administrators work together to set up invitations to global assignments in SAP SuccessFactors Platform Employee Central and, an SAP SuccessFactors Platform administrator, an support administrator, and a company administrator:

-   In SAP SuccessFactors Employee Central, employees are configured as expatriate employees.
-   In SAP SuccessFactors Work Zone, a company \(or area\) administrator associates workspaces to an office location, and office locations to a workspace.
-   In Employee Central, HR configures an employee as being on assignment in a foreign office, and the employee is invited to the workspaces.




<a name="loiof5c17ff9467340fc8897d729b623b4fe__section_nnv_thl_dlb"/>

## Step 1: Creating a Business Rule - SAP SuccessFactors Platform Administrator

Create a business rule in the SAP SuccessFactors Platform Admin Center to raise an `AddGlobalAssignment` event.

For more information, see [**Add Global Assignment and End Global Assignment**](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/e85fac4e6a3b4884b6451d4208cdb778/7a9212cb121c44c1843683b45f7bd95a.html).



<a name="loiof5c17ff9467340fc8897d729b623b4fe__section_hgv_thl_dlb"/>

## Step 2: Requesting Setup from SAP SuccessFactors Work Zone Support -SAP SuccessFactors Platform Administrator

Contact SAP SuccessFactors Work Zone support at [https://support.sap.com](https://support.sap.com) and request that they configure a `JobInfo` to send the `AddGlobalAssignment` upon an `onPostSave` event.



<a name="loiof5c17ff9467340fc8897d729b623b4fe__section_cw5_thl_dlb"/>

## Step 3: Enabling SAP SuccessFactors Work Zone as a Subscriber - SAP SuccessFactors Platform Administrator

In the SAP SuccessFactors Platform Admin Center, subscribe SAP SuccessFactors Work Zone to the *Add Global Assignment* event.

For more information, see [**Configuring Global Assignment Events with Recruiting**](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/e85fac4e6a3b4884b6451d4208cdb778/b14ec80f8e5f48369c1c201a6283ae3b.html).



<a name="loiof5c17ff9467340fc8897d729b623b4fe__section_rk5_thl_dlb"/>

## Step 4: Associating Locations with Workspaces - SAP SuccessFactors Work Zone Area or Company Administrator

Administrators configure which workspaces expatriate employees are invited to when working in a specific remote location. So, expatriate employees in that office automatically get access to the workspace.

1.  In n the *Administration Console*, choose *External Integrations* \> *Employee Central*.
2.  Choose *\+ Company* to add a global assignment record.
3.  Select the company office that you want to create a global assignment record for.

4.  Enter the name of the workspace that you want to associate with the company office location.
5.  Save your entries.

6.  You’re returned to the *Employee Central* page and the Global Assignment record that you just created is listed in the catalog.

The *Employee Central* page lists the global assignment record that you created.

By using the slider toggle, you can enable or disable an association.



<a name="loiof5c17ff9467340fc8897d729b623b4fe__section_bb5_thl_dlb"/>

## Step 5: Assigning an Employee to a Global Assignment - HR Worker

After company locations and workspaces are associated, an HR worker can now assign an employee to a long-term global assignment. The assignee then receives automated invitations to the workspaces specified by the administrator for the office location to which they’ve been assigned.

As an HR professional, log on to SAP SuccessFactors Employee Central and create an event to update the employee records. For more information, see [**Configuring Global Assignment Events with Recruiting**](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/e85fac4e6a3b4884b6451d4208cdb778/b14ec80f8e5f48369c1c201a6283ae3b.html).



The employee's long-term foreign assignment is set. The employee receives invitations to the workspaces associated to the specified location.

