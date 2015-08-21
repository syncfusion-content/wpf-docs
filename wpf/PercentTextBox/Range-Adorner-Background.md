---
layout: post
title: Range-Adorner-Background
description: range adorner background
platform: wpf
control: PercentTextBox 
documentation: ug
---

# Range Adorner Background

The RangeAdornerBackground property is used to set the background color of the range adorner. 

![](Range-Adorner-Background_images/Range-Adorner-Background_img1.png)


## Properties

Property table

<table>
<tr>
<th>
{{ '**Property**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Data Type**' | markdownify }}</th></tr>
<tr>
<td>
RangeAdornerBackground</td><td>
Sets the background color of the adorner.</td><td>
Color name</td></tr>
</table>
# Adding Range Adorner Background to an Application 

We have to set the RangeAdornerBackground property either in XAML or the code file.

<table>
<tr>
<td>
{% highlight xml %} RangeAdornerBackground="LightGreen"{% endhighlight %}</td></tr>
<tr>
<td>
{% highlight c# %}control.RangeAdornerBackground = Brushes.LightGreen;{% endhighlight %}</td></tr>
</table>


