---
layout: post
title: Data Binding in WPF OLAP Gauge | Syncfusion®
description: Data binding in the WPF OLAP Gauge connects multidimensional data sources to gauge elements, enabling dynamic visualization and analysis.
platform: wpf
control: OLAP Gauge
documentation: ug
---

# Data Binding in WPF OLAP Gauge

## Binding a WPF OLAP Gauge to an offline cube

To connect to an OLAP cube available on the local machine, the physical path of the cube should be specified in the connection string. The following code snippet illustrates the same.

{% highlight c# %}

string connectionString = @"DataSource = system drive:\Cube\Adventure_Works_Ext.cub; Provider = MSOLAP;";
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding a WPF OLAP Gauge to a cube in local SQL Server

To connect to the OLAP cube available in SQL Server Analysis Services on the local machine, the server name and database name should be specified in the connection string. The following code example illustrates the same.

N> If credentials are required to connect to the cube, specify the user ID and password accordingly.

{% tabs %}

{% highlight c# %}

string connectionString = "Data source=localhost; Initial Catalog=Adventure Works DW;";
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

{% highlight vb %}

Dim connectionString As String = "Data source=localhost; Initial Catalog=Adventure Works DW;"
Dim DataManager As New OlapDataManager(connectionString)

{% endhighlight %}

{% endtabs %}

## Binding WPF OLAP Gauge to cube in online SQL Server

To connect to the OLAP cube available in SQL server Analysis Services on a the online server through **XML/A**, the host server link and database name should be specified in the connection string. The following code example illustrates the same.

N> If credentials are required to connect to the cube, specify the user ID and password accordingly.

{% tabs %}

{% highlight c# %}

string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

{% highlight vb %}

Dim connectionString As String = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;"
Dim DataManager As New OlapDataManager(connectionString)

{% endhighlight %}

{% endtabs %}

## Binding WPF OLAP Gauge to cube in online Mondrian server

To connect to the OLAP cube available on a Mondrian server through **XML/A**, the host server link and database name should be specified in the connection string. The following code example illustrates the same.

N> If credentials are required to connect to the cube, specify the user ID and password accordingly.

{% tabs %}

{% highlight c# %}

string connectionString = @"Data Source = http://localhost:8080/mondrian/xmla; Initial Catalog =FoodMart;";
OlapDataManager DataManager = new OlapDataManager(connectionString);
DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.Mondrian;

{% endhighlight %}

{% highlight vb %}

Dim connectionString As String = "Data Source = http://localhost:8080/mondrian/xmla; Initial Catalog =FoodMart;"
Dim DataManager As New OlapDataManager(connectionString)
DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.Mondrian

{% endhighlight %}

{% endtabs %}

## Binding WPF OLAP Gauge to cube in online ActivePivot Server

To connect to the OLAP cube available in ActivePivot Server through **XML/A**, the host server link and database name should be specified in the connection string. The following code example illustrates the same.

N> If credentials are required to connect to the cube, specify the user ID and password accordingly.

{% tabs %}

{% highlight c# %}

string connectionString = @"Data Source = http://localhost:8080/cva_s/xmla; Initial Catalog = CVAS;";
OlapDataManager DataManager = new OlapDataManager(connectionString);
DataManager.DataProvider.ProviderName=Syncfusion.Olap.DataProvider.Providers.ActivePivot;

{% endhighlight %}

{% highlight vb %}

Dim connectionString As String = "Data Source = http://localhost:8080/cva_s/xmla; Initial Catalog = CVAS;"
Dim DataManager As New OlapDataManager(connectionString)
DataManager.DataProvider.ProviderName=Syncfusion.Olap.DataProvider.Providers.ActivePivot

{% endhighlight %}

{% endtabs %}
