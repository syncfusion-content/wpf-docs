---
layout: post
title: ReportViewer API | ReportViewer | WPF | Syncfusion
description: List of Reportviewer API
platform: wpf
control: ReportViewer
 documentation: ug
---

# ReportViewer API

## Properties 

<table>
<tr>
<th>Property</th>
<th>Description</th>
<th>Type</th>
<th>Data Type</th>
</tr>
<tr>
<td>ReportPath</td>
<td>Gets or sets the file Reporting Server Report Path or local system path.</td>
<td>Dependency Property</td>
<td>string </td>
</tr>
<tr>
<td>DataSources</td>
<td>Get a collection of data sources used by the report.</td>
<td>-</td>
<td>ReportDataSourceCollection</td>
</tr>
<tr>
<td>CurrentPage</td>
<td>Gets or sets the current page</td>
<td>Dependency Property</td>
<td>Int</td>
</tr>
<tr>
<td>ProcessingMode</td>
<td>Gets or sets the processing mode namely Remote(from ReportingService or process DataSource from Database server) or Local</td>
<td>Dependency Property</td>
<td>Enum</td>
</tr>
<tr>
<td>ReportServerUrl</td>
<td>Gets or sets the ReportServerUrl of the Report Server</td>
<td>Dependency Property</td>
<td>String</td>
</tr>
<tr>
<td>ShowContextMenu</td>
<td>Gets or sets the ContextMenu visibility</td>
<td>Dependency Property</td>
<td>Boolean</td>
</tr>
<tr>
<td>ShowPrintButton</td>
<td>Gets or sets a value that indicates whether Print button is visible on the toolbar.</td>
<td>Dependency Property</td>
<td>Boolean</td>
</tr>
<tr>
<td>ShowRefreshButton</td>
<td>Gets or sets a value that indicates whether the Refresh button is visible.</td>
<td>Dependency Property</td>
<td>Boolean</td>
</tr>
<tr>
<td>ShowToolBar</td>
<td>Gets or sets a value that indicates whether the toolbar is visible on the control.</td>
<td>Dependency Property</td>
<td>Boolean</td>
</tr>
<tr>
<td>ShowZoomControl</td>
<td>Gets or sets a value that indicates whether the Zoom list box is visible.</td>
<td>Dependency Property</td>
<td>Boolean</td>
</tr>
<tr>
<td>ViewMode</td>
<td>Gets or sets a value that indicates whether it is Normal or Print View</td>
<td>Dependency Property</td>
<td>enum</td>
</tr>
<tr>
<td>ShowPdfExportButton</td>
<td>Gets or sets a value that indicates whether the PDF button is visible</td>
<td>Dependency Property</td>
<td>Boolean</td>
</tr>
<tr>
<td>ShowXPSExportButton</td>
<td>Gets or sets a value that indicates whether the XPS Export Button is Visible</td>
<td>Dependency Property</td>
<td>Boolean</td>
</tr>
<tr>
<td>ShowExportControls</td>
<td>Get or set a value that indicates whether the Export control is Visible</td>
<td>Dependency Property</td>
<td>Boolean</td>
</tr>
<tr>
<td>ShowPageNavigationControls</td>
<td>Get or set a value that indicates whether the page navigation controls is visible</td>
<td>Dependency Property</td>
<td>Boolean</td>
</tr>
<tr>
<td>ReportServerCredential</td>
<td>Credential access to Report Server</td>
<td>Dependency Property</td>
<td>ICredentials</td>
</tr>
<tr>
<td>ShowPageLayoutControl</td>
<td>Gets or sets a value that indicates whether the page layout control is visible</td>
<td>Dependency Property</td>
<td>Boolean</td>
</tr>
<tr>
<td>ShowParametersBlock</td>
<td>Gets or sets a value that indicates whether the parameter block control is visible</td>
<td>Dependency Property</td>
<td>Boolean</td>
</tr>
</table>

## Methods

<table>
<tr>
<th>Method</th>
<th>Description</th>
<th>Parameters</th>
<th>Return Type</th>
</tr>
<tr>
<td>RefreshReport</td>
<td>Causes the local report to be rendered with new data.</td>
<td>-</td>
<td>Void</td>
</tr>
<tr>
<td>GetParameters</td>
<td>Get the necessary parameters for the report</td>
<td>-</td>
<td>ReportParameterInfoCollection</td>
</tr>
<tr>
<td>GetTotalPage</td>
<td>Gets the total pages of the report</td>
<td>-</td>
<td>Void</td>
</tr>
<tr>
<td>GetDataSetNames</td>
<td>Get the dataset names from the local report</td>
<td>-</td>
<td>IList&lt;string&gt;</td>
</tr>
<tr>
<td>LoadReport</td>
<td>Loads the Local report for processing</td>
<td>Stream</td>
<td>void</td>
</tr>
<tr>
<td>Print</td>
<td>Displays the Print dialog box.</td>
<td>-</td>
<td>Void</td>
</tr>
<tr>
<td>ShowNormalView</td>
<td>Displays the Normal view of the Report</td>
<td>-</td>
<td>Void</td>
</tr>
<tr>
<td>SetParameters</td>
<td>Set the necessary parameters for the report</td>
<td>ReportParameter[]</td>
<td>void</td>
</tr>
</table>

## Events

<table>
<tr>
<th>Event</th>
<th>Description</th>
</tr>
<tr>
<td>ViewModeChanged</td>
<td>The event is triggered when the view is changed to normal and print view</td>
</tr>
<tr>
<td>ViewButtonClick</td>
<td>The event is triggered when the view button is clicked</td>
</tr>
<tr>
<td>SubreportProcessing</td>
<td>The event is triggered when the report is RDLC and contains with sub report.</td>
</tr>
</table>