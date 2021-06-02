---
layout: post
title: ReportViewer Troubleshooting Errors | ReportViewer | WPF | Syncfusion
description: How to handle the errors for respective issues in Syncfusion Essential Studio WPF ReportViewer Control, its elements and more.
platform: wpf
control: ReportViewer
documentation: ug
---
# Troubleshooting Errors

To resolve the respective issues in report viewer, use the following troubleshooting steps:

## RV001

<table>

<tr>
<td>CODE</td><td>RV001</td>
</tr>

<tr>
<td>TEXT</td><td>The source of the report definition has not been specified.</td>
</tr>
<tr>
<td>DESCRIPTION</td>
<td>The report viewer will not render the report when either the report path or stream is not set or the given path is incorrect.</td>
</tr>
<tr>
<td>SOLUTION</td>
<td>
<li>Make sure that the report path is specified and ensure whether the name or report path is correct.</li>
<li>Check whether the report exists in the specified directory or not and also it should be accessible.</li>  

For Example : viewer.ReportPath = @"../../SampleReport.rdl";  
</td>
</tr>
</table>

## RV002

<table>

<tr>
<td>CODE</td><td>RV002</td>
</tr>

<tr>
<td>TEXT</td><td>The report definition has an invalid schema version.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report definition should contain the supported schema version (For Example : 2008) to render the report in the report viewer.
</td>
</tr>
<tr>
<td>SOLUTION</td>
<td>Make sure that the provided schema in your report definition is supported in the report viewer. <br> Supported versions are 2008, 2010, and 2016.</td>
</tr>
</table>

## RV003

<table>
<tr>
<td>CODE</td><td>RV003</td>
</tr>

<tr>
<td>TEXT</td>
<td>Report Deserialization failed.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>An error is occurred during the deserialization of the report definition.</td>
</tr>

<tr>
<td>SOLUTION</td><td>
<li>XML deserialization is failed due to incorrect item tags or missed element. Report item elements should have its required attribute.</li>
<li> Note: Detailed description with line number and position is mentioned in the report viewer instance error dialog.</li>
</td>
</tr>
</table>

## RV004

<table>
<tr>
<td>CODE</td><td>RV004</td>
</tr>

<tr>
<td>TEXT</td>
<td>Invalid Expression</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>The expression used in the report is incorrect scope or syntax or unsupported.</td>
</tr>

<tr>
<td>SOLUTION</td><td><li>Ensure that the expression used in the report is correct with valid scope and syntax.</li>
Note: Detailed information of report item along with line number and position is mentioned in the report viewer instance error dialog.
</td>
</tr>
</table>

## RV005

<table>
<tr>
<td>CODE</td>
<td>RV005</td>
</tr>

<tr>
<td>TEXT</td>
<td>The requested file or assembly was not found. It may have either moved or renamed.</td>
</tr>

<tr>
<td>DESCRIPTION</td>
<td> Any of the assembly related to report platform is missed at installation location.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>If you are previewing the report from Report Designer, check whether any assembly is missed at installed location (%ProgramData%\Syncfusion\Report Designer\ReportDesigner) or reinstall the Report Designer application. 
If you are loading the report from SDK sample, check whether any assembly is missed at installed location (%ProgramData%\Report Platform SDK\Assemblies) or reinstall the Report Platform SDK application. 
If you are loading the report from Report Server, check whether any assembly is missed at installed location (%ProgramData%\Report Server\ReportServer.Web\bin) or reinstall the Report Server application.

Note : Please contact Syncfusion support if you cannot resolve the issue.
</td>
</tr>
</table>

## RV006

<table>

<tr>
<td>CODE</td>
<td>RV006</td>
</tr>

<tr>
<td>TEXT</td>
<td>An error is occurred while sending a request to the reporting service.</td>
</tr>

<tr>
<td>DESCRIPTION</td>
<td>Report will not be rendered when there is a problem while connecting or retrieving the data from provided reporting service's URL.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>
<ol>
<li>Make sure that you are connected to the Internet.</li>
<li>Ensure that the specified reporting service URL is valid.</li>
<li>Check whether the reporting service is running or not.<br>
If not, start the reporting service from the desktop shortcut (For Example : Start Syncfusion Report Server IIS Express) or from installed location.    </li>   </ol>    

