---
layout: post
title: Culture-and-Number-Formats
description: culture and number formats
platform: wpf
control: CurrencyTextBox 
documentation: ug
---

# Culture and Number Formats

## Culture

CurrencyTextBox provides globalization support through the Culture property. 



<table>
<tr>
<td>
XAML<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150"                          Culture="en-US" Value="1234567"/></td></tr>
<tr>
<td>
C#Syncfusion.Windows.Shared.CurrencyTextBox currencyTextBox = new                           Syncfusion.Windows.Shared.CurrencyTextBox();currencyTextBox.Width = 100;currencyTextBox.Height = 25;currencyTextBox.Value = 1234567;currencyTextBox.Culture = new CultureInfo("en-US");</td></tr>
</table>


{{ '![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img1.png)' | markdownify }}
{:.image }




<table>
<tr>
<td>
XAML<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150"                             Culture="fr-FR" Value="1234567"/></td></tr>
<tr>
<td>
C#Syncfusion.Windows.Shared.CurrencyTextBox currencyTextBox = new                           Syncfusion.Windows.Shared.CurrencyTextBox();currencyTextBox.Width = 100;currencyTextBox.Height = 25;currencyTextBox.Value = 1234567;currencyTextBox.Culture = new CultureInfo("fr-FR");</td></tr>
</table>


{{ '![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img2.png)' | markdownify }}
{:.image }


As you have seen in these samples whenever you change the Culture property the Value is formatted based on the Culture.

## NumberFormat

You can customize the Number Format either by using the NumberFormat property or the CurrencyGroupSeparator, CurrencyGroupSizes, CurrencyDecimalDigits, and CurrencyDecimalSeparator, CurrencySymbol, CurrencyNegativePattern, and CurrencyPositivePattern properties.



<table>
<tr>
<td>
XAML<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150"                             Value="1234567">    <syncfusion:CurrencyTextBox.NumberFormat>        <numberformat:NumberFormatInfo CurrencyGroupSeparator="/"                       CurrencyDecimalDigits="4" CurrencyDecimalSeparator="*"                       CurrencySymbol="$"/>    </syncfusion:CurrencyTextBox.NumberFormat></syncfusion:CurrencyTextBox></td></tr>
<tr>
<td>
C#Syncfusion.Windows.Shared.CurrencyTextBox currencyTextBox = new                           Syncfusion.Windows.Shared.CurrencyTextBox();currencyTextBox.Width = 100;currencyTextBox.Height = 25;currencyTextBox.Value = 1234567;currencyTextBox.NumberFormat = new NumberFormatInfo() { CurrencyGroupSeparator = "/",                                CurrencyDecimalDigits = 4, CurrencyDecimalSeparator = "*",                                CurrencySymbol = "$" };</td></tr>
</table>


{{ '![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img3.png)' | markdownify }}
{:.image }




<table>
<tr>
<td>
XAML<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150"                             Value="1234567"                            CurrencyGroupSeparator="/" CurrencyDecimalDigits="4"                             CurrencyDecimalSeparator="*" CurrencySymbol="$"></syncfusion:CurrencyTextBox></td></tr>
<tr>
<td>
C#Syncfusion.Windows.Shared.CurrencyTextBox currencyTextBox = new                           Syncfusion.Windows.Shared.CurrencyTextBox();currencyTextBox.Width = 100;currencyTextBox.Height = 25;currencyTextBox.Value = 1234567;currencyTextBox.CurrencyGroupSeparator = "/";currencyTextBox.CurrencyDecimalDigits = 4;currencyTextBox.CurrencyDecimalSeparator = "*";currencyTextBox.CurrencySymbol = "$";</td></tr>
</table>


{{ '![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img4.png)' | markdownify }}
{:.image }


### CurrencyPositivePattern

Gets or sets the format pattern for the positive currency values. In the table displayed below “$” denotes the Currency symbol and n denotes the number.

_CurrencyPositivePattern table_

<table>
<tr>
<td>
Value</td><td>
Associated Pattern</td></tr>
<tr>
<td>
0</td><td>
$n</td></tr>
<tr>
<td>
1</td><td>
n$</td></tr>
<tr>
<td>
2</td><td>
$ n</td></tr>
<tr>
<td>
3</td><td>
n $</td></tr>
</table>


XAML



<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150" Value="1234" 

                            CurrencyPositivePattern="3"/>



{{ '![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img5.png)' | markdownify }}
{:.image }


### CurrencyNegativePattern

Gets or sets the format pattern for the negative currency values. In the table displayed below “$” denotes the Currency symbol and n denotes the number.

_CurrencyNegativePattern table_

<table>
<tr>
<td>
Value</td><td>
Associated Pattern</td></tr>
<tr>
<td>
0</td><td>
($n)</td></tr>
<tr>
<td>
1</td><td>
-$n</td></tr>
<tr>
<td>
2</td><td>
$-n</td></tr>
<tr>
<td>
3</td><td>
$n-</td></tr>
<tr>
<td>
4</td><td>
(n$)</td></tr>
<tr>
<td>
5</td><td>
-n$</td></tr>
<tr>
<td>
6</td><td>
n-$</td></tr>
<tr>
<td>
7</td><td>
n$-</td></tr>
<tr>
<td>
8</td><td>
-n $</td></tr>
<tr>
<td>
9</td><td>
-$ n</td></tr>
<tr>
<td>
10</td><td>
n $-</td></tr>
<tr>
<td>
11</td><td>
$ n-</td></tr>
<tr>
<td>
12</td><td>
$ -n</td></tr>
<tr>
<td>
13</td><td>
n- $</td></tr>
<tr>
<td>
14</td><td>
($ n)</td></tr>
<tr>
<td>
15</td><td>
(n $)</td></tr>
</table>


XAML



<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150" 

                            Value="-1234" CurrencyNegativePattern="0"/>



{{ '![](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img6.png)' | markdownify }}
{:.image }


