---
layout: post
title: Data Binding in WPF Olap Chart control | Syncfusion
description: Learn about Data Binding support in Syncfusion WPF Olap Chart control, its elements and more details.
platform: wpf
control: OLAP Chart
documentation: ug
---

# Data Binding in WPF Olap Chart

## Binding OLAP chart to offline cube

To connect to an OLAP cube available in the local machine, set the physical path of the cube set in the connection string. The following code sample illustrates the same.

{% highlight c# %}

string connectionString = @"DataSource = system drive:\OfflineCube\Adventure_Works_Ext.cub; Provider = MSOLAP;";
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding OLAP chart to cube in local SQL Server

To connect to the OLAP cube available in SQL Server Analysis Service in the local machine, set the server name and database name in the connection string. If you have any credentials to connect your cube, then set the user ID and password attributes accordingly. The following code sample illustrates the same.

{% highlight c# %}

string connectionString = "Data source=localhost; Initial Catalog=Adventure Works DW;"; 
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding OLAP chart to cube in online SQL Server

To connect to the OLAP cube available in SQL Server Analysis Service in the online server through **XML/A**, set the host server link and database name in the connection string. If you have any credentials to connect your cube, then set the user ID and password attributes accordingly. The following code sample illustrates the same.

{% highlight c# %}

string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;"; 
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding OLAP chart to cube in online Mondrian Server

To connect to the OLAP cube available in the Mondrian Server through **XML/A**, set the host server link and database name in the connection string. If you have any credentials to connect your cube, then set the user ID and password attributes accordingly. The following code sample illustrates the same.

{% highlight c# %}

string connectionString = @"Data Source = http://localhost:8080/mondrian/xmla; Initial Catalog =FoodMart;";
OlapDataManager DataManager = new OlapDataManager(connectionString);
DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.Mondrian;

{% endhighlight %}

## Binding OLAP chart to cube in online ActivePivot Server

To connect to the OLAP cube available in the ActivePivot Server through **XML/A**, set the host server link and database name in the connection string. If you have any credentials to connect your cube, then set the user ID and password attributes accordingly. The following code sample illustrates the same.

{% highlight c# %}

string connectionString = @"Data Source = http://localhost:8080/cva_s/xmla; Initial Catalog = CVAS;";
OlapDataManager DataManager = new OlapDataManager(connectionString);
DataManager.DataProvider.ProviderName=Syncfusion.Olap.DataProvider.Providers.ActivePivot;

{% endhighlight %}