Installed location path : (%ProgramData%\Report Server\Infrastructure\StartReportServerIISExpress)
</td>
</tr>

</table>

## RV007

<table>

<tr>
<td>CODE</td>
<td>RV007</td>
</tr>

<tr>
<td>TEXT</td>
<td>Invalid object name.</td>
</tr>

<tr>
<td>DESCRIPTION</td>
<td>Specified data source is invalid.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Verify that you are connected to the data source and query syntax is correct.</td>
</tr>
</table>

## RV008

<table>
<tr>
<td>CODE</td><td>RV008</td>
</tr>

<tr>
<td>TEXT</td>
<td>Cannot load sub report.</td>
</tr>

<tr>
<td>DESCRIPTION</td>
<td>Sub report cannot be loaded with an invalid name or report path.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>
<li>Make sure that the sub report path is specified and ensure whether the name or path is correct.</li>
<li>Check whether the report exists in the specified directory or not and also it should be accessible.</li>  
</td>
</tr>
</table>

## RV009

<table>
<tr>
<td>CODE</td><td>RV009</td>
</tr>

<tr>
<td>TEXT</td><td>The data source used in a report does not exist or not accessible.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report will not be rendered in the report viewer when the data source used in a report does not exists or it is non accessible due to permission rights.</td>
</tr>

<tr>
<td>SOLUTION</td><td>Ensure whether the data source in a report exists in the referred location.
<li> For embedded data source, the data source is referred in the local machine </li>
<li> For shared data source, the data source is existed in the server and used in the local machine. Make sure that the authentication is sufficient to access the data source.</li>
</td>
</tr>
</table>

## RV010

<table>
<tr>
<td>CODE</td><td>RV010</td>
</tr>

<tr>
<td>TEXT</td>
<td>An error is occurred on the Report Server.</td>
</tr>

<tr>
<td>DESCRIPTION</td>
<td>Specified reporting service encounters an error while rendering the report in report viewer.<br>
</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Check the error log file(s) generated in the below mentioned location. (C:\Syncfusion\Report Server\ReportServer.Web\App_Data\Logs)<br>
 For more information about the types of status code, refer to the available status code in online.</td>
</tr>
</table>

## RV011

<table>

<tr>
<td>CODE</td><td>RV011</td>
</tr>

<tr>
<td>TEXT</td><td>Please select a value for the report parameter.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report parameters must be supplied with value if it is non-nullable while trying to preview the report in report viewer.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Enter the value to parameter in a parameter block, when it is non-nullable or allow blank.</td>
</tr>
</table>

## RV012

<table>

<tr>
<td>CODE</td><td>RV012</td>
</tr>

<tr>
<td>TEXT</td><td>The value provided for the report parameter is not valid for its type.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>The report will not be rendered from the report viewer when the specified value for report parameter is irrespective to its type.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Provide an appropriate value to report parameter based on its data type while rendering the report. <br>
Example: A parameter with integer data type allows integer value, it does not allows float values.</td>
</tr>
</table>

## RV013

<table>

<tr>
<td>CODE</td><td>RV013</td>
</tr>

<tr>
<td>TEXT</td><td>Parameter is missing a value.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report viewer will not render the report when the hidden parameter does not contain a value, which is non-nullable.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Provide value to hidden parameters in your report definition before rendering the report. <br> Note: Hidden parameters must contain default value or it should be nullable.</td>
</tr>
</table>

## RV014

<table>

<tr>
<td>CODE</td><td>RV014</td>
</tr>

<tr>
<td>TEXT</td><td>Forward dependencies are not valid.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report will not be rendered when there is an existence of forward dependencies between parameters.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Make sure to remove the forward dependencies in your report definition before previewing the report. <br>
Example: FirstParameter depends on Dataset1 and Dataset1 depends on SecondParameter, and then it results in forward dependency. <br> Note: Parameters are executed based on the order.</td>
</tr>
</table>

## RV015

<table>

<tr>
<td>CODE</td><td>RV015</td>
</tr>

