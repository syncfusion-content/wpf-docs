---
layout: post
title: Animation Types in WPF Busy Indicator Control | Syncfusion®
description: Learn about animation types supported in the Syncfusion® WPF Busy Indicator (SfBusyIndicator) control.
platform: WPF
control: Busy Indicator
documentation: ug
---

# Animation Types in WPF Busy Indicator (SfBusyIndicator)

The `AnimationType` property for the SfBusyIndicator allows the user to select one of the built-in animations as the busy indicator.

> **Note:** The `AnimationSpeed` property is not applicable for the `Fluent` animation type.

{% tabs %}

{% highlight xaml %}

<Grid Background="CornflowerBlue">

    <Notification:SfBusyIndicator AnimationType="Flight"/>

</Grid>

{% endhighlight  %}

{% highlight c# %}

SfBusyIndicator busyIndicator = new SfBusyIndicator();

busyIndicator.AnimationType = AnimationTypes.Flight;

{% endhighlight  %}

{% endtabs %}

The following gif image showcases the types of animations available in BusyIndicator.

![Animation Types](AnimationTypes_images/BusyIndicator-animation-video.gif)

> **Note:** View the [sample](https://github.com/SyncfusionExamples/wpf-BusyIndicator-Sample) on GitHub.
