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

### Use of NullValue and UseNullOption

You can enter a null value in the UpDown control only when the UseNullOption is set to true. You can also specify a value to be displayed in the UpDown control when the value of the UpDown control is set to null by using the NullValue property.

The NullValue can be set for the UpDown control as shown in the following code example.


{%highlight xml%}

<syncfusion:UpDown Name="upDown" UseNullOption="true" NullValue="1"/>

{%endhighlight%}



{%highlight c#%}

UpDown upDown = new UpDown();

upDown.UseNullOption = true;

upDown.NullValue = 2;

{%endhighlight%}

Tables for Properties and Events

> NullValue properties

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

> NullValue Event Table	

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
UseNullOptionChanged</td><td>
Occurs when the UseNullOption value is changed.</td><td>
DependencyObject andDependencyPropertyChangedEventArgs.</td><td>
PropertyChangedCallback</td><td>
Not applicable.</td></tr>
</table>


