---
layout: post
title: Customizing DropDown in WPF TimePicker | Syncfusion
description: Learn how to customize dropdown visibility and height in WPF TimePicker control for better user experience.
platform: wpf
control: SfTimePicker
documentation: ug
---

# Customizing DropDown in WPF TimePicker

We can customize the [SfTimeSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTimeSelector.html) visibility, drop-down button visibility and height of the `SfTimeSelector`.

## Change DropDown height

The height of drop-down can be changed using [DropDownHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTimePicker.html#Syncfusion_Windows_Controls_Input_SfTimePicker_DropDownHeight) property.

{% tabs %}
{% highlight XAML %}

<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
    <syncfusion:SfTimePicker DropDownHeight="300"
                         Name="sfTimePicker"/>
</Window>

{% endhighlight %}
{% highlight c# %}
using Syncfusion.Windows.Controls.Input;

SfTimePicker sfTimePicker = new SfTimePicker();
sfTimePicker.DropDownHeight = 300;

{% endhighlight %}
{% endtabs %}

![SfTimePicker with DropDownHeight](Features_images/Customizing-DropDown_img2.png)

## Show or hide DropDown button

If we want to restrict the user from selecting a time from a drop-down time selector, we can hide the drop-down button by using the [ShowDropDownButton](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfTimePicker.html#Syncfusion_Windows_Controls_Input_SfTimePicker_ShowDropDownButton) property value as `false`. The default value of `ShowDropDownButton` property is `true`.

{% tabs %}
{% highlight XAML %}

<Window 
    . . .
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf">
    <syncfusion:SfTimePicker ShowDropDownButton="False"
                         Name="sfTimePicker"/>
</Window>

{% endhighlight %}
{% highlight c# %}
using Syncfusion.Windows.Controls.Input;

SfTimePicker sfTimePicker = new SfTimePicker();
sfTimePicker.ShowDropDownButton = false;

{% endhighlight %}
{% endtabs %}

![SfTimePicker hides the drop-down button](Features_images/Customizing-DropDown_img3.png)

Click [here](https://github.com/SyncfusionExamples/wpf-time-picker-examples/tree/master/Samples/TimeSelectorItem) to download the sample that showcases the DropDown customization support.
