---
layout: post
title: Animation | TabNavigation | WPF | Syncfusion
description: This section describes animation effects of tabnavigation control.
platform: wpf
control: TabNavigation
documentation: ug
---

# Animation

Transition Effect property is used to set the animation effect for the tab navigation control. The Transition effect is an enum that contains five values namely:

* Slide – The item/page navigates with slide effect.

{% tabs %}
{% highlight xaml %}

<syncfusion:TabNavigationControl TransitionEffect="Slide" ItemsSource="{Binding MyCollection}">
</syncfusion:TabNavigationControl>

{% endhighlight %}
{% endtabs %}

* Fade – During navigation, the previous item fades out and the new item appears with variation in opacity.

{% tabs %}
{% highlight xaml %}

<syncfusion:TabNavigationControl TransitionEffect="Fade" ItemsSource="{Binding MyCollection}">
</syncfusion:TabNavigationControl>

{% endhighlight %}
{% endtabs %}

* Zoom – The new item appears with a zooming effect.

{% tabs %}
{% highlight xaml %}

<syncfusion:TabNavigationControl TransitionEffect="Zoom" ItemsSource="{Binding MyCollection}">
</syncfusion:TabNavigationControl>

{% endhighlight %}
{% endtabs %}

* Blur – The new item appears with blur effect.

{% tabs %}
{% highlight xaml %}

 <syncfusion:TabNavigationControl TransitionEffect="Blur"  ItemsSource="{Binding MyCollection}">
 </syncfusion:TabNavigationControl>

{% endhighlight %}
{% endtabs %}

* Push – The new item descends from the top 

{% tabs %}
{% highlight xaml %}

<syncfusion:TabNavigationControl TransitionEffect="Push" ItemsSource="{Binding MyCollection}">
</syncfusion:TabNavigationControl>

{% endhighlight %}
{% endtabs %}

* PushIn – The new item ascends from the bottom

{% tabs %}
{% highlight xaml %}

<syncfusion:TabNavigationControl TransitionEffect="PushIn" ItemsSource="{Binding MyCollection}">
</syncfusion:TabNavigationControl>

{% endhighlight %}
{% endtabs %}

* Wipe – The old item gets washed out and the new item appears.

{% tabs %}
{% highlight xaml %}

 <syncfusion:TabNavigationControl TransitionEffect="Wipe" ItemsSource="{Binding MyCollection}">
 </syncfusion:TabNavigationControl>

{% endhighlight %}
{% endtabs %}
