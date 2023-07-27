<!-- loio9fd82e0d77964061b769d9109d7119a2 -->

# Reports

SAP Build Work Zone, advanced edition administrator reports display information about many aspects of SAP Build Work Zone, advanced edition usage. Reports can include adoption metrics \(such as user information, user contribution, and consumption activity\), and disk usage statistics.



<a name="loio9fd82e0d77964061b769d9109d7119a2__section_vc3_d42_4tb"/>

## Overview

SAP Build Work Zone, advanced edition reports can be downloaded as CSV or XLSX files. Workspace administrators can choose from a vartiety of reports to get workspace-specific data. In the case of a private workspace, the company administrator can view the details and membership of the workspace only if the *Include Private Workspace Details* feature is enabled in the *Feature Enablement* \> *Features* screen.



> ### Note:  
> Report time frames span a maximum of 3 months at a time. For example, if you want to view results for a particular report from January 1, 2019 to May 31, 2019, you would have to generate two reports. The first report would have a date range of January 1, 2019 to March 31, 2019, and the second report would span April 1, 2019 to May 31, 2019.



<a name="loio9fd82e0d77964061b769d9109d7119a2__section_nmk_vn1_hlb"/>

## Running a report

1.  From the *Administration Console*, select *Analytics* \> *Reports*.
2.  Select the options for the report that you want to run:


    <table>
    <tr>
    <th valign="top">

    Option


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Select Report*


    
    </td>
    <td valign="top">
    
    Select the type of report that you want to run from the dropdown menu.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Specify Date Range*


    
    </td>
    <td valign="top">
    
    From the calendar, choose the start date and the end date for the period to be covered by your report.

    The maximum date range spans no more than 3 months .


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Show Report Header*


    
    </td>
    <td valign="top">
    
    Select this option to include report headings indicating the report name and the settings used for the report \(such as the time frame and the workspaces covered\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Type*


    
    </td>
    <td valign="top">
    
    Select the output format of the report.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Select Workspace*


    
    </td>
    <td valign="top">
    
    Select either *All* or any of the specific workspaces created in your company.


    
    </td>
    </tr>
    </table>
    
3.  Choose *Request Report*.

    The report is queued to run. Generally your report runs almost immediately, unless there are multiple reports scheduled \(queued\). Some reports with large amounts of data to process, such as the workspace activity report, can take up to about an hour to run.

    Queued and completed reports are displayed below the report options and are visible to all administrators.

4.  Reload the page in your browser to see the results of your recently run report.

5.  To download your report, click the report name and save on your computer.


> ### Note:  
> If users copy or move content between workspaces, it affects the counts of their activities in reports: A moved document is no longer counted in the original workspace, but it’s counted in the new workspace in which it’s located, while a copied document is counted in both workspaces.



<a name="loio9fd82e0d77964061b769d9109d7119a2__section_ecx_d52_4tb"/>

## Availability of reports

The availability of reports is shown in the following table:

> ### Note:  
> Area administrators can't run all reports.


<table>
<tr>
<th valign="top">

Report



</th>
<th valign="top">

Link to more information



</th>
<th valign="top">

Area Administrators

\(for their area only\)



</th>
<th valign="top">

Company Administrators

\(for the entire company\)



</th>
</tr>
<tr>
<td valign="top">

Activity Summary by Month



</td>
<td valign="top">

[Activity Summary by Week or Month Report](activity-summary-by-week-or-month-report-dfa4abc.md)



</td>
<td valign="top">

Yes



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Activity Summary by Week



</td>
<td valign="top">

[Activity Summary by Week or Month Report](activity-summary-by-week-or-month-report-dfa4abc.md)



</td>
<td valign="top">

Yes



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Company Settings Changes



</td>
<td valign="top">

[Company Settings Changes Report](company-settings-changes-report-71cc82e.md)



</td>
<td valign="top">

No



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Company User Detail Report



</td>
<td valign="top">

[Company Settings Changes Report](company-settings-changes-report-71cc82e.md)



</td>
<td valign="top">

No



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Compliance Report



</td>
<td valign="top">

[Compliance Report](compliance-report-d0a7599.md)



</td>
<td valign="top">

No



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Content Views by Month



</td>
<td valign="top">

[Content Views by Week or Month Report](content-views-by-week-or-month-report-749c4f8.md)



</td>
<td valign="top">

Yes



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Content Views by Week



</td>
<td valign="top">

[Content Views by Week or Month Report](content-views-by-week-or-month-report-749c4f8.md)



</td>
<td valign="top">

Yes



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Contribution Report by Object by Month



</td>
<td valign="top">

[Contribution by Object by Month or Week Report](contribution-by-object-by-month-or-week-report-97dce9e.md)



</td>
<td valign="top">

Yes



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Contribution Report by Object by Week



</td>
<td valign="top">

[Contribution by Object by Month or Week Report](contribution-by-object-by-month-or-week-report-97dce9e.md)



</td>
<td valign="top">

Yes



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Engagement Report



</td>
<td valign="top">

[Engagement Report](engagement-report-e79f175.md)



</td>
<td valign="top">

No



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Expertise Report



</td>
<td valign="top">

[Expertise Report](expertise-report-37923b5.md)



</td>
<td valign="top">

No



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Kudo Detail



</td>
<td valign="top">

[Kudo Detail Report](kudo-detail-report-7a08a3c.md)



</td>
<td valign="top">

No



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Search Summary by Month



</td>
<td valign="top">

[Search Summary by Week or Month Report](search-summary-by-week-or-month-report-6e43aa5.md)



</td>
<td valign="top">

No



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Search Summary by Week



</td>
<td valign="top">

[Search Summary by Week or Month Report](search-summary-by-week-or-month-report-6e43aa5.md)



</td>
<td valign="top">

No



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Terms of Service Compliance Report



</td>
<td valign="top">

[Terms of Service Compliance Report](terms-of-service-compliance-report-2b9d4de.md)



</td>
<td valign="top">

No



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Top Disk Usage per User



</td>
<td valign="top">

[Top Disk Usage per Workspace or User Report](top-disk-usage-per-workspace-or-user-report-6398baf.md)



</td>
<td valign="top">

No



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Top Disk Usage per Workspace



</td>
<td valign="top">

[Top Disk Usage per Workspace or User Report](top-disk-usage-per-workspace-or-user-report-6398baf.md)



</td>
<td valign="top">

No



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

User Contribution Activity Report



</td>
<td valign="top">

[User Contribution Activity Report](user-contribution-activity-report-cf9bf88.md)



</td>
<td valign="top">

No



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

User Contribution Report by Month



</td>
<td valign="top">

[User Contribution by Week or Month Report](user-contribution-by-week-or-month-report-c4ec364.md)



</td>
<td valign="top">

No



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

User Contribution Report by Week



</td>
<td valign="top">

[User Contribution by Week or Month Report](user-contribution-by-week-or-month-report-c4ec364.md)



</td>
<td valign="top">

No



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

User Page Views by Month



</td>
<td valign="top">

[User Page Views by Week or Month Report](user-page-views-by-week-or-month-report-a10a4f3.md)



</td>
<td valign="top">

No



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

User Page Views by Week



</td>
<td valign="top">

[User Page Views by Week or Month Report](user-page-views-by-week-or-month-report-a10a4f3.md)



</td>
<td valign="top">

No



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Workspace Activity Report



</td>
<td valign="top">

[Workspace Activity Report](workspace-activity-report-c44d406.md)



</td>
<td valign="top">

Yes



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Workspace Administrators Report



</td>
<td valign="top">

[Workspace Administrators Report](workspace-administrators-report-67cfc9c.md)



</td>
<td valign="top">

No



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Workspace Member Activity Report



</td>
<td valign="top">

[Workspace Member Activity Report](workspace-member-activity-report-b07d17d.md)



</td>
<td valign="top">

No



</td>
<td valign="top">

Yes



</td>
</tr>
<tr>
<td valign="top">

Workspace Template Activity Report



</td>
<td valign="top">

[Workspace Template Activity Report](workspace-template-activity-report-8e2117c.md)



</td>
<td valign="top">

No



</td>
<td valign="top">

Yes



</td>
</tr>
</table>

