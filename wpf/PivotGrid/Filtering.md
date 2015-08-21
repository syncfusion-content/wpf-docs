---
layout: post
title: Filtering 
description: filtering 
platform: wpf
control: PivotGrid
documentation: ug
---


# Filtering 

Filtered data displays only a subset of data that meets criteria that you specify and hides data that you do not want displayed. Filters are automatically reapplied every time the PivotGrid is refreshed or updated. In the PivotGrid, filters are additive, which means that each additional filter is based on the current filter and further reduces the subset of data. We can apply n number of filtering conditions to the grid at a time. Data is filtered based on the filter expression specified.

{% highlight C# %}  



// Adding filters with filter expressions

this.PivotGridControl1.Filters.Add(new FilterExpression { Expression="Product = Bike" Name="Product Filter" });

{% endhighlight %} 



{% highlight vbnet %} 


' Adding filters with filter expressions

Me.PivotGridControl1.Filters.Add(New FilterExpression With {.Expression="Product = Bike" .Name="Product Filter" })

{% endhighlight %} 