<tr>
<td>TEXT</td><td>The expression that references parameter is not valid and does not exist in the parameters collection or forward dependencies.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>
Report viewer throws error when you try to use the non-existing report parameter or with forward dependencies.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Make sure to use the parameters that are exists in report definition and avoid forward dependencies in the report. <br>
Note: Letters in the names of parameters should be in correct case.</td>
</tr>
</table>

## RV016

<table>

<tr>
<td>CODE</td><td>RV016</td>
</tr>

<tr>
<td>TEXT</td><td>Value property of an image report item contains invalid value.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report will not be rendered to report viewer when you try to use the invalid image data or non-existing image in the report.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Ensure that the value provided to image report item is specified properly, and make sure that the image is available.
<li>Embedded : Image data should be available in a report definition.</li>
<li>External : External images can be obtained by specifying a URL, and make sure that credentials are sufficient to access the image.</li>
<li>Database : Images can be referred from the dataset, and make sure that credentials are sufficient to access the database.</li></td>
</tr>
</table>

## RV017

<table>

<tr>
<td>CODE</td><td>RV017</td>
</tr>

<tr>
<td>TEXT</td><td>Provide Report Server information to get shared data source information.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report with shared data source must contain the Report Server information and credentials that are provided to render in the report viewer.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Make sure that credentials in Report Server URL are not empty, and ensure that the correct information is provided to the report viewer. <br> Example: viewer.ReportServerUrl = @"http://mvc.syncfusion.com/reportserver/"
viewer.ReportServerCredential = new System.Net.NetworkCredential("username", "password");
</td>
</tr>
</table>

## RV018

<table>

<tr>
<td>CODE</td><td>RV018</td>
</tr>

<tr>
<td>TEXT</td><td>Provide Report Server information to get shared dataset information.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report with shared dataset must contain the Report Server information and credentials to render in the report viewer.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Make sure that credentials in Report Server URL are not empty, and ensure that the correct information is provided to the report viewer.<br> Example: viewer.ReportServerUrl = @"http://mvc.syncfusion.com/reportserver/"
viewer.ReportServerCredential = new System.Net.NetworkCredential("username", "password");</td>
</tr>
</table>

## RV019

<table>

<tr>
<td>CODE</td><td>RV019</td>
</tr>

<tr>
<td>TEXT</td><td>The ReportServerUrl or ReportServerCredential is missing.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Server report or server referred items used in the report will not be rendered in the report viewer without ReportServerUrl and ReportServerCredential.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Make sure that ReportServerUrl and ReportServerCredential are not empty and provided with proper data and accessible.</td>
</tr>
</table>

## RV020

<table>

<tr>
<td>CODE</td><td>RV020</td>
</tr>

<tr>
<td>TEXT</td><td>The value for the DataSetName property is missing.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Data region items are not allowed in reports without datasets to render in the viewer.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Make sure to provide dataset name property value in your report definition, ensure that the property value is not empty.</td>
</tr>
</table>

## RV021

<table>

<tr>
<td>CODE</td><td>RV021</td>
</tr>

<tr>
<td>TEXT</td><td>Data region items are not allowed in reports without datasets to render in the viewer</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report viewer will not render the report when data region items does not refer the dataset.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Make sure to provide dataset name property value in your report definition. <br> Note: Report will render when the report definition has a single dataset; When dataset count is greater than one you must specify the dataset name property value to data region items (Tablix, Chart, Gauge etc..)</td>
</tr>
</table>

## RV022

<table>

<tr>
<td>CODE</td><td>RV022</td>
</tr>

<tr>
<td>TEXT</td><td>Report item refers to an invalid DataSetName.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report will not be rendered in the report viewer when non-existing dataset is used in the report.<br>
</td>
</tr>

<tr>
<td>SOLUTION</td>
<td><li>Embedded : Make sure that the report item referred dataset exists in report definition.</li>
<li>Shared : Make sure that the referred dataset exists in server and accessible.</li></td>
</tr>
</table>

## RV023

<table>

<tr>
<td>CODE</td><td>RV023</td>
</tr>

<tr>
<td>TEXT</td><td>Toggle items must be text boxes that share the same scope, and they are not allowed in page headers or footers.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>In our report viewer, toggle items must be shared within same scope, and they are not allowed in page headers and page footers.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Provide toggle items in the report in same scope, not from their page header or page footer. <br>
Example: If a report item in the page header contains the toggle item then the referred toggle item should be in header region.</td>
</tr>
</table>

