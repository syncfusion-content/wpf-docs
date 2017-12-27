---
layout: post
title: CarouselItem properties 
description: Explains about the properties in CarouselItem
platform: wpf
control: Carousel
documentation: ug
---

# IsSelected 

IsSelected is a Boolean property in the CarouselItem which is used to select a particular CarouselItem. 


{% tabs %}

{% highlight xml %}

<syncfusion:Carousel x:Name="carousel">

<syncfusion:Carousel.ItemContainerStyle>

<Style TargetType="syncfusion:CarouselItem">

<Style.Triggers>

<Trigger Property="IsSelected" Value="True">

<Setter Property="FontWeight" Value="Bold">

</Setter>

</Trigger>

</Style.Triggers>

</Style>

</syncfusion:Carousel.ItemContainerStyle>

<syncfusion:CarouselItem Content="Item1" x:Name="item1"/>

<syncfusion:CarouselItem Content="Item2" x:Name="item2"/>

<syncfusion:CarouselItem Content="Item3" x:Name="item3"/>

<syncfusion:CarouselItem Content="Item4" x:Name="item4"/>

<syncfusion:CarouselItem Content="Item5" x:Name="item5" IsSelected="True"/>

</syncfusion:Carousel>


{% endhighlight %}

{% endtabs %}

![](CarouselItem-properties-images/IsSelectedproperty.png)



