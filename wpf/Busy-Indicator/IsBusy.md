---
layout: post
title: IsBusy in WPF Busy Indicator Control | Syncfusion®
description: Learn all about IsBusy support in the Syncfusion® WPF Busy Indicator (SfBusyIndicator) control and more.
platform: WPF
control: Busy Indicator
documentation: ug
---

# IsBusy in WPF Busy Indicator (SfBusyIndicator)

The `IsBusy` property in the `SfBusyIndicator` control is used to determine whether an animation should be executed.

{% tabs %}

{% highlight xaml %}

<Grid Background="CornflowerBlue">

    <Navigation:SfBusyIndicator IsBusy="True"/>

</Grid>

{% endhighlight %}

{% highlight c# %}

SfBusyIndicator busyIndicator = new SfBusyIndicator();

busyIndicator.IsBusy = true;

{% endhighlight %}

{% endtabs %}

![IsBusy](IsBusy_images/IsBusy_img1.png)

Busy Indicator
{:.caption}

> **Note:** View the [sample](https://github.com/SyncfusionExamples/wpf-BusyIndicator-examples/tree/master/Samples/IsBusy) on GitHub.
