---
layout: post
title: Maximum-and-Minimum-Validation
description: maximum and minimum validation
platform: wpf
control: UpDown Control
documentation: ug
---

# Maximum and Minimum Validation

The UpDown control supports maximum and minimum validation. On setting the MaxValidation or MinValidation to OnLostFocus, then the value in the UpDown control is validated when the UpDown control loses focus. After validation, when the value of the UpDown control is greater than the MaxValue or lesser than the MinValue, the value of the Value property automatically is set to MaxValue or MinValue respectively.

On setting the MaxValidation or MinValidation to OnKeyPress, then the value in the UpDown control is validated when editing the value in the UpDown control. After validation, when the value of the Value property is greater than the MaxValue or lesser than the MinValue, you cannot edit the UpDown control.

On enabling the MaxValueOnExceedMaxDigit property and setting the MaxValidation to the OnKeyPress, then MaxValue is assigned to the Value property when the value is greater than the MaxValue. However, when the MaxValueOnExceedMaxDigit property is disabled, you cannot enter text in the UpDown control should the value be greater than the MaxValue.

Similarly, on enabling the MinValueOnExceedMinDigit property and setting the MinValidation to the OnKeyPress, the MinValue is assigned to the Value property when the value is lesser than the MinValue. However, when the MinValueOnExceedMinDigit property is disabled, you cannot enter text in the UpDown control should the value be lesser than MinValue.

### Use of MaxValidation and MinValidation

The MaxValidation and MinValidation can be set for the UpDown control as shown in the following code.

{%highlight xml%}


<syncfusion:UpDown Name="upDown" MaxValue="100" MinValue="0" MaxValidation="OnLostFocus"MinValidation="OnKeyPress" MaxValueOnExceedMaxDigit="True" MinValueOnExceedMinDigit="True"/>

{%endhighlight%}

{%highlight c#%}


UpDown upDown = new UpDown();

upDown.MaxValue = 100;

upDown.MinValue = 0;

upDown.MaxValidation = MaxValidation.OnLostFocus;

upDown.MinValidation = MinValidation.OnKeyPress;

upDown.MaxValueOnExceedMaxDigit = true;

upDown.MinValueOnExceedMinDigit = true;

{%endhighlight%}

Tables for Properties, and Events

MaxValidation and MinValidation Properties

<table>
<tr>
<th>
{{ '**Property**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Type**' | markdownify }}</th><th>
{{ '**Data Type**' | markdownify }}</th><th>
{{ '**Reference links**' | markdownify }}</th></tr>
<tr>
<td>
MaxValidation</td><td>
Gets or sets the MaxValidation.</td><td>
DependencyProperty</td><td>
MaxValidation</td><td>
Not applicable</td></tr>
<tr>
<td>
MinValidation</td><td>
Gets or sets the MinValidation.</td><td>
DependencyProperty</td><td>
MinValidation</td><td>
Not applicable</td></tr>
<tr>
<td>
MaxValueOnExceedMaxDigit</td><td>
Gets or sets a value that indicates whether or not to assign MaxValue to the Value property when the value exceeds the MaxValue.</td><td>
DependencyProperty</td><td>
bool</td><td>
Not applicable</td></tr>
<tr>
<td>
MinValueOnExceedMinDigit</td><td>
Gets or sets a value that indicates whether or not to assign MinValue to the Value property when the value is lesser than the MinValue.</td><td>
DependencyProperty</td><td>
bool</td><td>
Not applicable</td></tr>
</table>


MaxValidation and MinValidation event

<table>
<tr>
<th>
{{ '**Events**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Arguments**' | markdownify }}</th><th>
{{ '**Type**' | markdownify }}</th><th>
{{ '**Reference links**' | markdownify }}</th></tr>
<tr>
<td>
MinValidationChanged</td><td>
Occurs when the MinValidation is changed.</td><td>
DependencyObject andDependencyPropertyChangedEventArgs.</td><td>
PropertyChangedCallback</td><td>
Not applicable.</td></tr>
<tr>
<td>
MaxValidationChanged</td><td>
Occurs when the MaxValidation is changed.</td><td>
DependencyObject andDependencyPropertyChangedEventArgs.</td><td>
PropertyChangedCallback</td><th>
Not applicable.</td></tr>
</table>