## RV024

<table>

<tr>
<td>CODE</td><td>RV024</td>
</tr>

<tr>
<td>TEXT</td><td>Provide dataset inputs for report.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>To render the RDLC report, you must add the data source collection in the report viewer if any dataset is used in the report.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Make sure to add the dataset to render the report in report viewer if dataset fields are used. <br>
Example: viewer.DataSources.Add("Dataset1", object collection of data) <br>
Note: Here, name ("Dataset1") is the dataset name used in the report definition.</td>
</tr>
</table>

## RV025

<table>

<tr>
<td>CODE</td><td>RV025</td>
</tr>

<tr>
<td>TEXT</td><td>Collection class or datatable input is needed.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>In report viewer to render the RDLC report, the report must have collection class or datatable input to rendering the report.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Make sure to provide dataset collection to render the report. Supported collections are "IEnumerable", "System.Data.DataTable", and "System.Data.Dataset"</td>
</tr>
</table>

## RV026

<table>

<tr>
<td>CODE</td><td>RV026</td>
</tr>

<tr>
<td>TEXT</td><td>The value expression for the TextRun contains a colon or a line terminator.
</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Textbox report item value expression contains a colon or a line terminator.<br>
Colons and line terminators are not valid in expressions.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Remove colons and line terminator used in the specified report item expression.</td>
</tr>
</table>

## RV027

<table>

<tr>
<td>CODE</td><td>RV027</td>
</tr>

<tr>
<td>TEXT</td><td>The tablix report item has an invalid TablixMember in column hierarchy, and the KeepTogether property is not set to None.
</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>All tablix member elements in a TablixColumnHierarchy must have the KeepWithGroup property as None.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Set KeepWithGroup property as "None" in a TablixColumnHierarchy for all TablixMember in the tablix report item.</td>
</tr>
</table>

## RV028

<table>

<tr>
<td>CODE</td><td>RV028</td>
</tr>

<tr>
<td>TEXT</td><td>The tablix has an invalid TablixMember in column hierarchy, and the RepeatOnNewPage property is not set to false.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>
All TablixMember elements in a TablixColumnHierarchy must have the RepeatOnNewPage property which is set to false.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Set RepeatOnNewPage property as "false" in a TablixColumnHierarchy for all TablixMembers.</td>
</tr>
</table>

## RV029

<table>

<tr>
<td>CODE</td><td>RV029</td>
</tr>

<tr>
<td>TEXT</td><td>Each dataset, data region, or grouping in the report has different name for their report item.<br>
Dataset, data region, and grouping names must be unique within a report.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report item referred dataset, data region, and grouping names must be unique within a report.<br>
Referred dataset, data region, and grouping names are different for their report item.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Provide unique dataset, data region, and grouping name for their report item in your report definition. <li>
Incorrect : Dataset name : Item1, Tablix name : Item1 </li>
<li> Correct : Dataset name : Item1, Tablix name : Item1 </li></td>
</tr>
</table>

## RV030

<table>

<tr>
<td>CODE</td><td>RV030</td>
</tr>

<tr>
<td>TEXT</td><td>The tablix has a detail member with inner members.<br>
Detail members contain only static inner members.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>In tablix report item, detail members contain only static inner members.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>In tablix report item, provide static inner members for their detail members.</td>
</tr>
</table>

## RV031

<table>

<tr>
<td>CODE</td><td>RV031</td>
</tr>

<tr>
<td>TEXT</td><td>A "ReportName" can not be an empty string or just white space.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>In SubReport item, the ReportName property value cannot be an empty or just white space.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Make sure that 'ReportName' property value for subreport item is non empty.</td>
</tr>
</table>

## RV032

<table>

<tr>
<td>CODE</td><td>RV032</td>
</tr>

<tr>
<td>TEXT</td><td>Subreport cannot be shown.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report viewer will not render the sub report without the ReportPath or ReportServerUrl.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Provide subreport ReportPath or ReportServerUrl in your report.</td>
</tr>
</table>

## RV033

<table>

<tr>
<td>CODE</td><td>RV033</td>
</tr>

