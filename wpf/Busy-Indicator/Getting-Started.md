---
layout: post
title: Getting Started with WPF Busy Indicator control | Syncfusion®
description: Learn here about getting started with Syncfusion® WPF Busy Indicator (SfBusyIndicator) control, its elements and more details.
platform: wpf
control: Busy Indicator
documentation: ug
---

# Getting Started with WPF Busy Indicator (SfBusyIndicator)

This section explains how to create a WPF application and add the [SfBusyIndicator](https://help.syncfusion.com/wpf/busy-indicator/overview) control to it. It also covers the basics of the control and steps to show a busy state for long-running operations.

**Namespace:** `Syncfusion.Windows.Controls.Notification`

**Assembly:** `Syncfusion.SfBusyIndicator.WPF.dll`

## Create the SfBusyIndicator

The following code example shows how to create the SfBusyIndicator in XAML and in code-behind.

{% tabs %}

{% highlight xaml %}

<Window x:Class="GettingStarted.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:syncfusion="clr-namespace:Syncfusion.Windows.Controls.Notification;assembly=Syncfusion.SfBusyIndicator.WPF"
        Title="Getting Started" Height="450" Width="800">
    <Grid Background="CornflowerBlue">
        <syncfusion:SfBusyIndicator x:Name="busyIndicator"/>
    </Grid>
</Window>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.Windows.Controls.Notification;

public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent()
        SfBusyIndicator busyIndicator = new SfBusyIndicator();
        this.Content = busyIndicator;
    }
}

{% endhighlight %}

{% endtabs %}

N> View [sample](https://github.com/SyncfusionExamples/wpf-BusyIndicator-examples/tree/master/Samples/Getting-Started) on GitHub.

## Theme

SfBusyIndicator supports various built-in themes. Refer to the following links to apply themes for the SfBusyIndicator:

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF SfBusyIndicator](IsBusy_images/Theme.png)