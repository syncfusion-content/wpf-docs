---
layout: post
title: Deals with Path Support provided by Carousel control for WPF
description: Explains about Path Support provided by Carousel control for WPF
platform: wpf
control: Carousel
documentation: ug
---

# Path Support

Carousel panel arrange its children on a path. User can specify any path and it can be created easily using expression blend.

## Adding Path support to an Application

### VisualMode

In our carousel control, we can set the path using the two different modes of VisualMode property.To use the standard path, the VisualMode property need to set as Standard.And to set the custom path, use VisualMode as **CustomPath** along with **Path** Property of Carousel control. By default, the VisualMode value is Standard for carousel control. The same has been explained in the below code example.

###VisualMode Standard


{% tabs %}

{% highlight Xaml %}

<syncfusion:Carousel x:Name="carousel"
VisualMode="Standard"
VerticalAlignment="Center"
HorizontalAlignment="Center"
ItemsPerPage="5"
RadiusX="250" Height="257" Width="558" SelectedIndex="4">
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

![](Path-Support_images/StandardVisualMode.jpeg)

###VisualMode as CustomPath

{% tabs %}

{% highlight Xaml %}

<syncfusion:Carousel x:Name="carousel"   

VisualMode="CustomPath"

VerticalAlignment="Top"

ItemsPerPage="5"

RadiusX="250" Height="257" Width="558" SelectedIndex="4">

<syncfusion:Carousel.Path>

<Path Data="M0,300 L600,300" Stroke="Blue" StrokeThickness="2" HorizontalAlignment="Stretch" VerticalAlignment="Stretch"/>

</syncfusion:Carousel.Path>

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

![](Path-Support_images/CustomVisualMode.jpeg)


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
Path<br/><br/></td><td>
Sets the CustomPath for the Carousel control<br/><br/></td><td>
DependencyProperty<br/><br/></td><td>
CustomEditorCollection<br/><br/></td></tr>
</table>
