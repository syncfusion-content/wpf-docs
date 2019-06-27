---
layout: post
title: Validation | UpDown | WPF | Syncfusion
description: Validation of UpDown Control
platform: wpf
control: UpDown
documentation: ug
---
# Validation

The `UpDown` control supports maximum and minimum value validation. It allows to define when the Minimum and Maximum value validation should occur. 

## Maximum and minimum validation

On setting the `MaxValidation` or `MinValidation` to `OnLostFocus`, then the value in the UpDown control is validated when the UpDown control loses focus. After validation, when the value of the UpDown control is greater than the `MaxValue` or lesser than the `MinValue`, the value of the `Value` property automatically is set to `MaxValue` or `MinValue` respectively.

On setting the `MaxValidation` or `MinValidation` to `OnKeyPress`, then the value in the UpDown control is validated when editing the value in the UpDown control. After validation, when the value of the `Value` property is greater than the `MaxValue` or lesser than the `MinValue`, the UpDown control cannot let to edit the value.

On enabling the `MaxValueOnExceedMaxDigit` property and setting the `MaxValidation` to the `OnKeyPress`, then `MaxValue` is assigned to the `Value` property when the value is greater than the `MaxValue`. However, when the `MaxValueOnExceedMaxDigit` property is disabled, the UpDown control cannot let to enter the text, when the value be greater than the `MaxValue`.

Similarly, on enabling the `MinValueOnExceedMinDigit` property and setting the `MinValidation` to the `OnKeyPress`, the `MinValue` is assigned to the `Value` property when the value is lesser than the `MinValue`. However, when the `MinValueOnExceedMinDigit` property is disabled, the text cannot enter in the `UpDown` control should the value be lesser than `MinValue`.

The `MaxValidation` and `MinValidation` can be set for the UpDown control as shown in the following code.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" MaxValue="100" MinValue="0" MaxValidation="OnLostFocus"
            MinValidation="OnKeyPress" MaxValueOnExceedMaxDigit="True" MinValueOnExceedMinDigit="True"/>

{% endhighlight %}

{% highlight C# %}

UpDown updown = new UpDown();
updown.Value = 10
updown.MaxValue = 100;
updown.MinValue = 0;
updown.MaxValidation = MaxValidation.OnLostFocus;
updown.MinValidation = MinValidation.OnKeyPress;
updown.MinValueOnExceedMinDigit = true;
updown.MaxValueOnExceedMaxDigit = true;
Grid1.Children.Add(updown);

{% endhighlight %}

{% endtabs %}

## Tables for MaxValidation, MinValidation properties and events

<table>
<tr>
<td>
Property</td><td>
Description</td><td>
Type</td><td>
DataType</td></tr>
<tr>
<td>
MaxValidation</td><td>
Gets or sets the MaxValidation.</td><td>
DependencyProperty</td><td>
MaxValidation</td></tr>
<tr>
<td>
MinValidation</td><td>
Gets or sets the MinValidation.</td><td>
DependencyProperty</td><td>
MinValidation</td></tr>
<tr>
<td>
MaxValueOnExceedMaxDigit</td><td>
Gets or sets a value that indicates whether or not to assign MaxValue to the Value property when the value exceeds the MaxValue.</td><td>
DependencyProperty</td><td>
Bool</td></tr>
<tr>
<td>
MinValueOnExceedMinDigit</td><td>
Gets or sets a value that indicates whether or not to assign MinValue to the Value property when the value is lesser than the MinValue.</td><td>
DependencyProperty</td><td>
Bool</td></tr>
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
MinValidationChanged</td><td>
Occurs when the MinValidation is changed.</td><td>
DependencyObject andDependencyPropertyChangedEventArgs.</td><td>
PropertyChangedCallback</td></tr>
<tr>
<td>
MaxValidationChanged</td><td>
Occurs when the MaxValidation is changed.</td><td>
DependencyObject andDependencyPropertyChangedEventArgs.</td><td>
PropertyChangedCallback</td></tr>
</table>
