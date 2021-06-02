---
layout: post
title: Mondrian Server through XMLA in WPF OLAPCommon control | Syncfusion
description: Connecting to mondrian server through xmla in Syncfusion WPF OLAPCommon control, its elements, and more.
platform: wpf
control: OLAPCommon
documentation: ug
---

# Connecting to Mondrian Server through XMLA



The following code illustrates how to connect to the Mondrian server:


{% tabs %}
{% highlight c# %}



// Connecting to Mondrian Server

OlapDataManager DataManager = new OlapDataManager(@"Data Source = http://localhost:8080/mondrian/xmla; Initial Catalog = FoodMart;"); 'Where localhost is the machine name which has installed Mondrian Services. For example [http://bi.syncfusion.com:8080/mondrian/xmla](http://bi.syncfusion.com:8080/mondrian/xmla)



DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.Mondrian;


{% endhighlight  %}

{% highlight vbnet %}



' Connecting to Mondrian Server

Dim DataManager As OlapDataManager = New OlapDataManager(@"Datasource = [http://bi.syncfusion.com:8080/mondrian/xmla](http://bi.syncfusion.com:8080/mondrian/xmla); Initial Catalog=FoodMart;") ’Where localhost is the machine name which has installed Mondrian Services. For example [http://bi.syncfusion.com:8080/mondrian/xmla](http://bi.syncfusion.com:8080/mondrian/xmla)



DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.Mondrian


{% endhighlight  %}
{% endtabs %}

[Refer here](http://mondrian.pentaho.com/) for more information about Mondrian XMLA configurations.



