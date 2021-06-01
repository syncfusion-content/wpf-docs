---
layout: post
title: Number Formatting in WPF NumericUpdown control | Syncfusion
description: Learn here all about Number Formatting support in Syncfusion WPF NumericUpdown (UpDown) control and more.
platform: wpf
control: UpDown
documentation: ug
---

# Number Formatting in WPF NumericUpdown (UpDown)

This section explains how to format the value in WPF UpDown control.

## Decimal digit

The [NumberDecimalDigits](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_NumberDecimalDigits) property is used to specify the number of digits to be displayed after the decimal point in the [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html) control.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Height="23" Width="100" NumberDecimalDigits="4" />

{% endhighlight %}

{% highlight C# %}

UpDown updown = new UpDown();
updown.Height = 23;
updown.Width = 100;
updown.NumberDecimalDigits = 4;
grid.Children.Add(updown);

{% endhighlight %}

{% endtabs %}

![Set the number decimal digits in WPF UpDown](CultureandNumberFormatting-images/wpf-updown-decimal.png)

## Group separator

The group separator is the character used to group the values. You can show the group separator in UpDown control by enable [GroupSeparatorEnabled](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_GroupSeperatorEnabled) property. The default value is `False`.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Width="100" Height="23" Value="5555555" GroupSeperatorEnabled="True" />

{% endhighlight %}

{% highlight C# %}

updown.Value = 5555555;
updown.GroupSeperatorEnabled = true;

{% endhighlight %}

{% endtabs %}

![Enabled the GroupSepartor into WPF UpDown control](CultureandNumberFormatting-images/wpf-updown-groupseparator.png)

## NumberFormatInfo

The number formatting of UpDown control can be customized by setting [UpDown.NumberFormatInfo](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_NumberFormatInfo) property by specifying the culture-specific group separator, decimal separator, and the number of decimal digits. You can show the group separator by enable the [GroupSeparatorEnabled](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_GroupSeperatorEnabled) property.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Value="5555555" GroupSeperatorEnabled="True">
<syncfusion:UpDown.NumberFormatInfo>
<globalization:NumberFormatInfo NumberGroupSeparator="/" NumberDecimalDigits="4" NumberDecimalSeparator="*"/>
</ syncfusion:UpDown.NumberFormatInfo>  
</ syncfusion:UpDown>

{% endhighlight %}

{% highlight C# %}

//Assign a value
updown.Value = 5555555;

//Initialize numberformatinfo
NumberFormatInfo numberFormatInfo = new NumberFormatInfo();

// set the format of number and group
updown.GroupSeperatorEnabled = true;
updown.NumberFormatInfo = numberFormatInfo;
updown.NumberFormatInfo.NumberGroupSeparator = "/";
updown.NumberFormatInfo.NumberDecimalDigits = 4;
updown.NumberFormatInfo.NumberDecimalSeparator = "*";

{% endhighlight %}

{% endtabs %} 

![Applied group and decimal separator of number format to WPF UpDown](CultureandNumberFormatting-images/wpf-updown-numberformat.png)

## Culture

The UpDown control provides globalization support to change the culture of the control by using the [Culture](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_Culture) property. The culture is used to format the decimal separator and group separator based on the respective culture.

For example, the Latin culture is used into the UpDown control.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Culture="bs-Latn" Value="5555555" Width="100" Height="23" />

{% endhighlight %}

{% highlight C# %}

System.Globalization.CultureInfo cultureInfo = new System.Globalization.CultureInfo("bs-Latn");
updown.Culture = cultureInfo;
updown.Value = 5555555;

{% endhighlight %}

{% endtabs %} 

![Applied latin culture into WPF UpDown](CultureandNumberFormatting-images/wpf-updown-latin_culture.png)
 
## Text alignment

You can align the text by using the [TextAlignment](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Shared.UpDown.html#Syncfusion_Windows_Shared_UpDown_TextAlignment) property.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Value="40" Height="23" TextAlignment="Left" Width="100" />

{% endhighlight %}

{% highlight C# %}

updown.TextAlignment = TextAlignment.Left;

{% endhighlight %}

{% endtabs %}

![Applied alignment into WPF UpDown control](CultureandNumberFormatting-images/wpf-updown-alignment.png)
