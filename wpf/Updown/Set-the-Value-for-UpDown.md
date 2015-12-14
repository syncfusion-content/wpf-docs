---
layout: post
title: Set the Value for UpDown | UpDown | WPF | Syncfusion
description: Set the Value for UpDown
platform: wpf
control: UpDown
documentation: ug
---

# Set the Value for UpDown

The value for `UpDown` can be specified by the Value property. 

## Change Value of UpDown

Value of `UpDown` control can be changed by `Value` property. A value can be set for the `UpDown` control as shown in the following code example.

{% tabs %}

{% highlight XAML %}
<syncfusion:UpDown Name="upDown" Value="10" Width="100" Height="23"/>



{% endhighlight %}

{% highlight C# %}

UpDown updown = new UpDown();

updown.Value = 10;

{% endhighlight %}

{% endtabs %}

## Tables for Value Properties and Events

<table>
<tr>
<td>
**Property**<br/><br/></td><td>
**Description**<br/><br/></td><td>
**Type**<br/><br/></td><td>
**Data** **Type**<br/><br/></td></tr>
<tr>
<td>
Value<br/><br/></td><td>
Gets or sets the value of the UpDown control.<br/><br/></td><td>
DependencyProperty<br/><br/></td><td>
double?<br/><br/></td></tr>
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
ValueChanged<br/><br/></td><td>
Occurs when the value in the text box changes.<br/><br/></td><td>
DependencyObject andDependencyPropertyChangedEventArgs.<br/><br/></td><td>
PropertyChangedCallback<br/><br/></td></tr>
<tr>
<td>
ValueChanging<br/><br/></td><td>
Occurs when the value in the text box is about to change.<br/><br/></td><td>
Object andValueChangingEventArgs.<br/><br/></td><td>
ValueChangingEventHandler<br/><br/></td></tr>
</table>
## NullValueText

The `NullValueText` feature enables the `UpDown` control to accept `null` values when the `Value` is null.

A null value can enter in the `UpDown` control only by setting the `Value` as null. To display a TextValue in the `UpDown` control the `NullValueText` property can be used.

The `NullValueText` can be set for the `UpDown` control as shown in the following code example.

{% tabs %}

{% highlight XAML %}
<syncfusion:UpDown Name="upDown" Width="100" Height="23"  NullValueText="2" Value="{x:Null}" />



{% endhighlight %}

{% highlight C# %}

UpDown updown = new UpDown();

updown.Value = null;

updown.NullValueText = "2";

{% endhighlight %}

{% endtabs %}