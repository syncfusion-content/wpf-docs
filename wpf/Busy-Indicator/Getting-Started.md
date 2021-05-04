---
layout: post
title: Getting Started with WPF Busy Indicator control | Syncfusion
description: Learn here about getting started with Syncfusion WPF Busy Indicator (SfBusyIndicator) control, its elements and more details.
platform: wpf
control: Busy Indicator
documentation: ug
---

# Getting Started with WPF Busy Indicator (SfBusyIndicator)

Namespace: Syncfusion.Windows.Controls.Notification.

Assembly: Syncfusion.SfBusyIndicator.WPF (in Syncfusion.SfBusyIndicator.WPF.dll)

The following code example shows how to create the SfBusyIndicator from XAML and code behind respectively.

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


N> View [sample](https://github.com/SyncfusionExamples/wpf-BusyIndicator-examples/tree/master/Samples/Getting-Started) in GitHub

## Theme

SfBusyIndicator supports various built-in themes. Refer to the below links to apply themes for the SfBusyIndicator,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF SfBusyIndicator](IsBusy_images/Theme.png)