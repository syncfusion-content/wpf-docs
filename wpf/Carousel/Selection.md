---
layout: post
title: SelectedItem 
description: Explains about SelectedItem support in Carousel
platform: wpf
control: Carousel
documentation: ug
---

# SelectedItem

SelectedItem is a property in the Carousel that stores the currently selected CarouselItem. 

{% tabs %}

{% highlight Xaml %}

<syncfusion:Carousel x:Name="carousel">
            <syncfusion:CarouselItem Content="Item1" x:Name="item1"/>
            <syncfusion:CarouselItem Content="Item2" x:Name="item2"/>
            <syncfusion:CarouselItem Content="Item3" x:Name="item3"/>
            <syncfusion:CarouselItem Content="Item4" x:Name="item4"/>
            <syncfusion:CarouselItem Content="Item5" x:Name="item5"/>
        </syncfusion:Carousel>

{% endhighlight %}

{% highlight C# %}

Carousel carousel = new Carousel();
carousel.Items.Add(new CarouselItem() { Content = "1", Name="item1" });
carousel.Items.Add(new CarouselItem() { Content = "2", Name = "item2" });
carousel.Items.Add(new CarouselItem() { Content = "3", Name = "item3" });
carousel.Items.Add(new CarouselItem() { Content = "4", Name = "item4" });
carousel.Items.Add(new CarouselItem() { Content = "5", Name = "item5" });

carousel.SelectedItem = item3;

{% endhighlight %}

{% highlight VB %}

Dim carousel As Carousel = New Carousel
carousel.Items.Add(New CarouselItem)
carousel.Items.Add(New CarouselItem)
carousel.Items.Add(New CarouselItem)
carousel.Items.Add(New CarouselItem)
carousel.Items.Add(New CarouselItem)

carousel.SelectedItem = item3

{% endhighlight %}

{% endtabs %}


# Carousel Events

List of `Carousel` events are given in the following sections.

<table>
<tr>
<th>
Carousel Events<br/><br/></th><th>
Description<br/><br/></th></tr>
<tr>
<td>
SelectionChanged<br/><br/></td><td>
SelectionChanged event will fire when the value of the SelectedItem of the Carousel control is changed.<br/><br/></td></tr>
<tr>
<td>
SelectedValueChanged<br/><br/></td><td>
SelectedValueChanged event will fire when the selected value of the Carousel is changed<br/><br/></td></tr>
<tr>
<td>
SelectedIndexChanged<br/><br/></td><td>
SelectedIndexChanged event will fire when the selected index of the Carousel is changed<br/><br/></td></tr>
</table>


# IsSelected 

IsSelected is a Boolean property in the CarouselItem which is used to select a particular CarouselItem. 


{% tabs %}

{% highlight XAML %}

<syncfusion:Carousel x:Name="carousel">

<syncfusion:Carousel.ItemContainerStyle>

<Style TargetType="syncfusion:CarouselItem">

<Style.Triggers>

<Trigger Property="IsSelected" Value="True">

<Setter Property="FontWeight" Value="Bold">

</Setter>

</Trigger>

</Style.Triggers>

</Style>

</syncfusion:Carousel.ItemContainerStyle>

<syncfusion:CarouselItem Content="Item1" x:Name="item1"/>

<syncfusion:CarouselItem Content="Item2" x:Name="item2"/>

<syncfusion:CarouselItem Content="Item3" x:Name="item3"/>

<syncfusion:CarouselItem Content="Item4" x:Name="item4"/>

<syncfusion:CarouselItem Content="Item5" x:Name="item5" IsSelected="True"/>

</syncfusion:Carousel>


{% endhighlight %}

{% endtabs %}

![](Selection-images/IsSelectedproperty.png)



