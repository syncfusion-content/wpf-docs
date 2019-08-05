---
layout: post
title: Formatting | UpDown | WPF | Syncfusion
description: This section explains about the Culture and Number Formatting of UpDown control
platform: wpf
control: UpDown
documentation: ug
---

# Formatting

The Number formatting controls how a number is displayed in the [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown.html) control by specifying the culture-specific group separator, decimal separator, and the number of decimal digits to be used. It can also format the value of the `UpDown` control by using the `NumberFormatInfo` property.

## Decimal digit

The [NumberDecimalDigits](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~NumberDecimalDigits.html) property is used to raise the amount of zeros after the decimal point in the UpDown control.

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

![Displays the decimal digits in WPF UpDown](CultureandNumberFormatting-images/Updown_decimal.png)

## Culture

The UpDown control provides globalization support by enabling to change the culture of the control by using the [Culture](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~Culture.html) property.

As shown in the following code example, the [Culture](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~Culture.html) property can be set to `en-US` for UpDown control. The U.S. culture uses "." as the decimal seperator.

{%tabs%}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Culture="en-US" Width="100" Height="23" />

{% endhighlight %}

{% highlight C# %}

System.Globalization.CultureInfo cultureInfo = new System.Globalization.CultureInfo("en-US");
updown.Culture = cultureInfo;

{% endhighlight %}

{% endtabs %} 

![Applied US culture into WPF UpDown](CultureandNumberFormatting-images/CultureandNumberFormatting-img1.jpeg)


As shown in the following code example, the [Culture](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~Culture.html) property can also be set to `bs-Latn` for the UpDown control. The Latin culture uses ","as the decimal seperator.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Name="upDown" Culture="bs-Latn" Width="100" Height="23" />

{% endhighlight %}

{% highlight C# %}

System.Globalization.CultureInfo cultureInfo = new System.Globalization.CultureInfo("bs-Latn");
updown.Culture = cultureInfo;

{% endhighlight %}

{% endtabs %} 

![Applied latin culture into WPF UpDown](CultureandNumberFormatting-images/CultureandNumberFormatting-img2.jpeg)


## Group separator

The [GroupSeparatorEnabled](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~GroupSeperatorEnabled.html) property enables add the group separator to the [UpDown](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown.html) control value. Its default value is `false`.

The following instance of code describes how to set the `GroupSeparatorEnabled` property for the `UpDown` control:

{% tabs %}

{% highlight XAML %}
<syncfusion:UpDown Name="upDown" Width="100" Height="23" Value="5555555" GroupSeperatorEnabled="True" />

{% endhighlight %}

{% highlight C# %}

updown.Value = 5555555;
updown.GroupSeperatorEnabled = true;

{% endhighlight %}
{% endtabs %}

![Enabled the GroupSepartor into WPF UpDown control](CultureandNumberFormatting-images/Updown_groupseparator.png)

## NumberFormatInfo

The [NumberFormatInfo](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.UpDown~NumberFormatInfo.html) can be set for the `UpDown` control as shown in the following code example.

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

{% endtabs %} 

![Applied group and decimal separator of number format in WPF UpDown](CultureandNumberFormatting-images/Updown_numberformat.png)

 
## Text alignment

You can align the text by using the `TextAlignment` property of UpDown control. You can align the text with the following choices. The options are Left, Right, Center and Justify.

{% tabs %}

{% highlight XAML %}

<syncfusion:UpDown Value="40" Height="23" TextAlignment="Left" Width="100" />

{% endhighlight %}

{% highlight C# %}

updown.TextAlignment = TextAlignment.Left;

{% endhighlight %}

{% endtabs %}

![Applied alignment into WPF UpDown control](CultureandNumberFormatting-images/Updown_alignment.png)
