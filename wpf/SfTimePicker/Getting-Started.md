---
layout: post
title: Getting Started documentation of SfTimePicker control  for WPF
description: Getting Started documentation of SfTimePicker control  for WPF
platform: wpf
control: SfTimePicker
documentation: ug
---

# Getting Started

This section explains how to create the SfTimePicker control

## Adding SfTimePicker control

Create a WPF project in Visual Studio and refer to the following assemblies.

* Syncfusion.SfInput.WPF

* Syncfusion.SfShared.WPF

The following code sample shows how to create the SfDatePicker from code-behind and XAML. 

{% tabs %}

{% highlight XAML %}


	<Window x:Class="SfTimePicker_WPF"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="clr-namespace:SfDatePicker_WPF" WindowState="Maximized"
        xmlns:input="http://schemas.syncfusion.com/wpf"
        Title="TimePicker" Height="300" Width="300">

    <Grid>
        <input:SfTimePicker x:Name="datePicker" VerticalAlignment="Center" Width="200" />
    </Grid>
    </Window>

{% endhighlight %}

{% highlight c# %}

	     SfTimePicker datepicker = new SfTimePicker();
         grid.Children.Add(timepicker);

{% endhighlight %}

{% endtabs %}






