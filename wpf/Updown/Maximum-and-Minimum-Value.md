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
[XAML]

<syncfusion:UpDown Name="upDown" MaxValue="100" MinValue="0"/>

{%endhighlight%}

{%highlight c#%}
[C#]

UpDown upDown = new UpDown();

upDown.MaxValue = 100;

upDown.MinValue = 0;

{%endhighlight%}

Tables for Properties, and Events

_MaxValue and MinValue properties_

<table>
<tr>
<td>
{{ '**Property**' | markdownify }}</td><td>
{{ '**Description**' | markdownify }}</td><td>
{{ '**Type**' | markdownify }}</td><td>
{{ '**Data Type**' | markdownify }}</td><td>
{{ '**Reference links**' | markdownify }}</td></tr>
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
_MaxValue and MinValue Events_

<table>
<tr>
<th>
{{ '**Events**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Arguments**' | markdownify }}</th><th>
{{ '**Type**' | markdownify }}</th><th>
{{ '**Reference links**' | markdownify }}</th></tr>
<tr>
<th>
MaxValueChanged</th><th>
Occurs when the MaxValue is changed.</th><th>
DependencyObject andDependencyPropertyChangedEventArgs.</th><th>
PropertyChangedCallback</th><th>
Not applicable.</th></tr>
<tr>
<th>
MinValueChanged</th><th>
Occurs when the MinValue is changed.</th><th>
DependencyObject andDependencyPropertyChangedEventArgs. </th><th>
PropertyChangedCallback</th><th>
Not applicable.</th></tr>
</table>


