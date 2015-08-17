---
layout: post
title: Range-Adorner
description: range adorner
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Range Adorner

The EnableRangeAdorner property is used to show the adorner range based on the minimum and maximum values given to that control.

![](Range-Adorner_images/Range-Adorner_img1.png)



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
EnableRangeAdorner </td><td>
The Adorner range will displayed based on the value.</td><td>
bool </td></tr>
</table>

## Adding Range Adorner to an Application 

The EnableRangeAdorner property must be set either in XAML or the code file.

<table>
<tr>
<td>
{% highlight xml %} EnableRangeAdorner="True" {% endhighlight %} </td></tr>
<tr>
<td>
{% highlight C# %} control.EnableRangeAdorner = true;{% endhighlight %} </td></tr>
</table>


