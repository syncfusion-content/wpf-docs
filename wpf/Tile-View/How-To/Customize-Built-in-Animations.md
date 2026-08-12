---
layout: post
title: How to Customize Built-in Animations in WPF Tile View | Syncfusion®
description: Customize the built-in animations of the Syncfusion WPF Tile View (TileViewControl) by overriding the default animation styles and timing.
platform: wpf
control: TileView Control
documentation: ug
---

# How to Customize Built-in Animations in WPF Tile View

## Enable or Disable built-in animation

TileViewControl allows to enable or disable the built-in animation by the help of `EnableAnimation` property. By default, EnableAnimation value as true. To disable TileViewControl animation, set EnableAnimation property of TileViewControl as false.


{% tabs %}

{% highlight XAML %}

<syncfusion:TileViewControl x:Name="tileview"  EnableAnimation="False"/>

{% endhighlight %}

{% highlight C# %}

tileview.EnableAnimation = false;

{% endhighlight %}

{% endtabs %}

## Animation Duration

`TileViewControl` allows to customize the animation speed by the help of `AnimationDuration` property. By default, `AnimationDuration` value is 700 milliseconds.


{% tabs %}

{% highlight XAML %}

<syncfusion:TileViewControl x:Name="tileview"  AnimationDuration="00:00:00.700" />

{% endhighlight %}

{% highlight C# %}

tileview.AnimationDuration = new TimeSpan(0, 0, 0, 0, 700);

{% endhighlight %}

{% endtabs %}

