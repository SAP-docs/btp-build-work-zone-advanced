<!-- loioa3154ab67da94638a7f579d836a002e0 -->

# Login Activity Example

This example explains how the dashboard calculates the numbers for current users and unique logins.



## Scenario

A company has subscribed to 2000 licenses of SAP Build Work Zone, advanced edition. This number isn't shown on the dashboard. The company's SAP Build Work Zone, advanced edition instance was created on January 1, 2020. Today's date is December 31, 2021, which is two years since the tenant was created.



## Example Login Activities

**Example Login Activities**


<table>
<tr>
<th valign="top">

Time Period



</th>
<th valign="top">

Who Logged on to SAP Build Work Zone, advanced edition?



</th>
</tr>
<tr>
<td valign="top">

January 1, 2020 to December 31, 2020



</td>
<td valign="top">

Employees 1 to 100



</td>
</tr>
<tr>
<td valign="top">

January 1, 2021 to March 31, 2021



</td>
<td valign="top">

Employees 101-500



</td>
</tr>
<tr>
<td valign="top">

April 1, 2021 to June 30, 2021



</td>
<td valign="top">

Employees 101-500



</td>
</tr>
<tr>
<td valign="top">

July 1, 2021 to September 30, 2021



</td>
<td valign="top">

Employees 101-300 and 501-1000



</td>
</tr>
<tr>
<td valign="top">

October 1, 2021 to December 31, 2021



</td>
<td valign="top">

Employees 1001-2000



</td>
</tr>
</table>

At the end of 2021, employees 1 to 50 left the organization and became alumni.



## What Appears on the Dashboard

Based on the values in the previous table, the following shows the counts for active users and unique logins.

**Login Activity Values**


<table>
<tr>
<th valign="top">

Time Frame Selection



</th>
<th valign="top">

\*Active Users



</th>
<th valign="top">

Unique Logins



</th>
</tr>
<tr>
<td valign="top">

Last 4 weeks



</td>
<td valign="top">

1950



</td>
<td valign="top">

1000

-   Employees 1001 to 2000




</td>
</tr>
<tr>
<td valign="top">

Last 3 months



</td>
<td valign="top">

1950



</td>
<td valign="top">

1000

-   Employees 1001 to 2000




</td>
</tr>
<tr>
<td valign="top">

Last 6 months



</td>
<td valign="top">

1950



</td>
<td valign="top">

1700 \(1000 + 200 + 500\)

-   Employees 1001-2000, employees 101-300, and employees 501-1000




</td>
</tr>
<tr>
<td valign="top">

Last 12 months



</td>
<td valign="top">

1950



</td>
<td valign="top">

1900 \(1000 + 500 + 400\)

-   Employees 1001-2000, employees 501-1000, and employees 101-500




</td>
</tr>
</table>

\*The current users count of 1950 is equal to the total number of active users over time \(not dependent on a time frame selection\) minus the 50 alumni.

