---
layout: post
title: Scaling Opacity and Skewing Support provided by carousel control for WPF
description: Scaling Opacity and Skewing Support provided by carousel control for WPF
platform: wpf
control: Carousel
documentation: ug
---
# Scaling Opacity and Skewing Support

User can control Scaling, Opacity and Skewing for CarouselItem’s using **ScaleFractions**, **OpacityFractions** and **SkewAngleXFractions**, **SkewAngleYFractions** properties. 


Using **TopItemPosition** property, they can change the position of SelectedItem in a given path.

## Adding Scaling, Opacity and Skewing Support to an Application

To enable or disable this feature, use **OpacityEnabled**, **ScalingEnabled**, **SkewXEnabled**, **SkewYEnabled** properties.

The following code illustrates the usage of these properties.

{% tabs %}

{% highlight Xaml %}

<syncfusion:Carousel x:Name="carousel" VisualMode="CustomPath"  VerticalAlignment="Top"  Height="257" Width="558" ItemsPerPage="5" OpacityEnabled="True" ScalingEnabled="True" >

<syncfusion:Carousel.Path>

<Path Data="M0,300 L600,300" Stroke="Blue" StrokeThickness="2" HorizontalAlignment="Stretch" VerticalAlignment="Stretch"/>

</syncfusion:Carousel.Path>

<syncfusion:Carousel.OpacityFractions>

<syncfusion:PathFractionCollection>

<!--Fraction represents the position in Path- Value represents the Opacity of Carousel item in a particular point-->

<syncfusion:FractionValue Fraction="0" Value="1"/>

<syncfusion:FractionValue Fraction="1" Value="0.5"/>

</syncfusion:PathFractionCollection>

</syncfusion:Carousel.OpacityFractions>

<syncfusion:Carousel.ScaleFractions>

<syncfusion:PathFractionCollection>

<syncfusion:FractionValue Fraction="0" Value="1"/>

<syncfusion:FractionValue Fraction="1" Value="0.5"/>

</syncfusion:PathFractionCollection>

</syncfusion:Carousel.ScaleFractions>

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

![](Scaling-Opacity-and-Skewing-Support_images/Scaling-Opacity-and-Skewing-Support_img1.jpeg)


### Properties

<table>
<tr>
<td>
Property<br/><br/></td><td>
Description<br/><br/></td><td>
Type<br/><br/></td><td>
Data Type<br/><br/></td></tr>
<tr>
<td>
OpacityEnabled<br/><br/></td><td>
Enables or disables the Opacity support in Carousel.<br/><br/></td><td>
DependencyProperty<br/><br/></td><td>
Bool<br/><br/></td></tr>
<tr>
<td>
ScalingEnabled<br/><br/></td><td>
Enables or disables the Scaling support in Carousel.<br/><br/></td><td>
DependencyProperty<br/><br/></td><td>
Bool<br/><br/></td></tr>
<tr>
<td>
SkewAngleXEnabled<br/><br/></td><td>
Enables or disables the SkewAngleX support in Carousel.<br/><br/></td><td>
DependencyProperty<br/><br/></td><td>
Bool<br/><br/></td></tr>
<tr>
<td>
SkewAngleYEnabled<br/><br/></td><td>
Enables or disables the SkewAngleY support in Carousel.<br/><br/></td><td>
DependencyProperty<br/><br/></td><td>
Bool<br/><br/></td></tr>
<tr>
<td>
OpacityFractions<br/><br/></td><td>
Sets the Opacity Value for CarouselItem in the Path.<br/><br/></td><td>
DependencyProperty<br/><br/></td><td>
PathFractionCollection<br/><br/></td></tr>
<tr>
<td>
ScalingFractions<br/><br/></td><td>
Sets the Scale Value for CarouselItem in the Path.<br/><br/></td><td>
DependencyProperty<br/><br/></td><td>
PathFractionCollection<br/><br/></td></tr>
<tr>
<td>
SkewAngleXFraction<br/><br/></td><td>
Sets the SkewAngleX Value for CarouselItem in the Path.<br/><br/></td><td>
DependencyProperty<br/><br/></td><td>
PathFractionCollection<br/><br/></td></tr>
<tr>
<td>
SkewAngleYFractions<br/><br/></td><td>
Sets the SkewAngleY Value for CarouselItem in the Path.<br/><br/></td><td>
DependencyProperty<br/><br/></td><td>
PathFractionCollection<br/><br/></td></tr>
</table>
