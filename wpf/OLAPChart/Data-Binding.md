---
layout: post
title: Data-Binding| OlapChart | Wpf | Syncfusion
description: data binding
platform: wpf
control: OlapChart
documentation: ug
---

# Data Binding

## Binding OlapChart to Offline Cube

To connect an OLAP Cube available in local machine, set the physical path of the Cube set in the connection string. The following code sample illustrates the same.

{% highlight c# %}

	string connectionString = @"DataSource = system drive:\OfflineCube\Adventure_Works_Ext.cub; Provider = MSOLAP;";
	OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding OlapChart to Cube in local SQL Server

To connect an OLAP Cube available in SQL Server Analysis Service in local machine, set the server name and database name in the connection string. When you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. The following code sample illustrates the same.

{% highlight c# %}

	string connectionString = "Data source=localhost; Initial Catalog=Adventure Works DW;"; 
	OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding OlapChart to Cube in online SQL Server

To connect an OLAP Cube available in SQL Server Analysis Service in online server through **XML/A**, set the host server link and database name in the connection string. When you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. The following code sample illustrates the same.

{% highlight c# %}

	string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;"; 
	OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding OlapChart to Cube in online Mondrian Server

To connect an OLAP Cube available in Mondrian Server through **XML/A**, set the host server link and database name in the connection string. When you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. The following code sample illustrates the same.

{% highlight c# %}

	string connectionString = @"Data Source = http://localhost:8080/mondrian/xmla; Initial Catalog =FoodMart;";
	OlapDataManager DataManager = new OlapDataManager(connectionString);
	DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.Mondrian;

{% endhighlight %}

## Binding OlapChart to Cube in online ActivePivot Server

To connect an OLAP Cube available in ActivePivot Server through **XML/A**, set the host server link and database name in the connection string. When you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. The following code sample illustrates the same.

{% highlight c# %}

	string connectionString = @"Data Source = http://localhost:8080/cva_s/xmla; Initial Catalog = CVAS;";
	OlapDataManager DataManager = new OlapDataManager(connectionString);
	DataManager.DataProvider.ProviderName=Syncfusion.Olap.DataProvider.Providers.ActivePivot;

{% endhighlight %}
