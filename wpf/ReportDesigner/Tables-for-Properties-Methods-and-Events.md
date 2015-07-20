---
layout: post
title: Tables-for-Properties-Methods-and-Events
description: tables for properties, methods, and events
platform: wpf
control: Report Designer
documentation: ug
---

# Tables for Properties, Methods, and Events

## Properties

_Properties_

<table>
<tr>
<td>
Properties</td><td>
Description </td><td>
Types </td><td>
Data Type </td></tr>
<tr>
<td>
ShowRibbon</td><td>
Gets or sets the visibility of the Ribbon.</td><td>
Dependency property</td><td>
Boolean</td></tr>
<tr>
<td>
ShowApplicationMenu</td><td>
Gets or sets the visibility of the ApplicationMenu.</td><td>
Dependency Property </td><td>
Boolean</td></tr>
<tr>
<td>
ShowRuler</td><td>
Gets or sets a value to indicate whether the ruler is visible.</td><td>
Dependency Property</td><td>
Boolean</td></tr>
<tr>
<td>
EnableMDIDesigner</td><td>
Gets or sets a value to indicate whether multiple reports are enabled.</td><td>
Dependency Property</td><td>
Boolean</td></tr>
<tr>
<td>
ShowReportData</td><td>
Gets or sets a value to indicate whether report data is visible.</td><td>
Dependency Property</td><td>
Boolean</td></tr>
<tr>
<td>
Assemblies</td><td>
Gets or sets a value to indicate an assembly name to generate a RDLC report.</td><td>
Dependency Property</td><td>
List<Assembly></td></tr>
<tr>
<td>
ShowProperties</td><td>
Gets or sets a value to indicate whether the Properties window is visible.</td><td>
Dependency Property</td><td>
Boolean</td></tr>
<tr>
<td>
ReportFormat</td><td>
Gets or sets a value to indicate whether the report format is RDL2008 or RDL2010.</td><td>
Dependency Property</td><td>
ReportFormat</td></tr>
<tr>
<td>
DesignMode</td><td>
Gets or sets a value to indicate whether the design mode is RDL or RDLC.</td><td>
Dependency Property</td><td>
DesignMode</td></tr>
<tr>
<td>
ReportServerCredential</td><td>
Gets or sets credential access to the report server.</td><td>
Dependency Property</td><td>
ICredentials</td></tr>
<tr>
<td>
ReportServerFormsCredential</td><td>
Gets or sets report server’s forms credential.</td><td>
Dependency Property</td><td>
ReportServerFormsCredential</td></tr>
</table>
## Methods

_Methods_ 

<table>
<tr>
<td>
Methods            </td><td>
Description </td><td>
Parameters </td><td>
Return Type </td></tr>
<tr>
<td>
NewReport</td><td>
Opens a new blank report. </td><td>
-</td><td>
Void</td></tr>
<tr>
<td>
OpenReport                 </td><td>
Opens the RDL report from the file location.</td><td>
ReportPath</td><td>
Void</td></tr>
<tr>
<td>
SaveReportDialogue</td><td>
Saves the report.</td><td>
-</td><td>
Void</td></tr>
<tr>
<td>
SaveAsReportDialogue</td><td>
Makes a RDL report  to save in the corresponding location.</td><td>
-</td><td>
Void</td></tr>
</table>
## Events

_Events_ 

<table>
<tr>
<td>
Events</td><td>
Description </td></tr>
<tr>
<td>
ReportOpened</td><td>
This event is triggered when a report is opened in the Report Designer.</td></tr>
<tr>
<td>
ReportSaved</td><td>
This event is triggered when a report is saved.</td></tr>
<tr>
<td>
NewReportOpened</td><td>
This event is triggered when a new blank report is opened in the Report Designer.</td></tr>
<tr>
<td>
AllReportsClosed</td><td>
This event is triggered when all the reports in the Report Designer is closed.</td></tr>
</table>




