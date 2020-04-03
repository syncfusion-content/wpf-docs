---
layout: post
title: Formatting options in SfDatePicker control | Syncfusion
description: This page explain about how to display the date in various format in the WPF SfDatePicker control and items features.
platform: wpf
control: SfDatePicker
documentation: ug
---

# Date Formatting in WPF SfDatePicker

The [SfDatePicker](https://www.syncfusion.com/wpf-ui-controls/datepicker) control allows the user to format the display date in various ways.

## Display the date using the FormatString

 We can edit and display the selected date with various formatting like date, month and year formats by using the [FormatString](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~FormatString.html) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDatePicker x:Name="sfDatePicker" 
                         FormatString="M"/>

{% endhighlight %}
{% highlight C# %}

SfDatePicker sfDatePicker = new SfDatePicker();
sfDatePicker.FormatString = "M";

{% endhighlight %}
{% endtabs %}

![SfDatePicker selected date with month format](Features_images/Features_img1.png)

## Specifying format for the DateSelector

We can allow the user to select only the date or month or year from the [SfDateSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector.html) by using the [SelectorFormatString](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorFormatString.html) property. By default, the date, time and year value selector is enabled in the `SfDateSelector`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDatePicker x:Name="sfDatePicker" 
                         SelectorFormatString="M"/>

{% endhighlight %}
{% highlight C# %}

SfDatePicker sfDatePicker = new SfDatePicker();
sfDatePicker.SelectorFormatString = "M";

{% endhighlight %}
{% endtabs %}

![SfDatePicker contains only month selector](Features_images/Features_img2.png)

Click [here](https://github.com/SyncfusionExamples/wpf-date-picker-examples/tree/master/Samples/Formatting) to download the sample that showcases the edit, display date formatting and date selection formatting by the `SfDatePicker`.

N> A detailed explanation of standard date time formatting is available [here](http://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.71).aspx). The result string produced by these format specifiers are influenced by the settings in the Regional Options control panel. Computers with different cultures or different date and time settings will generate different result strings.

