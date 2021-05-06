---
layout: post
title: Data Binding in WPF Olap Gauge control | Syncfusion
description: Learn about Data Binding support in Syncfusion WPF Olap Gauge control and more.
platform: wpf
control: OLAP Gauge
documentation: ug
---

# Data Binding in WPF Olap Gauge

## Binding an OLAP gauge to offline cube

To connect to an OLAP cube available in the local machine, the physical path of the cube should be specified in the connection string. The following code snippet illustrates the same.

{% highlight c# %}

string connectionString = @"DataSource = system drive:\Cube\Adventure_Works_Ext.cub; Provider = MSOLAP;";
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding OLAP gauge to cube in local SQL Server

To connect to the OLAP cube available in SQL Server Analysis Service in the local machine, the server name and database name should be specified in the connection string. The following code example illustrates the same.

N> If any credentials are maintained to connect the cube, then the user ID and password attributes should be mentioned accordingly.

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

## Binding OLAP gauge to cube in online SQL Server

To connect to the OLAP cube available in SQL server Analysis Service in the online server through **XML/A**, the host server link and database name should be specified in the connection string. The following code example illustrates the same.

N> If any credentials are maintained to connect the cube, then the user ID and password attributes should be mentioned accordingly.

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

## Binding OLAP gauge to cube in online Mondrian server

To connect to the OLAP cube available in Mondrian server through **XML/A**, the host server link and database name should be specified in the connection string. The following code example illustrates the same.

N> If any credentials are maintained to connect the cube, then the user ID and password attributes should be mentioned accordingly.

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

## Binding OLAP gauge to cube in online ActivePivot Server

To connect to the OLAP cube available in ActivePivot server through **XML/A**, the host server link and database name should be specified in the connection string. The following code example illustrates the same.

N> If any credentials are maintained to connect the cube, then the user ID and password attributes should be mentioned accordingly.

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
