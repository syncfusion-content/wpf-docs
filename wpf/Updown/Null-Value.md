---
layout: post
title: Null-Value
description: null value
platform: wpf
control: UpDown Control
documentation: ug
---

# Null Value

The Null Value feature enables the UpDown control to accept null values.

Use of NullValue and UseNullOption

You can enter a null value in the UpDown control only when the UseNullOption is set to true. You can also specify a value to be displayed in the UpDown control when the value of the UpDown control is set to null by using the NullValue property.

The NullValue can be set for the UpDown control as shown in the following code example.

 [XAML]

<syncfusion:UpDown Name="upDown" UseNullOption="true" NullValue="1"/>



[C#]

UpDown upDown = new UpDown();

upDown.UseNullOption = true;

upDown.NullValue = 2;



Tables for Properties and Events

_NullValue properties_

<table>
<tr>
<td>
Properties</td><td>
Description</td><td>
Type</td><td>
Data Type</td><td>
Reference links</td></tr>
<tr>
<td>
UseNullOption</td><td>
Gets or sets the value that indicates whether to use the null value or not.</td><td>
DependencyProperty</td><td>
bool</td><td>
Not applicable</td></tr>
<tr>
<td>
NullValue</td><td>
Gets or sets a value to be displayed in the UpDown control when the value is null.</td><td>
DependencyProperty</td><td>
double?</td><td>
Not applicable</td></tr>
</table>
 _NullValue Event Table_	

<table>
<tr>
<th>
Event</th><th>
Description</th><th>
Arguments</th><th>
Type</th><th>
Reference links</th></tr>
<tr>
<th>
UseNullOptionChanged</th><th>
Occurs when the UseNullOption value is changed.</th><th>
DependencyObject andDependencyPropertyChangedEventArgs.</th><th>
PropertyChangedCallback</th><th>
Not applicable.</th></tr>
</table>


