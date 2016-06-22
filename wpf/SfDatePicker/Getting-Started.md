---
layout: post
title: Getting Started documentation of SfDatePicker control for WPF
description: Getting Started documentation of SfDatePicker control for WPF
platform: wpf
control: SfDatePicker
documentation: ug
---

# Getting Started

This section explains how to create the SfDatePicker control

## Adding SfDatePicker control

Create a WPF project in Visual Studio and refer to the following assemblies.

* Syncfusion.SfInput.WPF

* Syncfusion.SfShared.WPF

The following code sample shows how to create the SfDatePicker from code-behind and XAML. 

{% tabs %}

{% highlight XAML %}

	<Window x:Class="SfDatePicker_WPF.DateSelectorDemo"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="clr-namespace:SfDatePicker_WPF" WindowState="Maximized"
        xmlns:input="http://schemas.syncfusion.com/wpf"
        Title="DatePicker" Height="300" Width="300">

    <Grid>
        <input:SfDatePicker x:Name="datePicker" VerticalAlignment="Center" Width="200" Margin="15"/>
    </Grid>
    </Window>

{% endhighlight %}

{% highlight c# %}

	     SfDatePicker datepicker = new SfDatePicker();
         grid.Children.Add(datepicker);

{% endhighlight %}

{% endtabs %}






