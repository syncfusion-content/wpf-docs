---
layout: post
title: Customize Built-in Animations | TileView | wpf | Syncfusion
description: Customize built-in animations in Syncfusion Essential Studio WPF TileView Control, its elements and more.
platform: wpf
control: TileView Control
documentation: ug
---

# Customize Built-in Animations

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

