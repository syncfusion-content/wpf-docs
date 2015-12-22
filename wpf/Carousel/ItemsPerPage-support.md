---
layout: post
title: ItemsPerPage support | Carousel | wpf | Syncfusion
description: itemsperpage support
platform: wpf
control: Carousel
documentation: ug
---

# ItemsPerPage support

Using ItemsPerPage property, you can get or set the number of items to be displayed in the Carousel control. Carousel panel displays only items for the currently visible items.

## Using ItemsPerPage in an Application

In the below sample, ItemsPerPage is set as 5. Hence, while running the sample, only 5 items will be displayed in the path.

{% highlight xml %}

<syncfusion:Carousel x:Name="carousel" Height="400" Width="450" ItemsPerPage="5"><br>    <syncfusion:Carousel.Path><br>        <Path Data="M0,300 L600,300" Stroke="Blue" StrokeThickness="2" HorizontalAlignment="Stretch" VerticalAlignment="Stretch"/><br>    </syncfusion:Carousel.Path><br>    <syncfusion:Carousel.OpacityFractions><br>        <syncfusion:PathFractionCollection><br>            <syncfusion:FractionValue Fraction="0" Value="1"/><br>        </syncfusion:PathFractionCollection><br>    </syncfusion:Carousel.OpacityFractions><br>    <syncfusion:Carousel.ItemTemplate><br>        <DataTemplate><br>            <Border Height="100" Width="100"><br>                <Border.Background><br>                    <LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0"><br>                        <GradientStop Color="#FF8B8B8B" Offset="0"/><br>                        <GradientStop Color="#FFDADADA" Offset="1"/><br>                        <GradientStop Color="#FFF3F3F3" Offset="0.536"/><br>                    </LinearGradientBrush><br>                </Border.Background><br>                <ContentControl Content="{Binding}" HorizontalAlignment="Center" VerticalAlignment="Center"/><br>            </Border><br>        </DataTemplate><br>    </syncfusion:Carousel.ItemTemplate><br></syncfusion:Carousel></td></tr>
{% endhighlight  %}
{% highlight c# %}
carousel.ItemsSource = new ObservableCollection<string>() { "Item1", "Item2", "Item3", "Item4", "Item5", "Item6", "Item7", "Item8", "Item9" };</td></tr>


{% endhighlight %}


![](ItemsPerPage-support_images/ItemsPerPage-support_img1.png)


## Properties


<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th><th>
Reference links </th></tr>
<tr>
<td>
ItemsPerPage</td><td>
Gets or sets the number of items to be displayed in the Carousel control.</td><td>
DependencyProperty</td><td>
Integer</td><td>
</td></tr>
</table>


