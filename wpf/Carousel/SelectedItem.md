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

{% highlight xaml %}

<syncfusion:Carousel x:Name="carousel">
            <syncfusion:CarouselItem Content="Item1" x:Name="item1"/>
            <syncfusion:CarouselItem Content="Item2" x:Name="item2"/>
            <syncfusion:CarouselItem Content="Item3" x:Name="item3"/>
            <syncfusion:CarouselItem Content="Item4" x:Name="item4"/>
            <syncfusion:CarouselItem Content="Item5" x:Name="item5"/>
        </syncfusion:Carousel>

{% endhighlight %}

{% highlight c# %}

carousel.SelectedItem = item3;

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
SelectionChanged event<br/><br/></td><td>
SelectionChanged event will fire when the value of the SelectedItem of the Carousel control is changed.<br/><br/></td></tr>
<tr>
<td>
SelectedValueChanged event<br/><br/></td><td>
SelectedValueChanged event will fire when the selected value of the Carousel is changed<br/><br/></td></tr>
<tr>
<td>
SelectedIndexChanged<br/><br/></td><td>
SelectedIndexChanged event will fire when the selected index of the Carousel is changed<br/><br/></td></tr>
</table>


