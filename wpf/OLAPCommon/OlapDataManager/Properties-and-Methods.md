---
layout: post
title: Properties-and-Methods
description: properties and methods
platform: wpf
control: OLAP Common 
documentation: ug
---

# Properties and Methods

## Properties

### The properties and their descriptions are tabulated below:





_Table4: Properties_

<table>
<tr>
<th>
Property Name</th><th colspan = "2">
Description</th><th colspan = "2">
Type</th><th colspan = "2">
Value it Accepts</th><th>
Reference Link</th></tr>
<tr>
<td colspan = "2">
ConnectionString</td><td colspan = "2">
Used to pass the connection string to establish the connection. The user can also get the connection string using this property.</td><td colspan = "2">
string</td><td>
String</td><td>
-</td></tr>
<tr>
<td colspan = "2">
CurrentCellSet</td><td colspan = "2">
The user can get the CellSet of their input from here.</td><td colspan = "2">
CellSet</td><td>
-</td><td>
-</td></tr>
<tr>
<td colspan = "2">
CurrentCubeName</td><td colspan = "2">
Used to set or get the current cube name. When set, the whole data procession will change to the specified cube name.</td><td colspan = "2">
string</td><td>
String</td><td>
-</td></tr>
<tr>
<td colspan = "2">
CurrentCubeSchema</td><td colspan = "2">
The user can get the CubeSchema of the currently connected cube.</td><td colspan = "2">
CubeSchema</td><td>
-</td><td>
-</td></tr>
<tr>
<td colspan = "2">
CurrentReport</td><td colspan = "2">
Used to load an OlapReport or get the currently loaded report.</td><td colspan = "2">
OlapReport</td><td>
OlapReport</td><td>
OlapReport</td></tr>
<tr>
<td colspan = "2">
DataProvider</td><td colspan = "2">
Used to set a data provider and get the existing data provider.</td><td colspan = "2">
IDataProvider</td><td>
IDataProvider</td><td>
DataProvider</td></tr>
<tr>
<td colspan = "2">
IsCurrentReportModified</td><td colspan = "2">
Used to get or set the modified status of the currently loaded report.</td><td colspan = "2">
bool</td><td>
True/False</td><td>
-</td></tr>
<tr>
<td colspan = "2">
MdxQuery</td><td colspan = "2">
Used to pass the MDX query as input.</td><td colspan = "2">
string</td><td>
String</td><td>
MdxQuery</td></tr>
<tr>
<td>
PivotEngine</td><td colspan = "2">
Used to get the PivotEngine for the given input.</td><td colspan = "2">
PivotEngine</td><td colspan = "2">
PivotEngine</td><td>
-</td></tr>
<tr>
<td>
QuerySpecification</td><td colspan = "2">
Used to get the MDXQuerySpecification for the given OlapReport.</td><td colspan = "2">
MDXQuerySpecification</td><td colspan = "2">
-</td><td>
QuerySpecification</td></tr>
<tr>
<td>
ReportPath</td><td colspan = "2">
Used to get or set the report path to store the report as an XML file.</td><td colspan = "2">
string</td><td colspan = "2">
-</td><td>
-</td></tr>
<tr>
<td>
Reports</td><td colspan = "2">
Contains the report collection of the OlapDataManager.</td><td colspan = "2">
OlapReportCollection</td><td colspan = "2">
OlapReportCollection</td><td>
-</td></tr>
</table>






_Table5: Methods_

<table>
<tr>
<th>
Method Name</th><th>
Description</th><th>
Parameters</th><th>
Return Type</th><th>
Reference Link</th></tr>
<tr>
<td>
AddReport</td><td>
Used to add a new OlapReport to the report collection of OlapDataManager.</td><td>
OlapReport</td><td>
Void</td><td>
-</td></tr>
<tr>
<td>
CloneOlapDataManager</td><td>
Create a clone from the current state of OlapDataManager and return the new copy of OlapDataManager. The IDataProvider will be same for both the managers.</td><td>
-</td><td>
OlapDataManager</td><td>
-</td></tr>
<tr>
<td>
ExecuteCellSet</td><td>
This is an overloaded method that can be invoked by calling or by passing the MDXQuerySpecification or by passing the MDX query as string. This method will invoke the data processing and will return the processed CellSet, which will be further formatted. </td><td>
-</td><td>
CellSet</td><td>
ExecuteCellSet</td></tr>
<tr>
<td>
ExecuteOlapTable</td><td>
Used to create pivot engine from the CellSet.</td><td>
-</td><td>
PivotEngine</td><td>
</td></tr>
<tr>
<td>
GetMDXQuery</td><td>
This method will generate the MDX query from the MDXQuerySpecification and return the query as a string.</td><td>
-</td><td>
string</td><td>
-</td></tr>
<tr>
<td>
GetReport</td><td>
This method will return the OlapReport collection by giving the Xml report file name as an input.</td><td>
string</td><td>
OlapReportCollection</td><td>
-</td></tr>
<tr>
<td>
GetReportAsStream</td><td>
This method will return the current report collection along with current state of OlapDataManager as a Stream.</td><td>
-</td><td>
Stream</td><td>
GetReportAsStream</td></tr>
<tr>
<td>
LoadOlapDataManager</td><td>
Will accept the OlapReport as argument and Load the OlapDataManager with the given OlapReport.</td><td>
OlapReport</td><td>
Void</td><td>
LoadOlapDataManager</td></tr>
<tr>
<td>
LoadReport</td><td>
Used to get the report name as an argument and pick the specified report from the report collection to load the OlapDataManager with that report.</td><td>
string</td><td>
Void</td><td>
-</td></tr>
<tr>
<td>
LoadReportDefinitionFile</td><td>
Used to get the XML report file as input and load the OlapDataManager with the report in that file.</td><td>
string</td><td>
Void</td><td>
LoadReportDefinitionFile</td></tr>
<tr>
<td>
LoadReportDefinitionFromStream</td><td>
Used to get a stream as input and read the report from that stream and load the OlapDataManager with that report.</td><td>
Stream</td><td>
Void</td><td>
LoadReportDefinitionFromStream</td></tr>
<tr>
<td>
NotifyElementModified</td><td>
Used to trigger the ElementModified event.</td><td>
-</td><td>
Void</td><td>
-</td></tr>
<tr>
<td>
NotifyReportChanged</td><td>
Used to trigger the ReportChanged event.</td><td>
-</td><td>
Void</td><td>
-</td></tr>
<tr>
<td>
RemoveReport</td><td>
Used to get the report name as input and remove that report from report collection.</td><td>
string</td><td>
Void</td><td>
RemoveReport</td></tr>
<tr>
<td>
RenameReport</td><td>
Used to rename the current report of OlapDataManager.</td><td>
Index as int and new Report Name as string</td><td>
void</td><td>
RenameReport</td></tr>
<tr>
<td>
SaveReport</td><td>
Used to get the file name and store the current report collection along the current state of the OlapDataManager as an Xml file.</td><td>
string</td><td>
Void</td><td>
SaveReport</td></tr>
<tr>
<td>
SetCurrentReport</td><td>
Used to set an OlapReport as the current report of the OlapDataManager. This method is the initial method that will start data processing.</td><td>
OlapReport</td><td>
Void</td><td>
SetCurrentReport</td></tr>
</table>


