---
layout: post
title: Data-Binding
description: data binding
platform: wpf
control: Carousel
documentation: ug
---

# Data Binding

Carousel is a fully data bound control, supports binding to different data sources such as IList Data Source, XML Data Source, Observable Collection Data Source and WCF Services. 

## Using Data Binding in an Application

To bind a collection to Carousel, use the ItemsSource property. 

You can create Rich Interface Applications by defining DataTemplate to a Carousel control.

The following code tells about Data Binding and DataTemplate.

{% highlight xml %}

<table>
<tr>
<td>
[XAML]<syncfusion:Carousel x:Name="carousel" Height="400" Width="450"><br>    <syncfusion:Carousel.Path><br>        <Path Data="M0,300 L600,300" Stroke="Blue" StrokeThickness="2" HorizontalAlignment="Stretch" VerticalAlignment="Stretch"/><br>    </syncfusion:Carousel.Path><br>    <syncfusion:Carousel.OpacityFractions><br>        <syncfusion:PathFractionCollection><br>            <syncfusion:FractionValue Fraction="0" Value="1"/><br>        </syncfusion:PathFractionCollection><br>    </syncfusion:Carousel.OpacityFractions><br>    <syncfusion:Carousel.ItemTemplate><br>        <DataTemplate><br>            <Border Height="100" Width="100"><br>                <Border.Background><br>                    <LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0"><br>                        <GradientStop Color="#FF8B8B8B" Offset="0"/><br>                        <GradientStop Color="#FFDADADA" Offset="1"/><br>                        <GradientStop Color="#FFF3F3F3" Offset="0.536"/><br>                    </LinearGradientBrush><br>                </Border.Background><br>                <ContentControl Content="{Binding}" HorizontalAlignment="Center" VerticalAlignment="Center"/><br>            </Border><br>        </DataTemplate><br>    </syncfusion:Carousel.ItemTemplate><br></syncfusion:Carousel></td></tr>
<tr>
<td>
[C#]carousel.ItemsSource = new ObservableCollection<string>() { "Item1", "Item2", "Item3", "Item4", "Item5", "Item6", "Item7", "Item8", "Item9" };</td></tr>
</table>

{% endhighlight %}

![](Data-Binding_images/Data-Binding_img1.png)



