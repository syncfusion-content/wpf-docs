---
layout: post
title: OlapDataManager
description: olapdatamanager
platform: wpf
control: OLAP Common 
documentation: ug
---

# OlapDataManager

OlapDataManager is the most important class in the whole OLAP Base. All the information transfers from the control to OLAP base will happen through this class and this will retain the current state of the base objects. The connection is established in the Data provider of the OLAP Base, but the information required in establishing the connection is given to the data provider through the OlapDataManager. 



_Table3: Constructors_

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

{% highlight c# %}


OlapDataManager olapDataManager = new OlapDataManager("DataSource=localhost; Initial Catalog=Adventure Works DW");
{% endhighlight  %}


{% highlight vbnet %}

OlapDataManager olapDataManager = New OlapDataManager("DataSource=localhost; Initial Catalog=Adventure Works DW")


{% endhighlight  %}


Or



## Establishing Connection with the SSAS server through Data Provider

The following code snippet describes establishing connection with the server:

{% highlight c# %}



AdomdDataProvider dataProvider = new AdomdDataProvider("DataSource=localhost; Initial Catalog=Adventure Works DW");

OlapDataManager olapDataManager = new OlapDataManager(dataProvider);

{% endhighlight  %}

{% highlight vbnet %}



Dim dataProvider As AdomdDataProvider = New AdomdDataProvider("DataSource=localhost; Initial Catalog=Adventure Works DW")

Dim olapDataManager As OlapDataManager = New OlapDataManager(dataProvider) 

{% endhighlight  %}

## Establishing connection with the offline cube

The following code snippet describes establishing connection with the offline cube:

{% highlight c# %}


OlapDataManager olapDataManager = new OlapDataManager(@"Data Source = C:\ Common\Data\OfflineCube\Adventure_Works_Ext.cub; Provider = MSOLAP;");

{% endhighlight  %}



{% highlight vbnet %}



OlapDataManager olapDataManager = New OlapDataManager("Data Source = C:\\ Common\\Data\\OfflineCube\\Adventure_Works_Ext.cub; Provider = MSOLAP;") 

{% endhighlight  %}



## Establishing connection with XMLA Server:

XML for Analysis (XMLA) is a standard that allows the client applications to transfer multi-dimensional or OLAP data sources, which is available in the Mondrian Server. The back and forth communication is done using the web standards – HTTP, SOAP, and XML.  The query language used is MDX, is most widely supported for reporting from multi-dimensional data stores.



## Use Case Scenarios



XMLA provides the most efficient way to access an OLAP database over the Internet.



## Connecting to Mondrian Server 



The following code illustrates how to connect to the Mondrian server:



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


[Click here](http://mondrian.pentaho.com/) for more information about Mondrian XMLA configurations.



## Connecting to Active Pivot Server 

 The following code illustrates how to connect to Active Pivot server:

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



[Click here](http://quartetfs.com/) for more information on Active Pivot server.













