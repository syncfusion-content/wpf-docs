---
layout: post
title: Data Binding in WPF Olap Client control | Syncfusion
description: Learn about Data Binding support in Syncfusion Essential Studio WPF Olap Client control, its elements and more details.
platform: wpf
control: OLAP Client
 documentation: ug
---

# Data Binding in WPF Olap Client

## Binding OLAP client to offline cube

To connect to an OLAP cube available in the local machine, set the physical path of the cube set in the connection string. The following code example illustrates the same.

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

## Binding OLAP client to cube in local SQL Server

To connect to the OLAP cube available in SQL Server Analysis Service in the local machine, set the server name and database name in the connection string. If you have any credentials to connect your cube, then set the user ID and password attributes accordingly. The following code example illustrates the same.

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

## Binding OLAP client to cube in online SQL Server

To connect to the OLAP cube available in SQL Server Analysis Service in the online server through XML/A, set the host server link and database name in the connection string. If you have any credentials to connect your cube, then set the user ID and password attributes accordingly. The following code example illustrates the same.

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

## Binding OLAP client to cube in online Mondrian Server

To connect to the OLAP cube available in Mondrian Server through XML/A, set the host server link and database name in the connection string. If you have any credentials to connect your cube, then set the user ID and password attributes accordingly. The following code example illustrates the same.

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

## Binding OLAP client to cube in online ActivePivot Server

To connect to the OLAP cube available in ActivePivot Server through XML/A, set the host server link and database name in the connection string. If you have any credentials to connect your cube, then set the user ID and password attributes accordingly. The following code example illustrates the same.

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

