---
layout: post
title: DropDown Customization | SfDatePicker | WPF | Syncfusion
description: Explains about DropDown Customization of the SfDatePicker control for WPF
platform: wpf
control:  SfDatePicker
documentation: ug
---
# Customizing DropDown

## DropDown height

The height of drop down can be changed using [DropDownHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~DropDownHeight.html) property.

{% tabs %}

{% highlight XAML %}

	<syncfusion:SfDatePicker x:Name="sfdatePicker" VerticalAlignment="Center"  Width="200" Margin="15" DropDownHeight="300" />

{% endhighlight %}

{% highlight c# %}

	sfdatePicker.DropDownHeight = 200;

{% endhighlight %}

{% endtabs %}

![DropDown height](Customizing-DropDown_images/Customizing-DropDown_img2.png)


## IsDropDownOpen

Drop down can be programmatically opened or closed using the property [IsDropDownOpen](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~IsDropDownOpen.html).

## ShowDropDownButton

DropDownButton visibility can be changed by using the [ShowDropDownButton](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~ShowDropDownButton.html) property

{% tabs %}

{% highlight XAML %}

	<syncfusion:SfDatePicker x:Name="sfdatePicker" VerticalAlignment="Center"  Width="200" Margin="15" ShowDropDownButton="True"/>

{% endhighlight %}

{% highlight c# %}

	sfdatePicker.ShowDropDownButton = true;

{% endhighlight %}

{% endtabs %}

![Show drop down button](Customizing-DropDown_images/Customizing-DropDown_img3.png)