---
layout: post
title: Getting Started with WPF Busy Indicator Control | Syncfusion®
description: Learn how to get started with the Syncfusion® WPF Busy Indicator (SfBusyIndicator) control, including its elements and additional details.
platform: WPF
control: Busy Indicator
documentation: ug
---

# Getting Started with WPF Busy Indicator (SfBusyIndicator)

Namespace: `Syncfusion.Windows.Controls.Notification`

Assembly: `Syncfusion.SfBusyIndicator.WPF` (in Syncfusion.SfBusyIndicator.WPF.dll)

The following code examples demonstrate how to create the `SfBusyIndicator` using XAML and C# code-behind.

{% tabs %}

{% highlight xaml %}

<Page xmlns:Notification="clr-namespace:Syncfusion.Windows.Controls.Notification;assembly=Syncfusion.SfBusyIndicator.WPF">

    <Grid Background="CornflowerBlue">

        <Notification:SfBusyIndicator/>

    </Grid>

</Page>

{% endhighlight  %}

{% highlight c# %}

SfBusyIndicator busyIndicator = new SfBusyIndicator();

{% endhighlight  %}

{% endtabs %}

> **Note:** View the [sample](https://github.com/SyncfusionExamples/wpf-BusyIndicator-examples/tree/master/Samples/Getting-Started) on GitHub.

## Theme

The `SfBusyIndicator` supports various built-in themes. Refer to the links below to apply themes to the `SfBusyIndicator`:

  * [Apply Theme Using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a Custom Theme Using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

![Setting the Theme for WPF SfBusyIndicator](IsBusy_images/Theme.png)
