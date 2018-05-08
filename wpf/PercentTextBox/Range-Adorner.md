---
layout: post
title: Range Adorner| PercentTextBox  | Wpf | Syncfusion
description: range adorner
platform: wpf
control: PercentTextBox 
documentation: ug
---

# Range Adorner

The EnableRangeAdorner property is used to show the adorner range based on the minimum and maximum values given to that control.

![](Range-Adorner_images/Range-Adorner_img1.png)


### Properties



<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Data Type</th></tr>
<tr>
<td>
EnableRangeAdorner </td><td>
The Adorner range will displayed based on the value.</td><td>
bool </td></tr>
</table>

## Adding range adorner to an application 

We have to set the EnableRangeAdorner property, either in XAML or the code file.

{% tabs %}
{% highlight xaml %} 
EnableRangeAdorner="True"
{% endhighlight %}


{% highlight c# %}
control.EnableRangeAdorner = true;
{% endhighlight %}
{% endtabs %}


