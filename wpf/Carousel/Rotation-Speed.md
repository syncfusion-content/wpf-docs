---
layout: post
title: Deals with Rotation Speed Support provided by Carousel control for WPF
description: Explains about Angle Support provided by Carousel control for WPF
platform: wpf
control: Carousel
documentation: ug
---

# RotationSpeed Support

**RotationSpeed**  property of Carousel enables the items in the control to be rotated at a user defined speed.

## Adding RotationSpeed support to an Application

{% tabs %}

{% highlight Xaml %}

<syncfusion:Carousel  x:Name="Carousel"
VerticalAlignment="Center"
HorizontalAlignment="Center"
RotationSpeed="100"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C#}

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

