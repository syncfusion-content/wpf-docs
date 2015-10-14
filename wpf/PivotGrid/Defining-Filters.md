---
layout: post
title: Defining Filters| | Wpf | Syncfusion
description: defining filters
platform: wpf
control: PivotGrid
documentation: ug
---

# Defining Filters

Filters can be added to PivotGrid by the following way:

{% tabs %}
{% highlight C# %}  


// Adding filters with filter expressions

this.PivotGridControl1.Filters.Add(new FilterExpression { Expression="Product = Bike" Name="Product Filter" });

 {% endhighlight %}

{% highlight vbnet %} 


' Adding filters with filter expressions

Me.PivotGridControl1.Filters.Add(New FilterExpression With {.Expression="Product = Bike" .Name="Product Filter" })

{% endhighlight %} 
{% endtabs %}
