---
layout: post
title: Customizing DropDown in WPF DatePicker control | Syncfusion
description: Learn here all about Customizing DropDown support in Syncfusion WPF DatePicker (SfDatePicker) control and more.
platform: wpf
control:  SfDatePicker
documentation: ug
---

# Customizing DropDown in WPF DatePicker (SfDatePicker)

We can customize the [SfDateSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDateSelector.html) visibility, drop down button visibility and height of the `SfDateSelector`.

## Change DropDown height

The height of drop down can be changed using [DropDownHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDatePicker.html#Syncfusion_Windows_Controls_Input_SfDatePicker_DropDownHeight) property.

{% tabs %}
{% highlight XAML %}

<syncfusion:SfDatePicker DropDownHeight="300" 
	                     x:Name="sfDatePicker"/>

{% endhighlight %}
{% highlight c# %}

SfDatePicker sfDatePicker = new SfDatePicker();
sfDatePicker.DropDownHeight = 300;

{% endhighlight %}
{% endtabs %}

![WPF DatePicker DropdownHeight](Customizing-DropDown_images/wpf-datepicker-dropdownheight.png)

## Show or hide DropDown button

If we want to restrict the user to selecting a date from a drop down date selector, we can hide the drop down button by using the [ShowDropDownButton](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Input.SfDatePicker.html#Syncfusion_Windows_Controls_Input_SfDatePicker_ShowDropDownButton) property value as `false`. The default value of `ShowDropDownButton` property is `true`.

{% tabs %}
{% highlight XAML %}

<syncfusion:SfDatePicker ShowDropDownButton="False" 
	                     x:Name="sfDatePicker"/>

{% endhighlight %}
{% highlight c# %}

SfDatePicker sfDatePicker = new SfDatePicker();
sfDatePicker.ShowDropDownButton = false;

{% endhighlight %}
{% endtabs %}

![WPF DatePicker Dropdown Button](Customizing-DropDown_images/wpf-datepicker-dropdown-button.png)

Click [here](https://github.com/SyncfusionExamples/wpf-date-picker-examples/tree/master/Samples/DateSelectorItem) to download the sample that showcases the DropDown customization support.
