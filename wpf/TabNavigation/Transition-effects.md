---
layout: post
title: Transition effects | TabNavigation | wpf | Syncfusion
description: transition effects
platform: wpf
control: TabNavigation
documentation: ug
---

# Transition effects

Transition Effect property is used to set the effect for the Tab navigation control. The Transition effect is an enum that contains five values namely:

* Slide – The item/page navigates with slide effect.

{% highlight xaml %}

<syncfusion:TabNavigationControl TransitionEffect="Slide" ItemsSource="{Binding MyCollection}">

</syncfusion:TabNavigationControl>

{% endhighlight %}

* Fade – During navigation, the previous item fades out and the new item appears with variation in opacity.

{% highlight xaml %}

<syncfusion:TabNavigationControl TransitionEffect="Fade" ItemsSource="{Binding MyCollection}">

</syncfusion:TabNavigationControl>

{% endhighlight %}

* Zoom – The new item appears with a zooming effect.

{% highlight xaml %}

<syncfusion:TabNavigationControl TransitionEffect="Zoom" ItemsSource="{Binding MyCollection}">

</syncfusion:TabNavigationControl>

{% endhighlight %}

* Blur – The new item appears with blur effect.

{% highlight xaml %}

 <syncfusion:TabNavigationControl TransitionEffect="Blur"  ItemsSource="{Binding MyCollection}">

 </syncfusion:TabNavigationControl>

{% endhighlight %}

* Push – The new item descends from the top 

{% highlight xaml %}

<syncfusion:TabNavigationControl TransitionEffect="Push" ItemsSource="{Binding MyCollection}">

</syncfusion:TabNavigationControl>

{% endhighlight %}

* PushIn – The new item ascends from the bottom

{% highlight xaml %}

<syncfusion:TabNavigationControl TransitionEffect="PushIn" ItemsSource="{Binding MyCollection}">

</syncfusion:TabNavigationControl>

{% endhighlight %}

* Wipe – The old item gets washed out and the new item appears.

{% highlight xaml %}

 <syncfusion:TabNavigationControl TransitionEffect="Wipe" ItemsSource="{Binding MyCollection}">

 </syncfusion:TabNavigationControl>

{% endhighlight %}