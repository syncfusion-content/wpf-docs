---
layout: post
title: Culture-and-Number-Formats
description: culture and number formats
platform: wpf
control: IntegerTextBox 
documentation: ug
---

# Culture and Number Formats

## Culture

IntegerTextBox provides globalization support through the Culture property. 

<table>
<tr>
<td>
XAML<syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150"                            Culture="en-US" Value="1234567"/></td></tr>
<tr>
<td>
C#Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();integerTextBox.Width = 150;integerTextBox.Height = 25;integerTextBox.Value = 1234567;integerTextBox.Culture = new System.Globalization.CultureInfo("en-US");</td></tr>
</table>


{{ '![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img1.png)' | markdownify }}
{:.image }


<table>
<tr>
<td>
XAML<syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150"                            Culture="bs-Latn" Value="1234567"/></td></tr>
<tr>
<td>
C#Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();integerTextBox.Width = 150;integerTextBox.Height = 25;integerTextBox.Value = 1234567;integerTextBox.Culture = new System.Globalization.CultureInfo("bs-Latn");</td></tr>
</table>


{{ '![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img2.png)' | markdownify }}
{:.image }


In the first sample culture is set to “en-US” (US Culture) and in the second sample culture is set to “bs-Latn” (Latin Culture). The US culture uses “,” as the NumberGroupSeparator and the Latin culture uses “.” as the NumberGroupSeparator. When you change the Culture property the Value is formatted based on the Culture.

## Number Format

You can customize the Number Format either by using the NumberFormat property or the NumberGroupSeparator and the NumberGroupSizes property.

<table>
<tr>
<td>
XAML<syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150"                            Culture="en-US" Value="123456789012345">     <syncfusion:IntegerTextBox.NumberFormat>        <numberformat:NumberFormatInfo NumberGroupSeparator="/"/>    </syncfusion:IntegerTextBox.NumberFormat></syncfusion:IntegerTextBox></td></tr>
<tr>
<td>
C#Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();integerTextBox.Width = 150;integerTextBox.Height = 25;integerTextBox.Value = 1234567;integerTextBox.Culture = new System.Globalization.CultureInfo("en-US");integerTextBox.NumberFormat = new System.Globalization.NumberFormatInfo() {                                   NumberGroupSeparator = "/" };</td></tr>
</table>


{{ '![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img3.png)' | markdownify }}
{:.image }


<table>
<tr>
<td>
XAML<syncfusion:IntegerTextBox x:Name="integerTextBox" Height="25" Width="150"             Culture="en-US" Value="123456789012345" NumberGroupSeparator="/"/></td></tr>
<tr>
<td>
C#Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();integerTextBox.Width = 150;integerTextBox.Height = 25;integerTextBox.Value = 1234567;integerTextBox.Culture = new System.Globalization.CultureInfo("en-US");integerTextBox.NumberGroupSeparator = "/";</td></tr>
</table>


{{ '![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img4.png)' | markdownify }}
{:.image }


You can also change the NumberGroupSizes by using the NumberGroupSizes property.

Here is a sample for setting the NumberGroupSizes by using the NumberFormat property.

C#



Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();

integerTextBox.Width = 150;

integerTextBox.Height = 25;

integerTextBox.Value = 123456789012345;

integerTextBox.NumberFormat = new System.Globalization.NumberFormatInfo() { 

                              NumberGroupSeparator = "/", 

                              NumberGroupSizes = new int[] { 2, 3, 4 } };



{{ '![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img5.png)' | markdownify }}
{:.image }


Here is a sample for setting the NumberGroupSizes by using the NumberGroupSizes property of the integer textbox:

C#



Syncfusion.Windows.Shared.IntegerTextBox integerTextBox = new Syncfusion.Windows.Shared.IntegerTextBox();

integerTextBox.Width = 150;

integerTextBox.Height = 25;

integerTextBox.Value = 123456789012345;

integerTextBox.NumberGroupSeparator = "/";

integerTextBox.NumberGroupSizes = new Int32Collection() { 2, 3, 0 };



{{ '![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img6.png)' | markdownify }}
{:.image }


