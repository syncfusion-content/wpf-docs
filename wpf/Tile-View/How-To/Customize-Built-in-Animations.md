---
layout: post
title: How to Customize Built-in Animations in WPF Tile View | Syncfusion®
description: Customize the built-in animations of the Syncfusion WPF Tile View (TileViewControl) by overriding the default animation styles and timing.
platform: wpf
control: TileView Control
documentation: ug
---

# How to Customize Built-in Animations in WPF Tile View Control

## Enable or Disable built-in animation

The WPF Tile View Control allows built-in animations to be enabled or disabled using the `EnableAnimation` property. By default, this property is set to true. To disable animations, set `EnableAnimation` to false.

{% tabs %}

{% highlight XAML %}

<syncfusion:TileViewControl x:Name="tileview"  EnableAnimation="False"/>

{% endhighlight %}

{% highlight C# %}

tileview.EnableAnimation = false;

{% endhighlight %}

{% endtabs %}

## Animation Duration

`WPF Tile View Control` allows to customize the animation speed by the help of `AnimationDuration` property. By default, `AnimationDuration` value is 700 milliseconds.


{% tabs %}

{% highlight XAML %}

<syncfusion:TileViewControl x:Name="tileview"  AnimationDuration="00:00:00.700" />

{% endhighlight %}

{% highlight C# %}

tileview.AnimationDuration = new TimeSpan(0, 0, 0, 0, 700);

{% endhighlight %}

{% endtabs %}

