---
layout: post
title: Radius support provided by Carousel control for WPF
description: Explains about Radius Support provided by Carousel control for WPF
platform: wpf
control: Carousel
documentation: ug
---

# Radius Support

**RadiusX** and **RadiusY** properties in the Carousel can be used to define the X and Y axis radius to render the control.

## Adding Radius support to an Application

{% tabs %}

{% highlight Xaml %}

<syncfusion:Carousel x:Name="carousel" RadiusX="200" RadiusY="200">
            
            <syncfusion:Carousel.ItemTemplate>

                <DataTemplate>

                    <Border Height="100" Width="100" Background="LightBlue">

                        <ContentControl Content="{Binding}" HorizontalAlignment="Center" VerticalAlignment="Center"/>

                    </Border>

                </DataTemplate>

            </syncfusion:Carousel.ItemTemplate>

        </syncfusion:Carousel>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C#%}

Carousel carousel = new Carousel();
carousel.RadiusX = 200;
carousel.RadiusY = 200;
carousel.ItemsSource = new ObservableCollection<string>() { "Item1", "Item2", "Item3", "Item4", "Item5", "Item6", "Item7", "Item8", "Item9" };
grid1.Children.Add(carousel);

{% endhighlight %}

{% highlight VB %}

Dim carousel As New Carousel()
carousel.RadiusX = 200
carousel.RadiusY = 200
carousel.ItemsSource = New ObservableCollection(Of String) (New String() {"Item1", "Item2", "Item3", "Item4", "Item5", "Item6", "Item7", "Item8", "Item9"})
grid1.Children.Add(carousel)

{% endhighlight %}

{% endtabs %}

![](Radius-support-images/radius-support-images.png)