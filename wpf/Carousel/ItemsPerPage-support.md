---
layout: post
title: ItemsPerPage support provided by Carousel control for WPF
description: ItemsPerPage support provided by Carousel control for WPF
platform: wpf
control: Carousel
documentation: ug
---

# ItemsPerPage Support

To get or set the number of items to be displayed in the Carousel control, use **ItemsPerPage** property. Carousel panel displays only items for the currently visible items

## Using ItemsPerPage in an Application

In the below sample, ItemsPerPage is set as **5**. Hence, while running the sample, only 5 items will be displayed in the path.

{% highlight xaml %}
<syncfusion:Carousel x:Name="carousel" VisualMode="CustomPath"  Height="257" Width="558" ItemsPerPage="5">

<syncfusion:Carousel.OpacityFractions>

<syncfusion:PathFractionCollection>

<syncfusion:FractionValue Fraction="0" Value="1"/>

</syncfusion:PathFractionCollection>

</syncfusion:Carousel.OpacityFractions>

<syncfusion:Carousel.ItemTemplate>

<DataTemplate>

<Border Height="100" Width="100" Background="LightBlue">

<ContentControl Content="{Binding}" HorizontalAlignment="Center" VerticalAlignment="Center"/>

</Border>

</DataTemplate>

</syncfusion:Carousel.ItemTemplate>

</syncfusion:Carousel>



{% endhighlight %}

{% highlight c# %}

carousel.ItemsSource = new ObservableCollection<string>() { "Item1", "Item2", "Item3", "Item4", "Item5", "Item6", "Item7", "Item8", "Item9" };


{% endhighlight %}

![](ItemsPerPage-Support_images/ItemsPerPage-Support_img1.jpeg)


## Properties

<table>
<tr>
<td>
Property<br/><br/></td><td>
Description<br/><br/></td><td>
Type<br/><br/></td><td>
Data Type<br/><br/></td></tr>
<tr>
<td>
ItemsPerPage<br/><br/></td><td>
Gets or sets the number of items to be displayed in the Carousel control.<br/><br/></td><td>
DependencyProperty<br/><br/></td><td>
Integer<br/><br/></td></tr>
</table>
