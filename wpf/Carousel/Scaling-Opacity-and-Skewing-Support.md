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

# Opacity support

In our carousel control, when we set the property OpacityEnabled to true, the opacity for the control will set.

Please find the code snippet for the same:

{% tabs %}

{% highlight Xaml %}

<syncfusion:Carousel x:Name="Carousel" OpacityEnabled="True">
<syncfusion:Carousel.OpacityFractions>

<syncfusion:PathFractionCollection>

<!--Fraction represents the position in Path- Value represents the Opacity of Carousel item in a particular point-->

<syncfusion:FractionValue Fraction="0" Value="1"/>

<syncfusion:FractionValue Fraction="1" Value="0.5"/>

</syncfusion:PathFractionCollection>

</syncfusion:Carousel.OpacityFractions>
</syncfusion:Carousel>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

Carousel carousel = new Carousel() { Margin = new Thickness(4,4,4,4), RadiusX = 220, RadiusY = -100, ScaleFraction=0.60 };

PathFractionCollection patchfract = new PathFractionCollection();

FractionValue fractionvalue = new FractionValue() { Fraction = 0, Value=1 };

patchfract.Add(fractionvalue);

carousel.OpacityFraction = patchfract[0].Value;

carousel.ItemsSource = new ObservableCollection<string>() { "Item1", "Item2", "Item3", "Item4", "Item5", "Item6", "Item7", "Item8", "Item9" };

{% endhighlight %}

{% highlight VB %}

Dim carousel As Carousel = New Carousel
Dim patchfract As PathFractionCollection = New PathFractionCollection
Dim fractionvalue As FractionValue = New FractionValue
patchfract.Add(fractionvalue)
carousel.OpacityFraction = patchfract(0).Value

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

# Scaling feature

In our carousel control, the scaling for the carousel item would be set by using ScalingEnabled property. By default its property is false.
Please find the code snippet below:

{% tabs %}

{% highlight Xaml %}

<syncfusion:Carousel x:Name="Carousel" SkewAngleXEnabled="True" SkewAngleYEnabled="False">

<syncfusion:Carousel.SkewAngleXFractions>

<syncfusion:PathFractionCollection>

<syncfusion:FractionValue Fraction="0" Value="1"/>

<syncfusion:FractionValue Fraction="1" Value="0.5"/>

</syncfusion:PathFractionCollection>

</syncfusion:Carousel.SkewAngleXFractions>
</syncfusion:Carousel>


{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

Carousel carousel = new Carousel() { SkewAngleXEnabled = true, SkewAngleYEnabled = true };

PathFractionCollection patchfract = new PathFractionCollection();

FractionValue fractionvalue1 = new FractionValue() { Fraction = 0, Value=1 };

FractionValue fractionvalue2 = new FractionValue() { Fraction = 1, Value = 0.5 };

patchfract.Add(fractionvalue1);

patchfract.Add(fractionvalue2);

carousel.OpacityFractions.Add(patchfract[0]);

carousel.OpacityFractions.Add(patchfract[1]);

carousel.ItemsSource = new ObservableCollection<string>() { "Item1", "Item2", "Item3", "Item4", "Item5", "Item6", "Item7", "Item8", "Item9" };

{% endhighlight %}

{% highlight VB %}

Dim carousel As Carousel = New Carousel

carousel.SkewAngleYEnabled = true

carousel.SkewAngleXEnabled = true

Dim patchfract As PathFractionCollection = New PathFractionCollection

Dim fractionvalue1 As FractionValue = New FractionValue

Dim fractionvalue2 As FractionValue = New FractionValue

patchfract.Add(fractionvalue1)

patchfract.Add(fractionvalue2)

carousel.OpacityFractions.Add(patchfract(0))

carousel.OpacityFractions.Add(patchfract(1))

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
