---
layout: post
title: OlapDataManager| OLAPCommon  | Wpf | Syncfusion
description: olapdatamanager
platform: wpf
control: OLAPCommon 
documentation: ug
---

# OlapDataManager

OlapDataManager is the most important class in the whole OLAP Base. All the information transfers from the control to OLAP base will happen through this class and this will retain the current state of the base objects. The connection is established in the Data provider of the OLAP Base, but the information required in establishing the connection is given to the data provider through the OlapDataManager. 


### Constructors

<table>
<tr>
<th>
Constructors</th><th>
Description</th><th>
Parameters</th><th>
Return Type</th><th>
Reference Link</th></tr>
<tr>
<td>
OlapDataManager()</td><td>
Default constructor</td><td>
-</td><td>
Void</td><td>
-</td></tr>
<tr>
<td>
OlapDataManager(string)</td><td>
Accepts the connection string as argument and passes it to the Data Provider to establish the connection with data source.</td><td>
String</td><td>
Void</td><td>
-</td></tr>
<tr>
<td>
OlapDataManager(AdomdDataProvider)</td><td>
Accepts the Data Provider as argument and processes the cube that is connected with the given data provider.</td><td>
AdomdDataProvider</td><td>
Void</td><td>
-</td></tr>
</table>


## Establishing connection with the SSAS server

The following code snippet describes establishing connection with the server:

{% tabs %}
{% highlight c# %}


OlapDataManager olapDataManager = new OlapDataManager("DataSource=localhost; Initial Catalog=Adventure Works DW");
{% endhighlight  %}


{% highlight vbnet %}

OlapDataManager olapDataManager = New OlapDataManager("DataSource=localhost; Initial Catalog=Adventure Works DW")


{% endhighlight  %}
{% endtabs %}





## Establishing Connection with the SSAS server through Data Provider

The following code snippet describes establishing connection with the server:

{% tabs %}
{% highlight c# %}



AdomdDataProvider dataProvider = new AdomdDataProvider("DataSource=localhost; Initial Catalog=Adventure Works DW");

OlapDataManager olapDataManager = new OlapDataManager(dataProvider);

{% endhighlight  %}

{% highlight vbnet %}



Dim dataProvider As AdomdDataProvider = New AdomdDataProvider("DataSource=localhost; Initial Catalog=Adventure Works DW")

Dim olapDataManager As OlapDataManager = New OlapDataManager(dataProvider) 

{% endhighlight  %}
{% endtabs %}

## Establishing connection with the offline cube

The following code snippet describes establishing connection with the offline cube:

{% tabs %}
{% highlight c# %}


OlapDataManager olapDataManager = new OlapDataManager(@"Data Source = C:\ Common\Data\OfflineCube\Adventure_Works_Ext.cub; Provider = MSOLAP;");

{% endhighlight  %}



{% highlight vbnet %}



OlapDataManager olapDataManager = New OlapDataManager("Data Source = C:\\ Common\\Data\\OfflineCube\\Adventure_Works_Ext.cub; Provider = MSOLAP;") 

{% endhighlight  %}
{% endtabs %}


## Establishing connection with XMLA Server:

XML for Analysis (XMLA) is a standard that allows the client applications to transfer multi-dimensional or OLAP data sources, which is available in the Mondrian Server. The back and forth communication is done using the web standards – HTTP, SOAP, and XML.  The query language used is MDX, is most widely supported for reporting from multi-dimensional data stores.



### Use Case Scenarios



XMLA provides the most efficient way to access an OLAP database over the Internet.



## Connecting to Mondrian Server 



The following code illustrates how to connect to the Mondrian server:


{% tabs %}
{% highlight c# %}



// Connecting to Mondrian Server

OlapDataManager DataManager = new OlapDataManager("Data Source = http://localhost:8080/mondrian/xmla; Initial Catalog = FoodMart;");

DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.Mondrian;


{% endhighlight  %}


{% highlight vbnet %}



' Connecting to Mondrian Server 

Dim DataManager As OlapDataManager = New OlapDataManager("Datasource = http://bi.syncfusion.com:8080/mondrian/xmla; Initial Catalog=FoodMart;")

DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.Mondrian


{% endhighlight  %}
{% endtabs %}

[Click here](http://mondrian.pentaho.com/) for more information about Mondrian XMLA configurations.



## Connecting to Active Pivot Server 

 The following code illustrates how to connect to Active Pivot server:

 {% tabs %}
{% highlight c# %}



// Connecting to Active Pivot Server

OlapDataManager DataManager = new OlapDataManager(@"Data Source=http://localhost:8081/var_s/xmla;  Initial Catalog=VaRCubes; User ID=; Password=; Transport Compression=None;");

DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.ActivePivot;

{% endhighlight  %}



{% highlight vbnet %}



' Connecting to Active Pivot Server 

Dim DataManager As OlapDataManager = New OlapDataManager("Data Source=http://localhost:8081/var_s/xmla;  Initial Catalog=VaRCubes; User ID=; Password=; Transport Compression=None;")

DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.ActivePivot

{% endhighlight  %}
{% endtabs %}


[Click here](http://quartetfs.com/) for more information on Active Pivot server.



###  Properties

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




### Methods

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

## UseWhereClauseForSlicing

The UseWhereClauseForSlicing property facilitates the user to decide whether the MDX query parser engine should consider ‘Where’ or ‘Select’ clause for slicing data.

### Use Case Scenarios

While slicing dimensions with a specific range of measures using ‘Select’ clause in MDX query, an exception is thrown. This can be resolved by using the ‘Where’ clause for slicing.

Example: Slicing the Date dimension from months of 2002 to months of 2003 will throw an exception when ‘Select’ clause is used. 

### Properties



<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th><th>
Reference links </th></tr>
<tr>
<td>
UseWhereClauseForSlicing</td><td>
Enables the user to decide whether the MDX Query Parser Engine should consider the ‘Where’ or ‘Select’ clause for slicing operation</td><td>
Server side </td><td>
Boolean</td><td>
----</td></tr>
</table>


## Drill Through

This feature enables the user to drill through any value and see the data which formed the value.

The following code snippet illustrates how to drill through using MDX Query in OlapDataManager:

{% tabs %}
{% highlight c# %}

string query = @"drillthrough Select { [Customer].[Customer Geography].[Country].&[Australia] } on 0, { [Date].[Fiscal].[Fiscal Year].&[2002] } on 1 from [Adventure Works] Where [Internet Sales Amount]";

// executing the drill-through operation.

olapDataManager.Execute(query);
{% endhighlight  %}


{% highlight vbnet %}

Dim query As String = "drillthrough Select { [Customer].[Customer Geography].[Country].&[Australia] } on 0, { [Date].[Fiscal].[Fiscal Year].&[2002] } on 1 from [Adventure Works] Where [Internet Sales Amount]" 

'Executing the drill-through operation.

olapDataManager.Execute(query)


{% endhighlight  %}

{% endtabs %}






