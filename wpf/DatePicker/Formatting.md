---
layout: post
title: Deals with  Formatting options | SfDatePicker | WPF | Syncfusion
description: Deals with  Formatting options of SfDatePicker control for WPF
platform: wpf
control: SfDatePicker
documentation: ug
---

# Formatting

The SfDatePicker control allows the user to format the display text in various ways.

## Using the FormatString

The [FormatString](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~FormatString.html) property determines the format specifier by which the display text has to be formatted.

The following code sample shows how to create a date picker with a [month day pattern](http://msdn.microsoft.com/en-us/library/system.globalization.datetimeformatinfo.monthdaypattern(v=vs.71).aspx): 

{% highlight xaml %}



		<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

            <syncfusion:SfDatePicker VerticalAlignment="Center" 

                                   Width="200" Margin="15"

                                   FormatString="M"/>



		</Grid>


{% endhighlight  %}


![Format string](Features_images/Features_img1.png)

## Specifying format for the DateSelector

The [SelectorFormatString](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorFormatString.html) property used to specify format for the DateSelector



{% highlight xaml %}

	<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

    <syncfusion:SfDatePicker SelectorFormatString="M"   x:Name="sfdatePicker" VerticalAlignment="Center"  Width="200" Margin="15" />

	</Grid>

{% endhighlight  %}


![Selector format string](Features_images/Features_img2.png)


N> A detailed explanation of standard date time formatting is available [here](http://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.71).aspx). The result string produced by these format specifiers are influenced by the settings in the Regional Options control panel. Computers with different cultures or different date and time settings will generate different result strings.
