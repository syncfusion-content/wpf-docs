---
layout: post
title: OlapDataManager in WPF OLAP Common control | Syncfusion
description: Learn about OlapDataManager support in Syncfusion WPF OLAP Common control and more.
platform: wpf
control: OLAP Common
documentation: ug
---

# OlapDataManager in WPF OLAP Common

OlapDataManager is the most important class in the whole OLAP base. All the information are transferred from the control to OLAP base through this class and this will retain the current state of the base objects. The connection is established in the data provider of the OLAP base, but the information required in establishing the connection is given to the data provider through the OlapDataManager.


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
Accepts the connection string as an argument and passes it to the data provider to establish the connection with data source.</td><td>
String</td><td>
Void</td><td>
-</td></tr>
<tr>
<td>
OlapDataManager(AdomdDataProvider)</td><td>
Accepts the data provider as an argument and processes the cube that is connected with the given data provider.</td><td>
AdomdDataProvider</td><td>
Void</td><td>
-</td></tr>
</table>


## Establishing connection with the SSAS server

The following code snippet describes establishing connection with the server.

{% tabs %}
{% highlight c# %}


OlapDataManager olapDataManager = new OlapDataManager("DataSource=localhost; Initial Catalog=Adventure Works DW");
{% endhighlight  %}


{% highlight vbnet %}

OlapDataManager olapDataManager = New OlapDataManager("DataSource=localhost; Initial Catalog=Adventure Works DW")


{% endhighlight  %}
{% endtabs %}





## Establishing connection with the SSAS server through data provider

The following code snippet describes establishing connection with the server.

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

The following code snippet describes establishing connection with the offline cube.

{% tabs %}
{% highlight c# %}


OlapDataManager olapDataManager = new OlapDataManager(@"Data Source = C:\ Common\Data\OfflineCube\Adventure_Works_Ext.cub; Provider = MSOLAP;");

{% endhighlight  %}



{% highlight vbnet %}



OlapDataManager olapDataManager = New OlapDataManager("Data Source = C:\\ Common\\Data\\OfflineCube\\Adventure_Works_Ext.cub; Provider = MSOLAP;") 

{% endhighlight  %}
{% endtabs %}


## Establishing connection with XMLA Server

XML for Analysis (XMLA) is a standard that allows the client applications to transfer multi-dimensional or OLAP data sources, which is available in the Mondrian Server. The back and forth communication is done using the web standards – HTTP, SOAP, and XML. The query language used is MDX, which is most widely supported for reporting from multi-dimensional data stores.



## Connecting to Mondrian Server



The following code illustrates how to connect to the Mondrian Server.


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

 The following code illustrates how to connect to the Active Pivot Server.

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



## Connecting to SAP Business Warehouse Server 

 The following code illustrates how to connect to the SAP Business Warehouse server.

 {% tabs %}
{% highlight c# %}



// Connecting to SAP BW Server

OlapDataManager DataManager = new OlapDataManager(@"Data Source= http://sapdomain:50000/sap/bw/xml/soap/xmla; Initial Catalog=$INFOCUBE; User ID=username; Password=password;");

DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.SAPBW;

{% endhighlight  %}



{% highlight vbnet %}



' Connecting to SAP BW Server 

Dim DataManager As OlapDataManager = New OlapDataManager("Data Source= http://sapdomain:50000/sap/bw/xml/soap/xmla; Initial Catalog=$INFOCUBE; User ID=username; Password=password;")

DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.SAPBW

{% endhighlight  %}
{% endtabs %}


[Click here](https://www.sap.com/index.html) for more information on SAP BW server.



###  Properties

* **ConnectionString**: Passes the connection string to establish the connection. Users can also get the connection string using this property.
* **CurrentCellSet**: Gets the CellSet of user's input from here.
* **CurrentCubeName**: Sets or gets the current cube name. When set, the whole data procession will change to the specified cube name.
* **CurrentCubeSchema**: Gets the CubeSchema of the currently connected cube.
* **CurrentReport**: Loads an OlapReport or get the currently loaded report.
* **DataProvider**: Sets a data provider and gets the existing data provider.
* **IsCurrentReportModified**: Gets or sets the modified status of the currently loaded report.
* **MdxQuery**: Passes the MDX query as input.
* **PivotEngine**: Gets the pivot engine for the given input.
* **QuerySpecification**: Gets the MDXQuerySpecification for the given OlapReport.
* **ReportPath**: Gets or sets the report path to store the report as an XML file.
* **Reports**: Contains the report collection of the OlapDataManager.


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
This is an overloaded method that can be invoked by calling or passing the MDXQuerySpecification or by passing the MDX query as a string. This method invokes the data processing and returns the processed CellSet, which will be further formatted.</td><td>
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
This method generates an MDX query from the MDXQuerySpecification and returns the query as a string.</td><td>
-</td><td>
string</td><td>
-</td></tr>
<tr>
<td>
GetReport</td><td>
This method returns the OlapReport collection by giving the XML report file name as an input.</td><td>
string</td><td>
OlapReportCollection</td><td>
-</td></tr>
<tr>
<td>
GetReportAsStream</td><td>
This method returns the current report collection along with current state of OlapDataManager as a stream.</td><td>
-</td><td>
Stream</td><td>
GetReportAsStream</td></tr>
<tr>
<td>
LoadOlapDataManager</td><td>
Used to accept the OlapReport as an argument and loads the OlapDataManager with the given OlapReport.</td><td>
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
Used to get the XML report file as an input and load the OlapDataManager with the report in that file.</td><td>
string</td><td>
Void</td><td>
LoadReportDefinitionFile</td></tr>
<tr>
<td>
LoadReportDefinitionFromStream</td><td>
Used to get a stream as an input and read the report from that stream and load the OlapDataManager with that report.</td><td>
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
Used to get the report name as an input and remove that report from the report collection.</td><td>
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
Used to get the file name and store the current report collection along the current state of the OlapDataManager as an XML file.</td><td>
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


### Properties

* **UseWhereClauseForSlicing**: Enables users to decide whether the MDX Query Parser Engine should consider the ‘Where’ or ‘Select’ clause for slicing operation.

## Drill through

This feature enables the user to drill through any value and see the data which formed the value.

The following code snippet illustrates how to drill through using the MDX Query in OlapDataManager.

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






