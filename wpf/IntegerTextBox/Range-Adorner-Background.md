---
layout: post
title: Range-Adorner-Background
description: range adorner background
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Range Adorner Background

The RangeAdornerBackground property is used to set the background color of the range adorner. 

![](Range-Adorner-Background_images/Range-Adorner-Background_img1.png)



Properties

Property table

<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Data Type </th></tr>
<tr>
<td>
RangeAdornerBackground</td><td>
Sets the background color of the adorner.</td><td>
Color name</td></tr>
</table>
## Adding Range Adorner Background to an Application 

The RangeAdornerBackground property must be set either in XAML or the code file.

<table>
<tr>
<td>
{% highlight xml %}  RangeAdornerBackground="LightGreen" {% endhighlight %} </td></tr>
<tr>
<td>
{% highlight C# %} control.RangeAdornerBackground = Brushes.LightGreen; {% endhighlight %} </td></tr>
</table>