<tr>
<td>TEXT</td><td>The subreport cannot be found at the specified location.
</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>
Report will not be rendered in the report viewer when the report does not exists in specified location.</td>
</tr>
<tr>
<td>SOLUTION</td>
<td>Make sure that the report name or path is correct, and the report exists in the specified directory.</td>
</tr>

</table>

## RV034

<table>

<tr>
<td>CODE</td><td>RV034</td>
</tr>

<tr>
<td>TEXT</td><td>RunningValue aggregate should contain 3 arguments.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>In aggregate expression, the RunningValue should have 3 arguments.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Make sure that RunningValue aggregate contains three arguments. <li>
Syntax: =RunningValue("FieldExpression", "Aggregate", "Scope")</li><li>
Example: =RunningValue(Fields!YearlyIncome.Value,Sum,"GroupByInitial")</li></td>
</tr>
</table>

## RV035

<table>

<tr>
<td>CODE</td><td>RV035</td>
</tr>

<tr>
<td>TEXT</td><td>Report variable or group variable reference cannot be used in report parameter expressions.
</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report viewer does not renders the report when the parameter contains group or report variables. Variable values cannot be used in report parameter expressions.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Remove the variable reference used in parameter expressions.</td>
</tr>
</table>

## RV036

<table>

<tr>
<td>CODE</td><td>RV036</td>
</tr>

<tr>
<td>TEXT</td><td>Fields cannot be used in report parameter expressions.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report viewer does not render the report when the parameter contains field expressions and fields cannot be used in report parameter expressions.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Remove the field expressions used in parameter expressions.</td>
</tr>
</table>

## RV037

<table>

<tr>
<td>CODE</td><td>RV037</td>
</tr>

<tr>
<td>TEXT</td><td>
Aggregate and lookup functions cannot be used in report parameter expressions.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>The value expression is used for report parameter, it includes an aggregate or lookup function.<br> Aggregate and lookup functions cannot be used in report parameter expressions.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Remove Aggregate and Lookup functions in your report parameter expressions.</td>
</tr>
</table>

## RV038

<table>

<tr>
<td>CODE</td><td>RV038</td>
</tr>

<tr>
<td>TEXT</td><td>ReportItem expressions can be referred only to fields within the current dataset.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>ReportItem expressions can be referred only to fields within the current dataset.<br>
Make sure that the field expression is referred to current dataset.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Provide current dataset fields for report item expression. <li> Note : Tablix report item with scope "Dataset1" must contain the fields in the dataset1. If field expression specified in another dataset is required then you should specify the scope. </li>
<li>Example: =First(Fields!Name.Value, "Dataset2")</li></td>
</tr>
</table>

## RV039

<table>

<tr>
<td>CODE</td><td>RV039</td>
</tr>

<tr>
<td>TEXT</td><td>Invalid Expression</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report viewer does not render the report when invalid expression is used.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Provide valid expression in respective report item.
<li> Note: Detailed description with line number and position is mentioned in the report viewer instance error dialog.</li> </td>
</tr>
</table>

## RV040

<table>

<tr>
<td>CODE</td><td>RV040</td>
</tr>

<tr>
<td>TEXT</td><td>Expression does not used within the scope.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report viewer encounters an error when expression must be used outside the scope.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Provide the valid expression within the scope.<li> Note: Detailed description with the line number and position is mentioned in the report viewer instance error dialog.</li> </td>
</tr>
</table>

## RV041

<table>

<tr>
<td>CODE</td><td>RV041</td>
</tr>

<tr>
<td>TEXT</td><td>An error is occurred during the local report processing. There is an error occurred while rendering the custom code.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report viewer encounters an error when compiling the custom code used in the report.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Provide valid custom code in your report based on detailed information mentioned in the report viewer instance error dialog.  <br>
Note: Custom code exists in report properties.
</td>
</tr>
</table>

## RV042

<table>

<tr>
<td>CODE</td><td>RV042</td>
</tr>

<tr>
<td>TEXT</td><td>Invalid operator is used in expression.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report viewer encounters an error if it contains invalid operator in an expression.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Make sure to use appropriate and supported operators in the expression.<li> Note: Detailed information is provided with the expression, and the report item name is mentioned in the report viewer instance error dialog.</li> </td>
</tr>
</table>

## RV043

<table>

