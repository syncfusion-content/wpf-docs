---
layout: post
title: Range Adorner Background| PercentTextBox  | Wpf | Syncfusion
description: range adorner background
platform: wpf
control: PercentTextBox 
documentation: ug
---

# Range Adorner Background

The RangeAdornerBackground property is used to set the background color of the range adorner. 

![](Range-Adorner-Background_images/Range-Adorner-Background_img1.png)


### Properties



<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Data Type</th></tr>
<tr>
<td>
RangeAdornerBackground</td><td>
Sets the background color of the adorner.</td><td>
Color name</td></tr>
</table>

## Adding range adorner background to an application 

We have to set the RangeAdornerBackground property either in XAML or the code file.

{% tabs %}
{% highlight xaml %} 
RangeAdornerBackground="LightGreen"
{% endhighlight %}

{% highlight c# %}
control.RangeAdornerBackground = Brushes.LightGreen;
{% endhighlight %}
{% endtabs %}


