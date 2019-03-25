---
layout: post
title: ItemsPerPage support provided by Carousel control for WPF
description: ItemsPerPage support provided by Carousel control for WPF
platform: wpf
control: Carousel
documentation: ug
---

# ItemsPerPage Support

To get or set the number of items to be displayed in the Carousel control, use [ItemsPerPage](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.Carousel~ItemsPerPage.html) property. Carousel panel displays only items for the currently visible items

## Using ItemsPerPage in an Application

In the below sample, [ItemsPerPage](https://help.syncfusion.com/cr/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.Carousel~ItemsPerPage.html) is set as **5**. Hence, while running the sample, only 5 items will be displayed in the path.

{% tabs %}

{% highlight Xaml %}

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

{% endtabs %}

{% tabs %}

{% highlight C# %}

carousel.ItemsSource = new ObservableCollection<string>() { "Item1", "Item2", "Item3", "Item4", "Item5", "Item6", "Item7", "Item8", "Item9" };


{% endhighlight %}

{% highlight VB %}

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

{% endhighlight %}

{% endtabs %}

![Carousel item support](ItemsPerPage-Support_images/ItemsPerPage-Support_img1.jpeg)
