---
layout: post
title: Data Binding
description: Binding OLAP Client to OLAP Cube
platform: wpf
control: OLAP Client
documentation: ug
---

# Data Binding

## Binding OlapClient to Offline Cube

To connect an OLAP Cube available in local machine, set the physical path of the Cube set in the connection string. The following code example illustrates the same.

{% tabs %}

{% highlight c# %}  

string connectionString = @"Datasource = systemdrive:\OfflineCube\Adventure_Works_Ext.cub; Provider= msolap;";
OlapDataManager olapDataManager = new OlapDataManager(connectionString);
this.olapClient1.OlapDataManager = olapDataManager;
this.olapClient1.DataBind();

{% endhighlight %}

{% highlight vbnet %} 

Dim connectionString As String = @"Datasource = systemdrive:\OfflineCube\Adventure_Works_Ext.cub; Provider= msolap;"
Dim olapDataManager As OlapDataManager = New OlapDataManager(connectionString)
Me.olapClient1.OlapDataManager = olapDataManager
Me.olapClient1.DataBind()

{% endhighlight %}

{% endtabs %}

## Binding OlapClient to Cube in local SQL Server

To connect an OLAP Cube available in SQL Server Analysis Service in local machine, set the server name and database name in the connection string. When you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. The following code example illustrates the same.

{% tabs %}

{% highlight c# %}  

string connectionString = "Data source=localhost; Initial Catalog=Adventure Works DW";
OlapDataManager olapDataManager = new OlapDataManager(connectionString);
this.olapClient1.OlapDataManager = olapDataManager;
this.olapClient1.DataBind();

{% endhighlight %} 

{% highlight vbnet %} 

Dim connectionString As String = "Datasource = localhost; Initial Catalog=Adventure Works DW"
Dim olapDataManager As OlapDataManager = New OlapDataManager(connectionString)
Me.olapClient1.OlapDataManager = olapDataManager
Me.olapClient1.DataBind()

{% endhighlight %}

{% endtabs %}

## Binding OlapClient to Cube in online SQL Server

To connect an OLAP Cube available in SQL Server Analysis Service in online server through XML/A, set the host server link and database name in the connection string. When you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. The following code example illustrates the same.

{% tabs %}

{% highlight C# %}  

string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
OlapDataManager olapDataManager = new OlapDataManager(connectionString);
this.olapClient1.OlapDataManager = olapDataManager;
this.olapClient1.DataBind();

{% endhighlight %} 

{% highlight vbnet %} 

Dim connectionString As String = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;"
Dim olapDataManager As OlapDataManager = New OlapDataManager(connectionString)
Me.olapClient1.OlapDataManager = olapDataManager
Me.olapClient1.DataBind()

{% endhighlight %}

{% endtabs %}

## Binding OlapClient to Cube in online Mondrian Server

To connect an OLAP Cube available in Mondrian Server through XML/A, set the host server link and database name in the connection string. When you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. The following code example illustrates the same.

{% tabs %}

{% highlight c# %}  

string connectionString = @"Data Source = http://localhost:8080/mondrian/xmla; Initial Catalog =FoodMart;";
OlapDataManager olapDataManager = new OlapDataManager(connectionString);
olapDataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.Mondrian;
this.olapClient1.OlapDataManager = olapDataManager;
this.olapClient1.DataBind();

{% endhighlight %} 

{% highlight vbnet %} 

Dim connectionString As String = @"Data Source = http://localhost:8080/mondrian/xmla; Initial Catalog =FoodMart;"
Dim olapDataManager As OlapDataManager = New OlapDataManager(connectionString)
olapDataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.Mondrian;
Me.olapClient1.OlapDataManager = olapDataManager
Me.olapClient1.DataBind()

{% endhighlight %}

{% endtabs %}

## Binding OlapClient to Cube in online ActivePivot Server

To connect an OLAP Cube available in ActivePivot Server through XML/A, set the host server link and database name in the connection string. When you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. The following code example illustrates the same.

{% tabs %}

{% highlight c# %}  

string connectionString = @"Data Source = http://localhost:8080/cva_s/xmla; Initial Catalog = CVAS;";
OlapDataManager olapDataManager = new OlapDataManager(connectionString);
olapDataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.ActivePivot;
this.olapClient1.OlapDataManager = olapDataManager;
this.olapClient1.DataBind();

{% endhighlight %} 

{% highlight vbnet %} 

Dim connectionString As String = @"Data Source = http://localhost:8080/cva_s/xmla; Initial Catalog = CVAS;";
Dim olapDataManager As OlapDataManager = New OlapDataManager(connectionString)
olapDataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.ActivePivot;
Me.olapClient1.OlapDataManager = olapDataManager
Me.olapClient1.DataBind()

{% endhighlight %}

{% endtabs %}

