---
layout: post
title: Culture and Formatting in WPF CurrencyTextBox | Syncfusion®
description: Format the currency value in the Syncfusion WPF CurrencyTextBox control using culture settings, number formats, and grouping separators.
platform: wpf
control: CurrencyTextBox
documentation: ug
---

# Culture and Formatting in WPF CurrencyTextBox

## Assembly Deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#currencytextbox) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

Value of `CurrencyTextBox` can be formatted in the following ways:

* Culture
* NumberFormatInfo
* Dedicated properties (CurrencyGroupSeparator, CurrencyGroupSizes, CurrencyDecimalDigits, CurrencyDecimalSeparator)

## Culture based formatting

The [CurrencyTextBox](https://www.syncfusion.com/wpf-controls/currency-textbox) provides support for globalization by using the [Culture](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_Culture) property. The `Culture` property is used to format the decimal separator and group separator of the `CurrencyTextBox` value based on the respective culture.

{% tabs %}
{% highlight xaml %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150" Culture="fr-FR" Value="1234567"/>

{% endhighlight %}

{% highlight C# %}

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 100;
currencyTextBox.Height = 25;
currencyTextBox.Value = 1234567;
currencyTextBox.Culture = new CultureInfo("fr-FR");

{% endhighlight %}
{% endtabs %}

By default the US culture uses “,” as the `CurrencyGroupSeparator` "$" as `CurrencySymbol` and "." as the `CurrencyDecimalSeparator` where as the France culture uses “Space” as the `CurrencyGroupSeparator`, "€" as `CurrencySymbol` and "," as the `CurrencyDecimalSeparator`. 

**Default Culture**

![WPF CurrencyTextBox with Default Culture](Culture-and-Number-Formats_images/wpf-currency-textbox-culture.png)

**France Culture**

![WPF CurrencyTextBox with France Culture](Culture-and-Number-Formats_images/wpf-currency-textbox-france-culture.png)

## NumberFormatInfo-Based Formatting

The number formatting of `CurrencyTextBox` can be customized by setting the [NumberFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.EditorBase.html#Syncfusion_Windows_Shared_EditorBase_NumberFormat) property.

{% tabs %}
{% highlight xaml %}

<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:numberformat="clr-namespace:System.Globalization;assembly=mscorlib"
        x:Class="CurrencyTextBoxSample.MainWindow"
        Title="CurrencyTextBox Sample" Height="350" Width="525">
    <Grid>
        <syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150" Value="1234567">
            <syncfusion:CurrencyTextBox.NumberFormat>
                <numberformat:NumberFormatInfo CurrencyGroupSeparator="/"
                                               CurrencyDecimalDigits="4"
                                               CurrencyDecimalSeparator="*"
                                               CurrencySymbol="$"/>
            </syncfusion:CurrencyTextBox.NumberFormat>
        </syncfusion:CurrencyTextBox>
    </Grid>
</Window>

{% endhighlight %}

{% highlight C# %}

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 150;
currencyTextBox.Height = 25;
currencyTextBox.Value = 1234567;
currencyTextBox.NumberFormat = new NumberFormatInfo()
{
    CurrencyGroupSeparator = "/", 
    CurrencyDecimalDigits = 4,     
    CurrencyDecimalSeparator = "*", 
    CurrencySymbol = "$"
};

{% endhighlight %}
{% endtabs %}

![WPF CurrencyTextBox with Formatting](Culture-and-Number-Formats_images/wpf-currency-textbox-formatting.png)

The following code illustrates how to set the currency group size by using the `NumberFormat` property.

{% tabs %}
{% highlight C# %}

using System.Globalization;

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 150;
currencyTextBox.Height = 25;
currencyTextBox.Value = 123456789;
currencyTextBox.NumberFormat = new NumberFormatInfo()
{
    CurrencySymbol = "&",
    CurrencyDecimalDigits = 4,
    CurrencyGroupSeparator = "/",
    CurrencyDecimalSeparator = "*",

    // Adding the currency group size via NumberFormat property.
    CurrencyGroupSizes = new int[] { 2, 3, 4 }
};

{% endhighlight %}
{% endtabs %}

![WPF CurrencyTextBox displays Different Group Size between Numbers](Culture-and-Number-Formats_images/wpf-currency-textbox-group-size.png)

## Formatting with dedicated properties

The number formatting of `CurrencyTextBox` can also be customized by setting the [CurrencyGroupSeparator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CurrencyTextBox.html#Syncfusion_Windows_Shared_CurrencyTextBox_CurrencyGroupSeparator), [CurrencyGroupSizes](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CurrencyTextBox.html#Syncfusion_Windows_Shared_CurrencyTextBox_CurrencyGroupSizes), [CurrencyDecimalDigits](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CurrencyTextBox.html#Syncfusion_Windows_Shared_CurrencyTextBox_CurrencyDecimalDigits) and [CurrencyDecimalSeparator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CurrencyTextBox.html#Syncfusion_Windows_Shared_CurrencyTextBox_CurrencyDecimalSeparator), [CurrencySymbol](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CurrencyTextBox.html#Syncfusion_Windows_Shared_CurrencyTextBox_CurrencySymbol), [CurrencyNegativePattern](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CurrencyTextBox.html#Syncfusion_Windows_Shared_CurrencyTextBox_CurrencyNegativePattern), and [CurrencyPositivePattern](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CurrencyTextBox.html#Syncfusion_Windows_Shared_CurrencyTextBox_CurrencyPositivePattern) properties of CurrencyTextBox. You can show the group separator by enabling the [GroupSeparatorEnabled](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CurrencyTextBox.html#Syncfusion_Windows_Shared_CurrencyTextBox_GroupSeparatorEnabled) property (`true`).

The following code illustrates how to format using the `CurrencyDecimalSeparator`, `CurrencyDecimalDigits`, `CurrencyGroupSeparator`, and `CurrencyGroupSizes` properties of the `CurrencyTextBox`.

{% tabs %}
{% highlight C# %}

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 150;
currencyTextBox.Height = 25;
currencyTextBox.Value = 123456789;
currencyTextBox.CurrencySymbol = "#";
currencyTextBox.CurrencyDecimalDigits = 4;
currencyTextBox.GroupSeparatorEnabled = true;
currencyTextBox.CurrencyGroupSeparator = "/";
currencyTextBox.CurrencyDecimalSeparator = "*";

// Adding the currency group size via CurrencyGroupSizes property.
currencyTextBox.CurrencyGroupSizes = new int[] { 4, 3, 2 };

{% endhighlight %}
{% endtabs %}

![WPF CurrencyTextBox with Formatting](Culture-and-Number-Formats_images/wpf-currency-textbox-number-format.png)

N> When you use both the `NumberFormat` and the dedicated properties (`CurrencyGroupSeparator`, `CurrencySymbol`, `CurrencyDecimalDigits`, `CurrencyDecimalSeparator` and `CurrencyGroupSizes`) to format the value of `CurrencyTextBox`, the `CurrencyGroupSeparator` and `CurrencyGroupSizes` properties have higher priority.

N> When you use both `NumberFormat` and  `Culture`, the `NumberFormat` will have a higher priority.

### Positive Value Pattern

You can use the [CurrencyPositivePattern](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CurrencyTextBox.html#Syncfusion_Windows_Shared_CurrencyTextBox_CurrencyPositivePattern) property to customize the location of the currency symbol and the positive currency values. In the table below,"$" denotes the symbol of the currency, and "n" denotes the number.

**CurrencyPositivePattern table**

<table>
<tr>
<th>
Value</th><th>
Associated Pattern</th></tr>
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

![WPF CurrencyTextBox displays Positive Value Patterns](Culture-and-Number-Formats_images/wpf-currency-textbox-positive-patterns.png)

{% tabs %}
{% highlight xaml %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150" Value="1234" CurrencyPositivePattern="3"/>

{% endhighlight %}
{% highlight C# %}

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 150;
currencyTextBox.Height = 25;
currencyTextBox.Value = 1234;
currencyTextBox.CurrencyPositivePattern = 3;

{% endhighlight %}
{% endtabs %}

![WPF CurrencyTextBox displays Positive Value Pattern](Culture-and-Number-Formats_images/wpf-currency-textbox-positive-value.png)

###  Negative Value Pattern

You can use the [CurrencyNegativePattern](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.CurrencyTextBox.html#Syncfusion_Windows_Shared_CurrencyTextBox_CurrencyNegativePattern) property to customize the location of the currency symbol and the negative currency values. In the table below,"$" denotes the symbol of the currency, and "n" denotes the number.

**CurrencyNegativePattern table**

<table>
<tr>
<th>
Value</th><th>
Associated Pattern</th></tr>
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

![WPF CurrencyTextBox displays Negative Value Patterns](Culture-and-Number-Formats_images/wpf-currency-textbox-negative-patterns.png)

{% tabs %}
{% highlight xaml %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150" Value="-1234" CurrencyNegativePattern="0"/>

{% endhighlight %}
{% highlight C# %}

CurrencyTextBox currencyTextBox = new CurrencyTextBox();
currencyTextBox.Width = 150;
currencyTextBox.Height = 25;
currencyTextBox.Value = -1234;
currencyTextBox.CurrencyNegativePattern = 0;

{% endhighlight %}
{% endtabs %}

![WPF CurrencyTextBox displays Negative Value Pattern](Culture-and-Number-Formats_images/wpf-currency-textbox-negative-value.png)

## See Also

* [Getting Started](Getting-Started.md)
* [Appearance](Appearance.md)
* [Restriction or Validation](Restriction-or-Validation.md)
