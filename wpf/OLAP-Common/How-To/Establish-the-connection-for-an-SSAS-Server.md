---
layout: post
title: Establish the connection for an SSAS Server in OLAPCommon| Syncfusion
description: Establish the connection for an ssas server in Syncfusion Essential Studio WPF OLAPCommon control, its elements, features, and more.
platform: wpf
control: OLAPCommon
documentation: ug
---

# Establish the connection for an SSAS Server

A valid string is required to establish connection for an OlapDataManager.

Here is the code snippet that demonstrates how to connect SSAS by using connection string:

{% tabs %}
{% highlight c# %}

OlapDataManager dataManager = new OlapDataManager("DataSource=localhost; Initial Catalog=Adventure Works DW");

{% endhighlight  %}

{% highlight vbnet %}

Dim dataManager As New OlapDataManager("DataSource=localhost; Initial Catalog=Adventure Works DW")
{% endhighlight  %}
{% endtabs %}
{% tabs %}

{% highlight c# %}

Syncfusion.Olap.DataProvider.IDataProvider dataProvider = new Syncfusion.Olap.DataProvider.AdomdDataProvider("DataSource=localhost; Initial Catalog=Adventure Works DW");

OlapDataManager dataManager = new OlapDataManager(dataProvider); 

{% endhighlight  %}

{% highlight vbnet %}

Dim dataProvider As Syncfusion.Olap.DataProvider.IDataProvider = New Syncfusion.Olap.DataProvider.AdomdDataProvider("DataSource=localhost; Initial Catalog=Adventure Works DW")

Dim dataManager As New OlapDataManager(dataProvider)

{% endhighlight  %}
{% endtabs %}
