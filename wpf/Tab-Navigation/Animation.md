---
layout: post
title: Animation in WPF Tab Navigation control | Syncfusion
description: Learn about Animation support in Syncfusion Essential Studio WPF Tab Navigation control, its elements and more.
platform: wpf
control: TabNavigation
documentation: ug
---

# Animation in WPF Tab Navigation

Transition Effect property is used to set the animation effect for the tab navigation control. The Transition effect is an enum that contains five values namely:

* Slide – The item/page navigates with slide effect.

{% capture codesnippet1 %}
{% tabs %}
{% highlight xaml %}

<syncfusion:TabNavigationControl TransitionEffect="Slide" ItemsSource="{Binding MyCollection}">
</syncfusion:TabNavigationControl>

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet1 | OrderList_Indent_Level_1 }}

* Fade – During navigation, the previous item fades out and the new item appears with variation in opacity.

{% capture codesnippet2 %}
{% tabs %}
{% highlight xaml %}

<syncfusion:TabNavigationControl TransitionEffect="Fade" ItemsSource="{Binding MyCollection}">
</syncfusion:TabNavigationControl>

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet2 | OrderList_Indent_Level_1 }}

* Zoom – The new item appears with a zooming effect.

{% capture codesnippet3 %}
{% tabs %}
{% highlight xaml %}

<syncfusion:TabNavigationControl TransitionEffect="Zoom" ItemsSource="{Binding MyCollection}">
</syncfusion:TabNavigationControl>

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet3 | OrderList_Indent_Level_1 }}

* Blur – The new item appears with blur effect.

{% capture codesnippet4 %}
{% tabs %}
{% highlight xaml %}

 <syncfusion:TabNavigationControl TransitionEffect="Blur"  ItemsSource="{Binding MyCollection}">
 </syncfusion:TabNavigationControl>

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet4 | OrderList_Indent_Level_1 }}

* Push – The new item descends from the top 

{% capture codesnippet5 %}
{% tabs %}
{% highlight xaml %}

<syncfusion:TabNavigationControl TransitionEffect="Push" ItemsSource="{Binding MyCollection}">
</syncfusion:TabNavigationControl>

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet5 | OrderList_Indent_Level_1 }}

* PushIn – The new item ascends from the bottom

{% capture codesnippet6 %}
{% tabs %}
{% highlight xaml %}

<syncfusion:TabNavigationControl TransitionEffect="PushIn" ItemsSource="{Binding MyCollection}">
</syncfusion:TabNavigationControl>

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet6 | OrderList_Indent_Level_1 }}

* Wipe – The old item gets washed out and the new item appears.

{% capture codesnippet7 %}
{% tabs %}
{% highlight xaml %}

 <syncfusion:TabNavigationControl TransitionEffect="Wipe" ItemsSource="{Binding MyCollection}">
 </syncfusion:TabNavigationControl>

{% endhighlight %}
{% endtabs %}
{% endcapture %}
{{ codesnippet7 | OrderList_Indent_Level_1 }}
