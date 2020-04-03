---
layout: post
title: Formatting options in SfTimePicker control | Syncfusion
description: This page explain about how to display the time in various format in the WPF SfTimePicker control and items features.
platform: wpf
control: SfTimePicker
documentation: ug
---

# Time Formatting in WPF SfTimePicker

The [SfTimePicker](https://www.syncfusion.com/wpf-ui-controls/timepicker) control allows the user to format the display time in various ways.

## Display the time using the FormatString

 We can edit and display the selected time with various formatting like short time, long time, universal time and 24 hour time formats by using the [FormatString](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~FormatString.html) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTimePicker x:Name="sfTimePicker" 
                         FormatString="HH:mm:ss"/>

{% endhighlight %}
{% highlight C# %}

SfTimePicker sfTimePicker = new SfTimePicker();
sfTimePicker.FormatString = "HH:mm:ss";

{% endhighlight %}
{% endtabs %}

![SfTimePicker with 24 hour time format](Features_images/Features_img1.png)

Here, `SfTimePicker` with 24 hour time format

## Specifying format for the TimeSelector

We can allow the user to select only the particular hour, minutes, seconds or meridiem value from the [SfTimeSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimeSelector.html) by using the [SelectorFormatString](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfTimePicker~SelectorFormatString.html) property.  By default, the hour, minutes and meridiem value selector is enabled in the `SfTimeSelector`.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTimePicker x:Name="sfTimePicker" 
                         SelectorFormatString="M"/>

{% endhighlight %}
{% highlight C# %}

SfTimePicker sfTimePicker = new SfTimePicker();
sfTimePicker.SelectorFormatString = "M";

{% endhighlight %}
{% endtabs %}

![SfTimePicker contains only hour and meridiem value selelctor](Features_images/Features_img2.png)

Here, the `SfTimeSelector` with only hour and meridiem value selector.

Click [here](https://github.com/SyncfusionExamples/wpf-time-picker-examples/tree/master/Samples/Formatting) to download the sample that showcases the edit, display time formatting and time selection formatting by the `SfTimePicker`.

N> A detailed explanation of standard time formatting is available [here](http://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.71).aspx). The result string produced by these format specifiers are influenced by the settings in the Regional Options control panel. Computers with different cultures or different time and time settings will generate different result strings.
