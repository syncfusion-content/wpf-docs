---
layout: post
title: Range Adorner | CurrencyTextBox | wpf | Syncfusion
description: range adorner
platform: wpf
control: CurrencyTextBox 
documentation: ug
---

# Range Adorner

The EnableRangeAdorner property is used to show the adorner range based on the minimum and maximum values given to that control.

![](Range-Adorner_images/Range-Adorner_img1.png)

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

## Adding range adorner to an application 

The EnableRangeAdorner property must be set either in XAML or the code file.

{% tabs %}
{% highlight xaml %}

EnableRangeAdorner="True"

{% endhighlight %}

{% highlight C# %}

control.EnableRangeAdorner = true;

{% endhighlight %}
{% endtabs %}
