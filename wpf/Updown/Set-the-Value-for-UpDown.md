---
layout: post
title: Set-the-Value-for-UpDown
description: set the value for updown 
platform: wpf
control: UpDown Control
documentation: ug
---

# Set the Value for UpDown 

The value for UpDown can be specified by using the Value property.

Use of the Value Property

A value can be set for the UpDown control as shown in the following code example.

 [XAML]

<syncfusion:UpDown Name="upDown" Value="10"/>



[C#]

UpDown upDown = new UpDown();

upDown.Value = 10;



Tables for Properties and Events

 _Value property_

<table>
<tr>
<td>
Property</td><td>
Description</td><td>
Type</td><td>
Data Type</td><td>
Reference links</td></tr>
<tr>
<td>
Value</td><td>
Gets or sets the value of the UpDown control.</td><td>
DependencyProperty</td><td>
double?</td><td>
Not applicable.</td></tr>
</table>
_Value Events_

<table>
<tr>
<th>
Events</th><th>
Description</th><th>
Arguments</th><th>
Type</th><th>
Reference Link</th></tr>
<tr>
<th>
ValueChanged</th><th>
Occurs when the value in the text box changes.</th><th>
DependencyObject andDependencyPropertyChangedEventArgs.</th><th>
PropertyChangedCallback</th><th>
Not applicable.</th></tr>
<tr>
<th>
ValueChanging</th><th>
Occurs when the value in the text box is about to change.</th><th>
Object andValueChangingEventArgs.</th><th>
ValueChangingEventHandler</th><th>
Not applicable.</th></tr>
</table>


