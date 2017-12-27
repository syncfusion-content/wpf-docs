---
layout: post
title: Rotation Animation support provided by Carousel control for WPF
description: Explains about Rotation Animation Support provided by Carousel control for WPF
platform: wpf
control: Carousel
documentation: ug
---

# Rotation Animation 

**EnableRotationAnimation** property will enable or disable the Rotation Animation behavior of CarouselItems.

{% tabs %}

{% highlight Xaml %}

<syncfusion:Carousel x:Name="carousel" EnableRotationAnimation="False">

<syncfusion:CarouselItem Content="Item1" x:Name="item1"/>

<syncfusion:CarouselItem Content="Item2" x:Name="item2"/>

<syncfusion:CarouselItem Content="Item3" x:Name="item3"/>

<syncfusion:CarouselItem Content="Item4" x:Name="item4"/>

<syncfusion:CarouselItem Content="Item5" x:Name="item5"/>

</syncfusion:Carousel>

{% endhighlight %}

{% tabs %}

{% tabs %}

{% highlight c# %}

Carousel carousel = new Carousel();

carousel.EnableRotationAnimation = false;

carousel.Items.Add(new CarouselItem() { Content = "Item1" });

carousel.Items.Add(new CarouselItem() { Content = "Item2" });

carousel.Items.Add(new CarouselItem() { Content = "Item3" });

carousel.Items.Add(new CarouselItem() { Content = "Item4" });

carousel.Items.Add(new CarouselItem() { Content = "Item5" });

grid1.Children.Add(carousel);


{% endhighlight %}

{% endtabs %}