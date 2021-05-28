---
layout: post
title: IsBusy in WPF Busy Indicator control | Syncfusion
description: Learn here all about IsBusy support in Syncfusion WPF Busy Indicator (SfBusyIndicator) control and more.
platform: wpf
control: Busy Indicator
 documentation: ug
---

# IsBusy in WPF Busy Indicator (SfBusyIndicator)

The IsBusy property in the BusyIndicator control is used to determine whether an animation needs to be executed or not.

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


N> View [sample](https://github.com/SyncfusionExamples/wpf-BusyIndicator-examples/tree/master/Samples/IsBusy) in GitHub
