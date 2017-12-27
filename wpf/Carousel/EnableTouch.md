---
layout: post
title: Touch support provided by Carousel control for WPF 
description: Explains about Touch support in Carousel
platform: wpf
control: Carousel
documentation: ug
---

# Touch support

Carousel provides Touch UI which is easy to perform the rotation of CarouselItems.  

## How to enable Touch support in Carousel 

To enable Touch Support in Carousel, set `EnableTouch` property as true. When the property is false, we need to touch exactly on the item to rotate. By default its value is false. 

{% tabs %}

{% highlight xaml %}

<syncfusion:Carousel x:Name="carousel" EnableTouch="True">
            <syncfusion:CarouselItem Content="Item1" x:Name="item1"/>
            <syncfusion:CarouselItem Content="Item2" x:Name="item2"/>
            <syncfusion:CarouselItem Content="Item3" x:Name="item3"/>
            <syncfusion:CarouselItem Content="Item4" x:Name="item4"/>
            <syncfusion:CarouselItem Content="Item5" x:Name="item5"/>
        </syncfusion:Carousel>

{% endhighlight %}

{% endtabs %}




