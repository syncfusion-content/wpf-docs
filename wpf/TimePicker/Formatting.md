---
layout: post
title: Time Formatting in WPF TimePicker control | Syncfusion
description: Learn here all about Time Formatting support in Syncfusion WPF TimePicker (SfTimePicker) control and more.
platform: wpf
control: SfTimePicker
documentation: ug
---

# Time Formatting in WPF TimePicker (SfTimePicker)

The [SfTimePicker](https://www.syncfusion.com/wpf-ui-controls/timepicker) control allows the user to select and display the time in various formats.

## Display the time using the FormatString

 We can edit and display the selected time with various formatting like short time, long time, universal time and 24 hour time formats by using the [FormatString](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTimePicker.html#Syncfusion_Windows_Controls_Input_SfTimePicker_FormatString) property. The default value of `FormatString` property is `"h:mm tt"`.

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

We can allow the user to select the pair of hour, minutes, seconds and meridiem selector or any single selector cell from the [SfTimeSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTimeSelector.html) by using the [SelectorFormatString](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTimePicker.html#Syncfusion_Windows_Controls_Input_SfTimePicker_SelectorFormatString) property. The default value of `SelectorFormatString` property is `"h:mm tt"` and the hour, minutes and meridiem value selector is enabled in the `SfTimeSelector`.

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

![SfTimePicker contains only hour and meridiem value selector](Features_images/Features_img2.png)

Here, we can only able to select the hour and meridiem value from the `SfTimeSelector`

Click [here](https://github.com/SyncfusionExamples/wpf-time-picker-examples/tree/master/Samples/Formatting) to download the sample that showcases the edit, display time formatting and time selection formatting by the `SfTimePicker`.

N> A detailed explanation of standard time formatting is available [here](https://docs.microsoft.com/en-us/previous-versions/dotnet/netframework-1.1/az4se3k1(v=vs.71)). The result string produced by these format specifiers are influenced by the settings in the Regional Options control panel. Computers with different cultures or different time and time settings will generate different result strings.
