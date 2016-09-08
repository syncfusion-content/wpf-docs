---
layout: post
title: Getting Started documentation of Carousel control for WPF
description: getting started documentation of Carousel control for WPF
platform: wpf
control: Carousel
documentation: ug
---

# Getting Started

## Structure of the Carousel Control

![](Getting-Started_images/Getting-Started_img1.jpeg)


##   Adding carousel to an application

The Carousel control can be added to an application by using Visual Studio and Blend.

###     Creating Carousel control using XAML


Follow the below steps to add Carousel by using Visual Studio in XAML.

1. Create a new application in Visual Studio.

2. In the Visual Studio Toolbox, click Syncfusion Toolbox tab and select Carousel.

3. Drag and Drop the Carousel to design view, in order to add the Carousel control to your application.

4. In the properties window, customize the properties of the Carousel.

![](Getting-Started_images/Getting-Started_img2.jpeg)


The below code shows how Carousel can be added to an application by using Visual Studio in XAML

{% tabs %}

{% highlight Xaml %}

<syncfusion:Carousel x:Name="carousel" Height="400" Width="450">        

<syncfusion:CarouselItem>

<syncfusion:CarouselItem.Content>

<Viewbox Height="100" Width="100">

<Image Source="/Images/1.jpg"/>

</Viewbox>

</syncfusion:CarouselItem.Content>

</syncfusion:CarouselItem>

<syncfusion:CarouselItem>

<syncfusion:CarouselItem.Content>

<Viewbox Height="100" Width="100">

<Image Source="/Images/2.jpg"/>

</Viewbox>

</syncfusion:CarouselItem.Content>

</syncfusion:CarouselItem>

<syncfusion:CarouselItem>

<syncfusion:CarouselItem.Content>

<Viewbox Height="100" Width="100">

<Image Source="/Images/3.jpg"/>

</Viewbox>

</syncfusion:CarouselItem.Content>

</syncfusion:CarouselItem>

<syncfusion:CarouselItem>

<syncfusion:CarouselItem.Content>

<Viewbox Height="100" Width="100">

<Image Source="/Images/4.jpg"/>

</Viewbox>

</syncfusion:CarouselItem.Content>

</syncfusion:CarouselItem>

<syncfusion:CarouselItem>

<syncfusion:CarouselItem.Content>

<Viewbox Height="100" Width="100">

<Image Source="/Images/5.jpg"/>

</Viewbox>

</syncfusion:CarouselItem.Content>

</syncfusion:CarouselItem>

<syncfusion:CarouselItem>

<syncfusion:CarouselItem.Content>

<Viewbox Height="100" Width="100">

<Image Source="/Images/6.jpg"/>

</Viewbox>

</syncfusion:CarouselItem.Content>

</syncfusion:CarouselItem>

<syncfusion:CarouselItem>

<syncfusion:CarouselItem.Content>

<Viewbox Height="100" Width="100">

<Image Source="/Images/7.jpg"/>

</Viewbox>

</syncfusion:CarouselItem.Content>

</syncfusion:CarouselItem>

<syncfusion:CarouselItem>

<syncfusion:CarouselItem.Content>

<Viewbox Height="100" Width="100">

<Image Source="/Images/8.jpg"/>

</Viewbox>

</syncfusion:CarouselItem.Content>

</syncfusion:CarouselItem>

</syncfusion:Carousel>

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/Getting-Started_img3.jpeg)


### Creating Carousel control using C#

The below code shows how the Carousel control can be added to an application in C#

{% tabs %}

{% highlight C# %}

Carousel carousel = new Carousel();
carousel.Items.Add(new CarouselItem(){Content="1"});
carousel.Items.Add(new CarouselItem(){Content="2"});
carousel.Items.Add(new CarouselItem(){Content="3"});
carousel.Items.Add(new CarouselItem(){Content="4"});
carousel.Items.Add(new CarouselItem(){Content="5"});
this.LayoutRoot.Children.Add(carousel);

{% endhighlight %}

{% highlight VB %}

Dim carousel As New Carousel()
carousel.Items.Add(New CarouselItem() With { _
	Key .Content = "1" _
})
carousel.Items.Add(New CarouselItem() With { _
	Key .Content = "2" _
})
carousel.Items.Add(New CarouselItem() With { _
	Key .Content = "3" _
})
carousel.Items.Add(New CarouselItem() With { _
	Key .Content = "4" _
})
carousel.Items.Add(New CarouselItem() With { _
	Key .Content = "5" _
})
Me.LayoutRoot.Children.Add(carousel)

{% endhighlight %}

{% endtabs %}


