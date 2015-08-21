---
layout: post
title: Maximum-and-Minimum-Value
description: maximum and minimum value
platform: wpf
control: UpDown Control
documentation: ug
---

# Maximum and Minimum Value

The MaxValue is the maximum value that can be set for the UpDown control and MinValue is the minimum value that can be set for the UpDown control.

### Use of MaxValue and MinValue

The MaxValue and MinValue can be set for the UpDown control as shown in the following code example.

{%highlight xml%}

<syncfusion:UpDown Name="upDown" MaxValue="100" MinValue="0"/>

{%endhighlight%}

{%highlight c#%}

UpDown upDown = new UpDown();

upDown.MaxValue = 100;

upDown.MinValue = 0;

{%endhighlight%}

Tables for Properties, and Events

MaxValue and MinValue properties

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
MaxValue</td><td>
Gets or sets the maximum value that can be entered.</td><td>
DependencyProperty</td><td>
double</td><td>
Not applicable.</td></tr>
<tr>
<td>
MinValue</td><td>
Gets or sets the minimum value that can be entered.</td><td>
DependencyProperty</td><td>
double</td><td>
Not applicable.</td></tr>
</table>

MaxValue and MinValue Events

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
MaxValueChanged</td><td>
Occurs when the MaxValue is changed.</td><td>
DependencyObject andDependencyPropertyChangedEventArgs.</td><td>
PropertyChangedCallback</td><td>
Not applicable.</td></tr>
<tr>
<td>
MinValueChanged</td><td>
Occurs when the MinValue is changed.</td><td>
DependencyObject andDependencyPropertyChangedEventArgs. </td><td>
PropertyChangedCallback</td><td>
Not applicable.</td></tr>
</table>