<tr>
<td>CODE</td><td>RV043</td>
</tr>

<tr>
<td>TEXT</td><td>Unsupported Expression</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Provided expression does not support in the report viewer.<br>
Object expressions do not have complete support.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Please use supported expression in the report viewer to render the report.</td>
</tr>
</table>

## RV044

<table>

<tr>
<td>CODE</td><td>RV044</td>
</tr>

<tr>
<td>TEXT</td><td>Method name is not a member in custom code</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Evaluated method name is not a member in your custom code.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Provide valid method name. Make sure that the provided method name is present in your custom code.</td>
</tr>
</table>

## RV045

<table>

<tr>
<td>CODE</td><td>RV045</td>
</tr>

<tr>
<td>TEXT</td><td>Lookup function has incorrect number of parameters.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Provided lookup function has incorrect number of parameters in report definition.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Provide correct number of arguments for lookup expressions in respective report item expression, and refer the syntax of an look up expressions.</td>
</tr>
</table>

## RV046

<table>

<tr>
<td>CODE</td><td>RV046</td>
</tr>

<tr>
<td>TEXT</td><td>DateAdd function should have arguments.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report viewer encounters an error if "DateAdd" function does not contain any arguments.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Provide arguments for DateAdd function in respective report item expression, refer the syntax of an DateAdd functions. <br>
Example: =DateAdd("d",3,Fields!BirthDate.Value)</td>
</tr>
</table>

## RV047

<table>

<tr>
<td>CODE</td><td>RV047</td>
</tr>

<tr>
<td>TEXT</td><td>DateDiff function should contain arguments.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report viewer encounters an error if "DateDiff" function does not contain arguments in an expression.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Provide arguments for DateDiff function in respective report item expression, and refer the syntax of an DateDiff functions. <br>
Example: =DateDiff("yyyy",Fields!BirthDate.Value,"1/1/2010")</td>
</tr>
</table>

## RV048

<table>

<tr>
<td>CODE</td><td>RV048</td>
</tr>

<tr>
<td>TEXT</td><td>DatePart function should contain arguments.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report viewer encounters an error if "DatePart" function does not contain any arguments in an expression.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Provide arguments for DatePart function in respective report item expression, and refer the syntax of an DatePart functions. <br>
Example: =DatePart("q",Fields!BirthDate.Value,0,0)</td>
</tr>
</table>

## RV049

<table>

<tr>
<td>CODE</td><td>RV049</td>
</tr>

<tr>
<td>TEXT</td><td>DateSerial function should contain arguments.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report viewer encounters an error if "DateSerial" function does not contain any arguments in an expression.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Provide arguments for DateSerial function in respective report item expression, and refer the syntax of an DateSerial functions. <br>
Example: =DateSerial(DatePart("yyyy",Fields!BirthDate.Value)-10, DatePart("m",Fields!BirthDate.Value)+3,DatePart("d",Fields!BirthDate.Value)-1)</td>
</tr>
</table>

## RV050

<table>

<tr>
<td>CODE</td><td>RV050</td>
</tr>

<tr>
<td>TEXT</td><td>Provided IIF expression has invalid number of parameters.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report is not rendered in the report viewer when an "IIF" expression has invalid number of parameters.
</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Provide valid number arguments in your IIF expression. <li> Syntax: IIf(Expression As Boolean, TruePart As Object, FalsePart As Object) As Object </li></td>
</tr>
</table>

## RV051

<table>

<tr>
<td>CODE</td><td>RV051</td>
</tr>

<tr>
<td>TEXT</td><td>PaymentPeriod must be between 1 and numberOfPayments.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report viewer encounters an error if the payment period does not falls within the range.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Provide payment period value between 1 and numberOfPayments.</td>
</tr>
</table>

## RV052

<table>

<tr>
<td>CODE</td><td>RV052</td>
</tr>

<tr>
<td>TEXT</td><td>This implementation does not handle zero interest rate.</td>
</tr>

<tr>
<td>DESCRIPTION</td><td>Report is not rendered in the report viewer when it holds the zero interest rate.</td>
</tr>

<tr>
<td>SOLUTION</td>
<td>Provide greater than 0 or less than 0 interest rate. Does not provide 0 value for their interest rate.</td>
</tr>
</table>





