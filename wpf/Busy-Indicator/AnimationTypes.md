---
layout: post
title: Animation Types in WPF Busy Indicator | Syncfusion®
description: Animation types in WPF Busy Indicator provide visual feedback during processing with multiple built-in animations to enhance user engagement and experience.
platform: wpf
control: Busy Indicator
documentation: ug
---

# Animation Types in WPF Busy Indicator

The AnimationTypes property for the busy indicator allows the user to set one of the animations from the built-in animations.

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
