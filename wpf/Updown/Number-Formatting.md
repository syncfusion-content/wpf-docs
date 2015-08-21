---
layout: post
title: Number-Formatting
description: number formatting
platform: wpf
control: UpDown Control
documentation: ug
---

# Number Formatting

The Number formatting controls how a number is displayed in the UpDown control by specifying the culture-specific group separator, decimal separator, and the number of decimal digits to be used. You can format the value of the UpDown control by using the NumberFormatInfo property.

### Use of NumberFormatInfo

The NumberFormatInfo can be set for the UpDown control as shown in the following code example.

{%highlight xml%}

<syncfusion:UpDown HorizontalAlignment="Center" VerticalAlignment="Center" Name="upDown" Height="51"Width="140" Value="5555555">

            < syncfusion:UpDown.NumberFormatInfo>

                <globalization:NumberFormatInfo NumberGroupSeparator="/" NumberDecimalDigits="4"



                                       NumberDecimalSeparator="*"/>

            </ syncfusion:UpDown.NumberFormatInfo>

        </ syncfusion:UpDown>



{%endhighlight%}

{%highlight c#%}


UpDown upDown = new UpDown();

upDown.Value = 5555555;

upDown.NumberFormatInfo = new NumberFormatInfo()

{

NumberGroupSeparator = "/",

NumberDecimalDigits = 4,

NumberDecimalSeparator = "*"

};

{%endhighlight%}

![](Number-Formatting_images/Number-Formatting_img1.png)





Tables for Properties, and Events

NumberFormatInfo Property

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
NumberFormatInfo</td><td>
Gets or sets the format of the number.</td><td>
DependencyProperty</td><td>
NumberFormatInfo</td><td>
Not applicable.</td></tr>
</table>


NumberFormatInfo Event

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
NumberFormatInfoChanged</td><td>
Occurs when the format of the number changes.</td><td>
DependencyObject andDependencyPropertyChangedEventArgs.</td><td>
PropertyChangedCallback</td><td>
Not applicable.</td></tr>
</table>


