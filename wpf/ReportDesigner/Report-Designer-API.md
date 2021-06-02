---
layout: post
title: Report Designer API | ReportDesigner | wpf | Syncfusion
description: Learn here about API of Syncfusion Essential Studio WPF Report Designer control, its elements and more.
platform: wpf
control: Report Designer
documentation: ug
---

# Report Designer API in WPF

## Properties

<table>
<tr><th>
Properties</th><th>
Description </th><th>
Types </th><th>
Data Type </th></tr>
<tr><td>
ShowRibbon</td><td>
Gets or sets the visibility of the Ribbon.</td><td>
Dependency property</td><td>
Boolean</td></tr>
<tr><td>
ShowApplicationMenu</td><td>
Gets or sets the visibility of the ApplicationMenu.</td><td>
Dependency Property </td><td>
Boolean</td></tr>
<tr><td>
ShowRuler</td><td>
Gets or sets a value to indicate whether the ruler is visible.</td><td>
Dependency Property</td><td>
Boolean</td></tr>
<tr><td>
EnableMDIDesigner</td><td>
Gets or sets a value to indicate whether multiple reports are enabled.</td><td>
Dependency Property</td><td>
Boolean</td></tr>
<tr><td>
ShowReportData</td><td>
Gets or sets a value to indicate whether report data is visible.</td><td>
Dependency Property</td><td>
Boolean</td></tr>
<tr><td>
Assemblies</td><td>
Gets or sets a value to indicate an assembly name to generate a RDLC report.</td><td>
Dependency Property</td><td>
List&lt;Assembly&gt;</td></tr>
<tr><td>
ShowProperties</td><td>
Gets or sets a value to indicate whether the Properties window is visible.</td><td>
Dependency Property</td><td>
Boolean</td></tr>
<tr><td>
ReportFormat</td><td>
Gets or sets a value to indicate whether the report format is RDL2008 or RDL2010.</td><td>
Dependency Property</td><td>
ReportFormat</td></tr>
<tr><td>
DesignMode</td><td>
Gets or sets a value to indicate whether the design mode is RDL or RDLC.</td><td>
Dependency Property</td><td>
DesignMode</td></tr>
<tr><td>
ReportServerCredential</td><td>
Gets or sets credential access to the Report Server.</td><td>
Dependency Property</td><td>
ICredentials</td></tr>
<tr><td>
ReportServerFormsCredential</td><td>
Gets or sets report server’s forms credential.</td><td>
Dependency Property</td><td>
ReportServerFormsCredential</td></tr>
</table>

## Methods

<table>
<tr><th>
Methods </th><th>
Description </th><th>
Parameters </th><th>
Return Type </th></tr>
<tr><td>
NewReport</td><td>
Opens a new blank report. </td><td>
- </td><td>
Void</td></tr>
<tr><td>
OpenReport </td><td>
Opens the RDL report from the file location.</td><td>
ReportPath</td><td>
Void</td></tr>
<tr><td>
SaveReportDialog</td><td>
Saves the report.</td><td>
- </td><td>
Void</td></tr>
<tr><td>
SaveAsReportDialog</td><td>
Makes a RDL report  to save in the corresponding location.</td><td>
- </td><td>
Void</td></tr>
</table>

## Events

<table>
<tr><th>
Events</th><th>
Description </th></tr>
<tr><td>
ReportOpened</td><td>
This event is triggered when a report is opened in the Report Designer.</td></tr>
<tr><td>
ReportSaved</td><td>
This event is triggered when a report is saved.</td></tr>
<tr><td>
NewReportOpened</td><td>
This event is triggered when a new blank report is opened in the Report Designer.</td></tr>
<tr><td>
AllReportsClosed</td><td>
This event is triggered when all the reports in the Report Designer is closed.</td></tr>
</table>