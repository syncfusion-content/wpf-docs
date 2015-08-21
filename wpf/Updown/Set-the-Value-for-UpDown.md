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

### Use of the Value Property

A value can be set for the UpDown control as shown in the following code example.

{%highlight xml%}

<syncfusion:UpDown Name="upDown" Value="10"/>

{%endhighlight%}


{%highlight c#%}

UpDown upDown = new UpDown();

upDown.Value = 10;

{%endhighlight%}

Tables for Properties and Events

 _Value property_

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
{{ '**Events**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th><th>
{{ '**Arguments**' | markdownify }}</th><th>
{{ '**Type**' | markdownify }}</th><th>
{{ '**Reference links**' | markdownify }}</th></tr>
<tr>
<td>
ValueChanged</td><td>
Occurs when the value in the text box changes.</td><td>
DependencyObject andDependencyPropertyChangedEventArgs.</td><td>
PropertyChangedCallback</td><td>
Not applicable.</td></tr>
<tr>
<td>
ValueChanging</td><td>
Occurs when the value in the text box is about to change.</td><td>
Object andValueChangingEventArgs.</td><td>
ValueChangingEventHandler</td><td>
Not applicable.</td></tr>
</table>


