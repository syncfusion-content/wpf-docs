---
layout: post
title: Drill-Through
description: drill through
platform: wpf
control: OLAP Common 
documentation: ug
---

# Drill Through

This feature enables the user to drill through any value and see the data which formed the value.

The following code snippet illustrates how to drill through using MDX Query in OlapDataManager:

{% highlight c# %}

string query = @"drillthrough Select { [Customer].[Customer Geography].[Country].&[Australia] } on 0, { [Date].[Fiscal].[Fiscal Year].&[2002] } on 1 from [Adventure Works] Where [Internet Sales Amount]";

// executing the drill-through operation.

olapDataManager.Execute(query);
{% endhighlight  %}


{% highlight vbnet %}

Dim query As String = "drillthrough Select { [Customer].[Customer Geography].[Country].&[Australia] } on 0, { [Date].[Fiscal].[Fiscal Year].&[2002] } on 1 from [Adventure Works] Where [Internet Sales Amount]" 

'Executing the drill-through operation.

olapDataManager.Execute(query)


{% endhighlight  %}
