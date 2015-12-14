---
layout: post
title: Maximum and Minimum Value | UpDown | WPF | Syncfusion
description: Maximum and Minimum Value of UpDown
platform: wpf
control: UpDown
documentation: ug
---

# Maximum and Minimum Value

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

## Tables for MaxValue and MinValue Properties and Events

<table>
<tr>
<td>
**Property**<br/><br/></td><td>
**Description**<br/><br/></td><td>
**Type**<br/><br/></td><td>
**Data** **Type**<br/><br/></td></tr>
<tr>
<td>
MaxValue<br/><br/></td><td>
Gets or sets the maximum value that can be entered.<br/><br/></td><td>
DependencyProperty<br/><br/></td><td>
double<br/><br/></td></tr>
<tr>
<td>
MinValue<br/><br/></td><td>
Gets or sets the minimum value that can be entered.<br/><br/></td><td>
DependencyProperty<br/><br/></td><td>
double<br/><br/></td></tr>
</table>
<table>
<tr>
<td>
**Events**<br/><br/></td><td>
**Description**<br/><br/></td><td>
**Arguments**<br/><br/></td><td>
**Type**<br/><br/></td></tr>
<tr>
<td>
MaxValueChanged<br/><br/></td><td>
Occurs when the MaxValue is changed.<br/><br/></td><td>
DependencyObject andDependencyPropertyChangedEventArgs.<br/><br/></td><td>
PropertyChangedCallback<br/><br/></td></tr>
<tr>
<td>
MinValueChanged<br/><br/></td><td>
Occurs when the MinValue is changed.<br/><br/></td><td>
DependencyObject andDependencyPropertyChangedEventArgs.<br/><br/></td><td>
PropertyChangedCallback<br/><br/></td></tr>
</table>
