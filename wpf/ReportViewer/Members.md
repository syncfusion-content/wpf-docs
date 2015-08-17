---
layout: post
title: Members
description: members
platform: wpf
control: Report Viewer
documentation: ug
---

# Members

_Properties_ 

<table>
<tr>
<td>
{{ '**Property**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td><td>
{{ '**Type**' | markdownify }}</td><td>
{{ '**Data Type**' | markdownify }}</td></tr>
<tr>
<td>
<br>ReportPath</td><td>
Gets or sets the file Reporting Server Report Path or local system path.</td><td>
 Dependency Property</td><td>
string </td></tr>
<tr>
<td>
DataSources</td><td>
Get a collection of data sources used by the report.</td><td>
-</td><td>
ReportDataSourceCollection</td></tr>
<tr>
<td>
CurrentPage</td><td>
Gets or sets the current page</td><td>
 Dependency Property</td><td>
Int</td></tr>
<tr>
<td>
ProcessingMode</td><td>
Gets or sets the processing mode namely Remote(from ReportingService or process DataSource from Database server) or Local</td><td>
Dependency Property </td><td>
Enum</td></tr>
<tr>
<td>
ReportServerUrl</td><td>
Gets or sets the ReportServerUrl of the report server</td><td>
Dependency Property </td><td>
String</td></tr>
<tr>
<td>
ShowContextMenu</td><td>
Gets or sets the ContextMenu visibility</td><td>
Dependency Property </td><td>
Boolean</td></tr>
<tr>
<td>
ShowPrintButton</td><td>
Gets or sets a value that indica tes whether Print button is visible on the toolbar.</td><td>
Dependency Property </td><td>
Boolean</td></tr>
<tr>
<td>
ShowRefreshButton</td><td>
Gets or sets a value that indicates whether the Refresh button is visible.</td><td>
Dependency Property </td><td>
Boolean</td></tr>
<tr>
<td>
ShowToolBar</td><td>
Gets or sets a value that indicates whether the toolbar is visible on the control.</td><td>
Dependency Property </td><td>
Boolean</td></tr>
<tr>
<td>
ShowZoomControl</td><td>
Gets or sets a value that indicates whether the Zoom list box is visible.</td><td>
Dependency Property </td><td>
Boolean</td></tr>
<tr>
<td>
ViewMode</td><td>
Gets or sets a value that indicates whether it is Normal or Print View</td><td>
Dependency Property</td><td>
enum</td></tr>
<tr>
<td>
ShowPdfExportButton</td><td>
Gets or sets a value that indicates whether the Pdf button is visible </td><td>
Dependency Property</td><td>
Boolean</td></tr>
<tr>
<td>
ShowXpsExportButton</td><td>
Gets or sets a value that indicates whether the Xps Export Button is Visible</td><td>
Dependency Property</td><td>
Boolean</td></tr>
<tr>
<td>
ShowExportControls</td><td>
Get or set a value that indicates whether the Export control is Visible</td><td>
Dependency Property</td><td>
Boolean</td></tr>
<tr>
<td>
ShowPageNavigationControls</td><td>
Get or set a value that indicates whether the page navigationcontrols is visible</td><td>
Dependency Property</td><td>
Boolean</td></tr>
<tr>
<td>
ReportServerCredential</td><td>
Credential access to Report server</td><td>
Dependency Property</td><td>
ICredentials</td></tr>
<tr>
<td>
ShowPageLayoutControl</td><td>
Gets or sets a value that indicates whether the page layout control is visible</td><td>
Dependency Property</td><td>
Boolean</td></tr>
<tr>
<td>
ShowParametersBlock</td><td>
Gets or sets a value that indicates whether the parameter block  control is visible</td><td>
Dependency Property</td><td>
Boolean</td></tr>
</table>
_Methods_ 

<table>
<tr>
<th>

{{ '**Method**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td><td>
{{ '**Parameters**' | markdownify }}</td><td>
{{ '**Return Type**' | markdownify }}</td></tr>
<tr>
<th>
<br>RefreshReport</th><th>
Causes the local report to be rendered with new data.</th><th>
 -</th><th>
Void</th></tr>
<tr>
<th>
GetParameters</th><th>
Get the necessary parameters for the report</th><th>
-</th><th>
ReportParameterInfoCollection</th></tr>
<tr>
<th>
GetTotalPage</th><th>
Gets the total pages of the report</th><th>
-</th><th>
Void</th></tr>
<tr>
<th>
GetDataSetNames</th><th>
Get the dataset names from the local report</th><th>
-</th><th>
IList<string></th></tr>
<tr>
<th>
LoadReport</th><th>
Loads the Local report for processing</th><th>
Stream</th><th>
void</th></tr>
<tr>
<th>
Print</th><th>
Displays the Print dialog box.</th><th>
-</th><th>
Void</th></tr>
<tr>
<th>
ShowNormalView</th><th>
Displays the Normal view of the Report</th><th>
-</th><th>
Void</th></tr>
<tr>
<th>
SetParameters</th><th>
Set the necessary parameters for the report</th><th>
ReportParameter[]</th><th>
void</th></tr>
</table>
_Events_ 

<table>
<tr>
<th>
{{ '**Event**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th></tr>
<tr>
<th>
<br>ViewModeChanged</th><th>
The event is triggered when the view is changed to normal and print view</th></tr>
<tr>
<th>
ViewButtonClick</th><th>
The event is triggered when the view button is clicked</th></tr>
<tr>
<th>
SubreportProcessing</th><th>
The event is triggered when the report is RDLC and contains with sub report.</th></tr>
</table>


