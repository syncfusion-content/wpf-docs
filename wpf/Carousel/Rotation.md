---
layout: post
title: Deals with Rotation Angle Support provided by Carousel control for WPF
description: Explains about Angle Support provided by Carousel control for WPF
platform: wpf
control: Carousel
documentation: ug
---

# RotationAngle Support

[RotationAngle](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.Carousel~RotationAngle.html) property of carousel enables the items in the control to be rotated at a user defined angle.

## Adding RotationAngle support to an Application

{% tabs %}

{% highlight Xaml %}

<syncfusion:Carousel  x:Name="Carousel"
VerticalAlignment="Center"
HorizontalAlignment="Center"
RotationAngle="45"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

Carousel carousel = new Carousel();

carousel.HorizontalAlignment = HorizontalAlignment.Center;

carousel.VerticalAlignment = VerticalAlignment.Center;

carousel.Name = "Carousel1";

carousel.RotationAngle = 45;

carousel.ItemsSource = new ObservableCollection<string>() { "Item1", "Item2", "Item3", "Item4", "Item5", "Item6", "Item7", "Item8", "Item9" };

grid1.Children.Add(carousel);

{% endhighlight %}

{% highlight VB %}

Dim carousel As New Carousel()

carousel.HorizontalAlignment = HorizontalAlignment.Center

carousel.VerticalAlignment = VerticalAlignment.Center

carousel.Name = "Carousel1"

carousel.RotationAngle = 45

carousel.ItemsSource = New ObservableCollection(Of String)() From { _
	"Item1", _
	"Item2", _
	"Item3", _
	"Item4", _
	"Item5", _
	"Item6", _
	"Item7", _
	"Item8", _
	"Item9" _
}

grid1.Children.Add(carousel)

{% endhighlight %}

{% endtabs %}

![Carousel rotation](Rotation-images/Rotation-Angle_img1.jpeg)


# RotationSpeed Support

[RotationSpeed](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.Carousel~RotationSpeed.html)  property of Carousel enables the items in the control to be rotated at a user defined speed.

## Adding RotationSpeed support to an Application

{% tabs %}

{% highlight XAML %}

<syncfusion:Carousel  x:Name="Carousel"
VerticalAlignment="Center"
HorizontalAlignment="Center"
RotationSpeed="100"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

Carousel carousel = new Carousel();

carousel.HorizontalAlignment = HorizontalAlignment.Center;

carousel.VerticalAlignment = VerticalAlignment.Center;

carousel.Name = "Carousel1";

carousel.RotationSpeed = 100;

carousel.ItemsSource = new ObservableCollection<string>() { "Item1", "Item2", "Item3", "Item4", "Item5", "Item6", "Item7", "Item8", "Item9" };

grid1.Children.Add(carousel);

{% endhighlight %}

{% highlight VB %}

Dim carousel As New Carousel()

carousel.HorizontalAlignment = HorizontalAlignment.Center

carousel.VerticalAlignment = VerticalAlignment.Center

carousel.Name = "Carousel1"

carousel.RotationSpeed = 100

carousel.ItemsSource = New ObservableCollection(Of String)() From { _
	"Item1", _
	"Item2", _
	"Item3", _
	"Item4", _
	"Item5", _
	"Item6", _
	"Item7", _
	"Item8", _
	"Item9" _
}

grid1.Children.Add(carousel)

{% endhighlight %}

{% endtabs %}


# Rotation Animation 

[EnableRotationAnimation](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.Carousel~EnableRotationAnimation.html) property will enable or disable the Rotation Animation behavior of CarouselItems.

{% tabs %}

{% highlight XAML %}

<syncfusion:Carousel x:Name="carousel" EnableRotationAnimation="False">

<syncfusion:CarouselItem Content="Item1" x:Name="item1"/>

<syncfusion:CarouselItem Content="Item2" x:Name="item2"/>

<syncfusion:CarouselItem Content="Item3" x:Name="item3"/>

<syncfusion:CarouselItem Content="Item4" x:Name="item4"/>

<syncfusion:CarouselItem Content="Item5" x:Name="item5"/>

</syncfusion:Carousel>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

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


# Touch support

Carousel provides Touch UI which is easy to perform the rotation of CarouselItems.  

## How to enable Touch support in Carousel 

To enable Touch Support in Carousel, set [EnableTouch](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.Carousel~EnableTouch.html) property as true. When the property is false, we need to touch exactly on the item to rotate. By default its value is false. 

{% tabs %}

{% highlight XAML %}

<syncfusion:Carousel x:Name="carousel" EnableTouch="True">
            <syncfusion:CarouselItem Content="Item1" x:Name="item1"/>
            <syncfusion:CarouselItem Content="Item2" x:Name="item2"/>
            <syncfusion:CarouselItem Content="Item3" x:Name="item3"/>
            <syncfusion:CarouselItem Content="Item4" x:Name="item4"/>
            <syncfusion:CarouselItem Content="Item5" x:Name="item5"/>
        </syncfusion:Carousel>

{% endhighlight %}

{% endtabs %}