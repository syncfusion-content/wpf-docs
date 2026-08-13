---
layout: post
title: IsBusy in WPF SfBusyIndicator | Syncfusion®
description: The IsBusy property in WPF SfBusyIndicator controls the busy state, enabling responsive feedback and indicating ongoing processing tasks to users.
platform: wpf
control: Busy Indicator
documentation: ug
---

# IsBusy in WPF SfBusyIndicator

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
