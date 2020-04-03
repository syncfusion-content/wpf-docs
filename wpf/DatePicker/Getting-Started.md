---
layout: post
title: Getting started with WPF SfDatePicker control | Syncfusion
description: Learn here about getting started with Syncfusion WPF SfDatePicker control and more details about the control features.
platform: WPF
control: SfDatePicker
documentation: ug
---

# Getting Started with WPF SfDatePicker

This section explains how to create a WPF [SfDatePicker](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker.html) and explains about its structure.

## Structure of SfDatePicker

![WPF SfDatePicker Control](GettingStarted_images/SfDatePicker.png)

## Assembly deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#sfdatepicker) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

You can find more details about installing the NuGet package in a WPF application in the following link: 

[How to install nuget packages](https://help.syncfusion.com/wpf/nuget-packages)

## Add control through designer

The `SfDatePicker` control can be added to an application by dragging it from the toolbox to a designer view. The following required assembly references will be added automatically:

* Syncfusion.SfInput.WPF
* Syncfusion.SfShared.WPF

![SfDatePicker control added by designer](GettingStarted_images/wpf-date-picker-control-added-by-designer.png)

## Adding control manually in XAML

To add the control manually in XAML, follow the given steps:

1.	Add the following required assembly references to the project:
    * Syncfusion.SfInput.WPF
    * Syncfusion.SfShared.WPF
2.	Import Syncfusion WPF schema **http://schemas.syncfusion.com/wpf** in the XAML page.
3.	Declare the `SfDatePicker` control in the XAML page.

{% tabs %}
{% highlight XAML %}

<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
        x:Class="SfDatePickerSample.MainWindow"
        Title="SfDatePicker Sample" Height="350" Width="525">
    <Grid>
        <!-- Adding SfDatePicker control -->
        <syncfusion:SfDatePicker x:Name="sfDatePicker" 
                                 Width="200"/>
    </Grid>
</Window>

{% endhighlight %}
{% endtabs %}

## Add control manually in C\#

To add the control manually in C#, follow the given steps:

1.	Add the following required assembly references to the project:
    * Syncfusion.SfInput.WPF
    * Syncfusion.SfShared.WPF
2.	Import the `SfDatePicker` namespace **using Syncfusion.Windows.Controls.Input;**.
3.	Create an `SfDatePicker` instance, and add it to the window.

{% tabs %}
{% highlight C# %}

using Syncfusion.Windows.Controls.Input;
namespace SfDatePickerSample {    
    public partial class MainWindow : Window {
        public MainWindow() {
            InitializeComponent();

            //Creating an instance of SfDatePicker control
            SfDatePicker sfDatePicker = new SfDatePicker();

            //Adding SfDatePicker as window content
            this.Content = sfDatePicker;
        } 
    }
}

{% endhighlight %}
{% endtabs %}

![SfDatePicker control added by code](GettingStarted_images/wpf-date-picker.png)

## Setting the Date

We can set or change the selected date by using either [Value](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~Value.html) or [DateTime](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~DateTime.html) property. Here, `Value` is the `object` type property and `DateTime` is the `DateTime` type property.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDatePicker  Value="5/30/2021"
						  Name="sfDatePicker" />

{% endhighlight %}
{% highlight C# %}

SfDatePicker sfDatePicker= new SfDatePicker();
sfDatePicker.Value = new DateTime(2021,5,30);

{% endhighlight %}
{% endtabs %}

![SfDatePicker displaying selected value](Features_images/Features_img17.png)

## Date changed notification

When the selected date of `SfDatePicker`is changed, it will be notified by using the [ValueChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~ValueChanged_EV.html) event. You can get the details about the checked item in [ItemCheckedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Tools.Wpf~Syncfusion.Windows.Tools.Controls.ItemCheckedEventArgs.html).

* **OldValue** : Gets a date which is previously selected.

* **NewValue** : Gets a date which is currently selected.

{% tabs %}
{% highlight XAML %}

<syncfusion:SfDatePicker ValueChanged="SfdatePicker_ValueChanged" 
                         Name="sfDatePicker"/>

{% endhighlight %}
{% highlight C# %}

SfDatePicker sfDatePicker = new SfDatePicker();
sfDatePicker.ValueChanged += SfdatePicker_ValueChanged;

{% endhighlight %}
{% endtabs %}

You can handle the event as follows:

{% tabs %}
{% highlight C# %}

private void SfdatePicker_ValueChanged(DependencyObject d, DependencyPropertyChangedEventArgs e) {          
    Console.WriteLine("The Old selected Date: " + e.OldValue.ToString());
    Console.WriteLine("The Newly selected Date: " + e.NewValue.ToString());            
}

{% endhighlight %}
{% endtabs %}

## Display the date using the FormatString

 We can edit and display the selected date with various formatting like date, month and year formats by using the [FormatString](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~FormatString.html) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDatePicker x:Name="sfDatePicker" 
                         FormatString="M"/>

{% endhighlight  %}
{% highlight C# %}

SfDatePicker sfDatePicker = new SfDatePicker();
sfDatePicker.FormatString = "M";

{% endhighlight  %}
{% endtabs %}

![SfDatePicker selected date with month format](Features_images/Features_img1.png)

## Specifying format for the DateSelector

We can enable the user to select only the date or month or year from the [SfDateSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDateSelector.html) by using the [SelectorFormatString](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SelectorFormatString.html) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDatePicker x:Name="sfDatePicker" 
                         SelectorFormatString="M"/>

{% endhighlight  %}
{% highlight C# %}

SfDatePicker sfDatePicker = new SfDatePicker();
sfDatePicker.SelectorFormatString = "M";

{% endhighlight  %}
{% endtabs %}

![SfDatePicker contains only month selector](Features_images/Features_img2.png)

Click [here](https://github.com/SyncfusionExamples/wpf-date-picker-examples/tree/master/Samples/Formatting) to download the sample that showcases the display date formatting and date selection formatting by the `SfDatePicker`.

## Set selected value on lost focus

By default, the selected date of DateSelector can be sets to the `SfDatePicker.Value` property by clicking the `OK` button. If We want to update the selected date of DateSelector to the `SfDatePicker.Value` property automatically without clicking the OK button, use the [SetValueOnLostFocus](https://help.syncfusion.com/cr/wpf/Syncfusion.SfInput.Wpf~Syncfusion.Windows.Controls.Input.SfDatePicker~SetValueOnLostFocus.html) property value as `true`. This is value updated after the DateSelector lost its focus. The default value of `SetValueOnLostFocus` property is false.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDatePicker  SetValueOnLostFocus="True"
				          Name="sfDatePicker" />

{% endhighlight %}
{% highlight C# %}

SfDatePicker sfDatePicker= new SfDatePicker();
sfDatePicker.SetValueOnLostFocus = true;

{% endhighlight %}
{% endtabs %}

![SfDatePicker value updated on when SfDateSelector lost its focus](Features_images/Features_img15.gif)

Click [here](https://github.com/SyncfusionExamples/wpf-date-picker-examples/tree/master/Samples/SfDatePicker-Value-setting) to download the sample that showcases the value setting support in the `SfDatePicker`.