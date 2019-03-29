---
layout: post
title: Culture and Number Formats | CurrencyTextBox | wpf | Syncfusion
description: culture and number formats
platform: wpf
control: CurrencyTextBox 
documentation: ug
---

# Culture and Number Formats

## Culture

CurrencyTextBox provides globalization support through the [Culture](https://docs.microsoft.com/en-us/dotnet/api/system.globalization.cultureinfo.currentculture?view=netframework-4.7.2) property. 

{% tabs %}
{% highlight xaml %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150" Culture="en-US" Value="1234567"/>

{% endhighlight %}

{% highlight C# %}

Syncfusion.Windows.Shared.CurrencyTextBox currencyTextBox = new Syncfusion.Windows.Shared.CurrencyTextBox();
currencyTextBox.Width = 100;
currencyTextBox.Height = 25;
currencyTextBox.Value = 1234567;
currencyTextBox.Culture = new CultureInfo("en-US");

{% endhighlight %}
{% endtabs %}

![Culture format](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img1.png)

{% tabs %}
{% highlight xaml %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150"Culture="fr-FR" Value="1234567"/>

{% endhighlight %}

{% highlight C# %}

Syncfusion.Windows.Shared.CurrencyTextBox currencyTextBox = new Syncfusion.Windows.Shared.CurrencyTextBox();
currencyTextBox.Width = 100;
currencyTextBox.Height = 25;
currencyTextBox.Value = 1234567;
currencyTextBox.Culture = new CultureInfo("fr-FR");

{% endhighlight %}
{% endtabs %}

![Culture format](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img2.png)

As you have seen in these samples whenever you change the Culture property the Value is formatted based on the Culture.

## NumberFormat

You can customize the Number Format either by using the NumberFormat property or the [CurrencyGroupSeparator](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CurrencyTextBox~CurrencyGroupSeparator.html), [CurrencyGroupSizes](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CurrencyTextBox~CurrencyGroupSizes.html), [CurrencyDecimalDigits](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CurrencyTextBox~CurrencyDecimalDigits.html), and [CurrencyDecimalSeparator](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CurrencyTextBox~CurrencyDecimalSeparator.html), [CurrencySymbol](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CurrencyTextBox~CurrencySymbol.html), [CurrencyNegativePattern](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CurrencyTextBox~CurrencyNegativePattern.html), and [CurrencyPositivePattern](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.CurrencyTextBox~CurrencyPositivePattern.html) properties.

{% tabs %}
{% highlight xaml %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150"  Value="1234567">   
<syncfusion:CurrencyTextBox.NumberFormat>        
<numberformat:NumberFormatInfo CurrencyGroupSeparator="/" CurrencyDecimalDigits="4" CurrencyDecimalSeparator="*"   CurrencySymbol="$"/>  
</syncfusion:CurrencyTextBox.NumberFormat></syncfusion:CurrencyTextBox>

{% endhighlight %}

{% highlight C# %}

Syncfusion.Windows.Shared.CurrencyTextBox currencyTextBox = new  Syncfusion.Windows.Shared.CurrencyTextBox();
currencyTextBox.Width = 100;
currencyTextBox.Height = 25;
currencyTextBox.Value = 1234567;
currencyTextBox.NumberFormat = new NumberFormatInfo() { CurrencyGroupSeparator = "/", CurrencyDecimalDigits = 4, CurrencyDecimalSeparator = "*", CurrencySymbol = "$" };

{% endhighlight %}
{% endtabs %}

![Number format](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img3.png)

{% tabs %}
{% highlight xaml %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150" Value="1234567" CurrencyGroupSeparator="/" CurrencyDecimalDigits="4"    CurrencyDecimalSeparator="*" CurrencySymbol="$">
</syncfusion:CurrencyTextBox>

{% endhighlight %}

{% highlight C# %}

Syncfusion.Windows.Shared.CurrencyTextBox currencyTextBox = new   Syncfusion.Windows.Shared.CurrencyTextBox();
currencyTextBox.Width = 100;
currencyTextBox.Height = 25;
currencyTextBox.Value = 1234567;
currencyTextBox.CurrencyGroupSeparator = "/";
currencyTextBox.CurrencyDecimalDigits = 4;
currencyTextBox.CurrencyDecimalSeparator = "*";
currencyTextBox.CurrencySymbol = "$";

{% endhighlight %}
{% endtabs %}

![Number format](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img4.png)

### CurrencyPositivePattern

Gets or sets the format pattern for the positive currency values. In the table displayed below “$” denotes the Currency symbol and n denotes the number.

CurrencyPositivePattern table

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

{% tabs %}
{% highlight xaml %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150" Value="1234" CurrencyPositivePattern="3"/>

{% endhighlight %}
{% endtabs %}

![Currency pattern](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img5.png)

### CurrencyNegativePattern

Gets or sets the format pattern for the negative currency values. In the table displayed below “$” denotes the Currency symbol and n denotes the number.

CurrencyNegativePattern table

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

{% tabs %}
{% highlight xaml %}

<syncfusion:CurrencyTextBox x:Name="currencyTextBox" Height="25" Width="150" Value="-1234" CurrencyNegativePattern="0"/>

{% endhighlight %}
{% endtabs %}

![Currency negative pattern](Culture-and-Number-Formats_images/Culture-and-Number-Formats_img6.png)
