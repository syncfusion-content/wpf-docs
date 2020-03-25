---
layout: post
title: Deals with  Formatting options | SfDatePicker | WPF | Syncfusion
description: Deals with  Formatting options of SfDatePicker control for WPF
platform: wpf
control: SfDatePicker
documentation: ug
---

# Date Formatting

The [SfDatePicker](https://www.syncfusion.com/wpf-ui-controls/datepicker) control allows the user to format the display date in various ways.

## Display the date using the FormatString

 We can display the selected date with various formatting like date, month and year formats by using the [FormatString](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~FormatString.html) property.

{% tab %}
{% highlight xaml %}

<syncfusion:SfDatePicker x:Name="datePicker" 
                         FormatString="M"/>

{% endhighlight  %}
{% highlight C# %}

SfDatePicker datePicker = new SfDatePicker();
datePicker.FormatString = "M";

{% endhighlight  %}
{% endtabs %}

![SfDatePicker selected date with month format](Features_images/Features_img1.png)

## Specifying format for the DateSelector

We can enable the user to select only the date or month or year from the [SfDateSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector.html) by using the [SelectorFormatString](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorFormatString.html) property.

{% tab %}
{% highlight xaml %}

<syncfusion:SfDatePicker x:Name="datePicker" 
                         SelectorFormatString="M"/>

{% endhighlight  %}
{% highlight C# %}

SfDatePicker datePicker = new SfDatePicker();
datePicker.SelectorFormatString = "M";

{% endhighlight  %}
{% endtabs %}

![SfDatePicker contains only month selector](Features_images/Features_img2.png)

Click [here]() to download the sample that showcases the display date formatting and date selection formatting by the `SfDatePicker`.

N> A detailed explanation of standard date time formatting is available [here](http://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.71).aspx). The result string produced by these format specifiers are influenced by the settings in the Regional Options control panel. Computers with different cultures or different date and time settings will generate different result strings.

