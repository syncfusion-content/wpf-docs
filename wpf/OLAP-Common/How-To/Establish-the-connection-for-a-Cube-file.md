---
layout: post
title: Establish the connection for a Cube file in WPF OLAPCommon| Syncfusion
description: Establish the connection for a cube file in Syncfusion Essential Studio WPF OLAPCommon control, its elements, features and more.
platform: wpf
control: OLAPCommon
documentation: ug
---

# Establish the connection for a Cube file

A valid string is required to establish connection for an OlapDataManager.

Here is the code snippet that demonstrates how to connect cube file by using connection string:

{% tabs %}
{% highlight c# %}

OlapDataManager dataManager = new OlapDataManager("DataSource= AdventureWorks_Ext.cub; Provider=MSOLAP");

{% endhighlight  %}

{% highlight vbnet %}

Dim dataManager As New OlapDataManager("DataSource= AdventureWorks_Ext.cub; Provider=MSOLAP")


{% endhighlight  %}
{% endtabs %}



{% tabs %}
{% highlight c# %}

Syncfusion.Olap.DataProvider.IDataProvider dataProvider = new Syncfusion.Olap.DataProvider.AdomdDataProvider("DataSource= AdventureWorks_Ext.cub; Provider=MSOLAP");

OlapDataManager dataManager = new OlapDataManager(dataProvider); 

{% endhighlight  %}


{% highlight vbnet %}

Dim dataProvider As Syncfusion.Olap.DataProvider.IDataProvider = New Syncfusion.Olap.DataProvider.AdomdDataProvider("DataSource= AdventureWorks_Ext.cub; Provider=MSOLAP")

Dim dataManager As New OlapDataManager(dataProvider)

{% endhighlight  %}

{% endtabs %}
