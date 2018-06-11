---
layout: post
title: Maximum and Minimum Value | UpDown | WPF | Syncfusion
description: Maximum and Minimum Value of UpDown
platform: wpf
control: UpDown
documentation: ug
---

# Maximum and Minimum Values

`UpDown` control allows to define the Maximum and Minimum value. The `MaxValue` is the maximum value that can be set for the `UpDown` control and `MinValue` is the minimum value that can be set for the `UpDown` control. 

## MaxValue and MinValue

The maximum and minimum value can be set using the `MaxValue` and `MinValue` property for the `UpDown` control as shown in the following code example.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" MaxValue="100" MinValue="0" Width="100" Height="23"/>

{% endhighlight %}

{% highlight C# %}

UpDown updown = new UpDown();
updown.Width = 100;
updown.Height = 23;
updown.MaxValue = 100;
updown.MinValue = 0;
Grid1.Children.Add(updown);

{% endhighlight %}

{% endtabs %}

## Tables for MaxValue and MinValue properties and events

<table>
<tr>
<td>
Property</td><td>
Description</td><td>
Type</td><td>
DataType</td></tr>
<tr>
<td>
MaxValue</td><td>
Gets or sets the maximum value that can be entered.</td><td>
DependencyProperty</td><td>
double</td></tr>
<tr>
<td>
MinValue</td><td>
Gets or sets the minimum value that can be entered.</td><td>
DependencyProperty</td><td>
double</td></tr>
</table>
<table>
<tr>
<td>
Events</td><td>
Description</td><td>
Arguments</td><td>
Type</td></tr>
<tr>
<td>
MaxValueChanged</td><td>
Occurs when the MaxValue is changed.</td><td>
DependencyObject andDependencyPropertyChangedEventArgs.</td><td>
PropertyChangedCallback</td></tr>
<tr>
<td>
MinValueChanged</td><td>
Occurs when the MinValue is changed.</td><td>
DependencyObject andDependencyPropertyChangedEventArgs.</td><td>
PropertyChangedCallback</td></tr>
</table>
