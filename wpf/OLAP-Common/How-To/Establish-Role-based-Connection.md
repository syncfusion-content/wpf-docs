---
layout: post
title: Establish Role based Connection| OLAPCommon | Wpf | Syncfusion
description: Establish role-based connection in Syncfusion Essential Studio WPF OLAPCommon control, its elements, features, and more.
platform: wpf
control: OLAPCommon
documentation: ug
---

# Establish Role-based Connection



You can apply Role-based filtering to OLAP components by specifying the appropriate role name designed for specific set of users in the SSAS Cube. You must specify the role name in the “Roles” attribute of the connection string. The following code example illustrates this.


{% tabs %}
{% highlight c# %}



OlapDataManager olapDataManager = new OlapDataManager(@"Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Roles=Role1; Initial Catalog=Adventure Works DW 2008 SE;");

{% endhighlight %}



{% highlight vbnet %}



Dim olapDataManager As OlapDataManager = New OlapDataManager("Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Roles=Role1; Initial Catalog=Adventure Works DW 2008 SE;")


{% endhighlight  %}
{% endtabs %}