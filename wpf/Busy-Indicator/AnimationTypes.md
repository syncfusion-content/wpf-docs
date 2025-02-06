---
layout: post
title: AnimationTypes in WPF Busy Indicator control | Syncfusion®
description: Learn here all about AnimationTypes support in Syncfusion® WPF Busy Indicator (SfBusyIndicator) control and more.
platform: wpf
control: Busy Indicator
documentation: ug
---

# AnimationTypes in WPF Busy Indicator (SfBusyIndicator)

The AnimationTypes property for the SfBusyIndicator allows the user to set one of the animations from the built-in animations as the busy indicator.

N> `AnimationSpeed` property is not applicable for `Fluent` animation type.

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


The following gif image contains the types of animation in BusyIndicator.

![AnimationTypes](AnimationTypes_images/BusyIndicator-animation-video.gif)

N> View [sample](https://github.com/SyncfusionExamples/wpf-BusyIndicator-examples/tree/master/Samples/AnimationType) in GitHub
