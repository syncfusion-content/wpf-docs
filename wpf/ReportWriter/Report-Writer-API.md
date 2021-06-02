---
layout: post
title: Report Writer API | ReportWriter | WPF | Syncfusion
description: Learn here about List of ReportWriter API of Syncfusion Essential Studio for WPF, its elements, features, and more.
platform: wpf
control: ReportWriter
documentation: ug
---

# ReportWriter API of Essential Studio WPF

## Constructors

<table>
<tr>
<th>
Name</th><th>
Description</th></tr>
<tr>
<td>
ReportWriter()</td><td>
Initializes a new instance of the ReportWriter.</td></tr>
<tr>
<td>
ReportWriter(string)</td><td>
Initializes a new instance of the ReportWriter with the specified path of the report.</td></tr>
<tr>
<td>
ReportWriter(stream)</td><td>
Initializes a new instance of the ReportWriter with the stream of the report.</td></tr>
<tr>
<td>
ReportWriter(string, ReportDataSourceCollection)</td><td>
Initializes a new instance of the ReportWriter with the specified path of the report and data source collection.</td></tr>
<tr>
<td>
ReportWriter(stream, ReportDataSourceCollection)</td><td>
Initializes a new instance of the ReportWriter with the stream of the report and data source collection.</td></tr>
</table>

## Properties

<table>
<tr>
<th>
Property Name</th><th>
Description </th></tr>
<tr>
<td>
DataSources</td><td>
Gets or sets the data source collection.</td></tr>
<tr>
<td>
ReportPath</td><td>
Gets or sets the report path (file name of the report with its full path).</td></tr>
<tr>
<td>
ReportProcessingMode</td><td>
Gets or sets the processing mode (either local or remote).</td></tr>
<tr>
<td>
ReportServerCredential</td><td>
Gets or sets the Report Server credential.</td></tr>
<tr>
<td>
ReportServerFormsCredential</td><td>
Gets or sets the Report Server form credential. This is used to export SQL Azure RDL reports.</td></tr>
<tr>
<td>
ReportServerUrl</td><td>
Gets or sets the ReportServerURL.</td></tr>
</table>

## Methods

<table>
<tr>
<th>
Name</th><th>
Description</th></tr>
<tr>
<td>
GetDataSetNames()</td><td>
Returns the names of the data set as IList &lt;string&gt;.</td></tr>
<tr>
<td>
GetParameters()</td><td>
Returns the parameters of the report as ReportParameterInfoCollection.</td></tr>
<tr>
<td>
SetParameters(IEnumerable&lt;ReportParameters&gt;)</td><td>
Sets the parameters of the report.</td></tr>
<tr>
<td>
LoadReport(stream)</td><td>
Loads the report with the specified stream that contains the RDL contents.</td></tr>
<tr>
<td>
Save(string,writer type)</td><td>
Saves the report as a PDF, Word, Excel and HTML documents in the mentioned path.</td></tr>
<tr>
<td>
Save(stream)</td><td>
Saves the report as a PDF, Word, Excel and HTML documents in the stream.</td></tr>
</table>

## Events

<table>
<tr><th>
Events</th><th>
Description </th></tr>
<tr><td>
ReportError</td><td>
This event is triggered when Report throws Error.</td></tr>
<tr><td>
ExportCompleted</td><td>
This event is triggered when export is completed.</td></tr>
<tr><td>
SubreportProcessing</td><td>
This event is triggered when the report is RDLC and contains with subreport.</td></tr>
</table>