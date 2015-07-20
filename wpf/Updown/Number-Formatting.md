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

Use of NumberFormatInfo

The NumberFormatInfo can be set for the UpDown control as shown in the following code example.

 [XAML]

&lt;syncfusion:UpDown HorizontalAlignment="Center" VerticalAlignment="Center" Name="upDown" Height="51"Width="140" Value="5555555"&gt;

            &lt; syncfusion:UpDown.NumberFormatInfo&gt;

                <globalization:NumberFormatInfo NumberGroupSeparator="/" NumberDecimalDigits="4"



                                       NumberDecimalSeparator="*"/>

            &lt;/ syncfusion:UpDown.NumberFormatInfo&gt;

        &lt;/ syncfusion:UpDown&gt;





[C#]

UpDown upDown = new UpDown();

upDown.Value = 5555555;

upDown.NumberFormatInfo = new NumberFormatInfo()

{

NumberGroupSeparator = "/",

NumberDecimalDigits = 4,

NumberDecimalSeparator = "*"

};



{ ![http://help.syncfusion.com/ug/wpf/ImagesExt/image203_1275.png](Number-Formatting_images/Number-Formatting_img1.png) | markdownify }
{:.image }




Tables for Properties, and Events

_NumberFormatInfo Property_

<table>
<tr>
<td>
Property</td><td>
Description</td><td>
Type</td><td>
Data Type</td><td>
Reference Links</td></tr>
<tr>
<td>
NumberFormatInfo</td><td>
Gets or sets the format of the number.</td><td>
DependencyProperty</td><td>
NumberFormatInfo</td><td>
Not applicable.</td></tr>
</table>


_NumberFormatInfo Event_

<table>
<tr>
<th>
Event</th><th>
Description</th><th>
Arguments</th><th>
Type</th><th>
Reference Links</th></tr>
<tr>
<th>
NumberFormatInfoChanged</th><th>
Occurs when the format of the number changes.</th><th>
DependencyObject andDependencyPropertyChangedEventArgs.</th><th>
PropertyChangedCallback</th><th>
Not applicable.</th></tr>
</table>


