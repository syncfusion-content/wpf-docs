---
layout: post
title: Saving-the-RDL-Reports-as-PDF-Word-and-Excel-Documents
description: saving the rdl reports as pdf, word, and excel documents
platform: wpf
control: Report Writer
documentation: ug
---

# Saving the RDL Reports as PDF, Word, and Excel Documents

Essential Report Writer provides support for saving a report as a PDF, Word, or Excel document with the help of the class ReportWriter. The report elements such as Tablix, matrices, charts, gauges, shapes, and text boxes are supported in this feature.



Use Case Scenario

This feature is very useful in exporting the generated report as a PDF, Word, or Excel document.

## Constructors, Properties and Methods Tables

### Constructors

_Constructors Table_

<table>
<tr>
<td>
Name</td><td>
Description</td></tr>
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


### Properties

_Properties Table_

<table>
<tr>
<td>
Property Name</td><td>
Description </td></tr>
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
Gets or sets the report server credential.</td></tr>
<tr>
<td>
ReportServerFormsCredential</td><td>
Gets or sets the report server form credential. This is used to export SQL Azure RDL reports.</td></tr>
<tr>
<td>
ReportServerUrl</td><td>
Gets or sets the report server URL.</td></tr>
</table>
### Methods



_Methods Table_

<table>
<tr>
<th>
Name</th><th>
Description</th></tr>
<tr>
<th>
GetDataSetNames()</th><th>
Returns the names of the data set as IList<string>.</th></tr>
<tr>
<th>
GetParameters()</th><th>
Returns the parameters of the report as ReportParameterInfoCollection.</th></tr>
<tr>
<th>
SetParameters(IEnumberable<ReportParameters>)</th><th>
Sets the parameters of the report.</th></tr>
<tr>
<th>
LoadReport(stream)</th><th>
Loads the report  with the specified stream that contains the RDL contents.</th></tr>
<tr>
<th>
Save(string,writertype)</th><th>
Saves the report as a PDF, Word, or Excel document in the mentioned path.</th></tr>
<tr>
<th>
Save(stream)</th><th>
Saves the report as a PDF, Word, or Excel document in the stream.</th></tr>
</table>


