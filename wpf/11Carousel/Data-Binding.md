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

Using Data Binding in an Application

To bind a collection to Carousel, use the ItemsSource property. 

You can create Rich Interface Applications by defining DataTemplate to a Carousel control.

The following code tells about Data Binding and DataTemplate.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:Carousel x:Name="carousel" Height="400" Width="450"&gt;<br>    &lt;syncfusion:Carousel.Path&gt;<br>        &lt;Path Data="M0,300 L600,300" Stroke="Blue" StrokeThickness="2" HorizontalAlignment="Stretch" VerticalAlignment="Stretch"/&gt;<br>    &lt;/syncfusion:Carousel.Path&gt;<br>    &lt;syncfusion:Carousel.OpacityFractions&gt;<br>        &lt;syncfusion:PathFractionCollection&gt;<br>            &lt;syncfusion:FractionValue Fraction="0" Value="1"/&gt;<br>        &lt;/syncfusion:PathFractionCollection&gt;<br>    &lt;/syncfusion:Carousel.OpacityFractions&gt;<br>    &lt;syncfusion:Carousel.ItemTemplate&gt;<br>        &lt;DataTemplate&gt;<br>            &lt;Border Height="100" Width="100"&gt;<br>                &lt;Border.Background&gt;<br>                    &lt;LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0"&gt;<br>                        &lt;GradientStop Color="#FF8B8B8B" Offset="0"/&gt;<br>                        &lt;GradientStop Color="#FFDADADA" Offset="1"/&gt;<br>                        &lt;GradientStop Color="#FFF3F3F3" Offset="0.536"/&gt;<br>                    &lt;/LinearGradientBrush&gt;<br>                &lt;/Border.Background&gt;<br>                &lt;ContentControl Content="{Binding}" HorizontalAlignment="Center" VerticalAlignment="Center"/&gt;<br>            &lt;/Border&gt;<br>        &lt;/DataTemplate&gt;<br>    &lt;/syncfusion:Carousel.ItemTemplate&gt;<br>&lt;/syncfusion:Carousel&gt;</td></tr>
<tr>
<td>
[C#]carousel.ItemsSource = new ObservableCollection<string>() { "Item1", "Item2", "Item3", "Item4", "Item5", "Item6", "Item7", "Item8", "Item9" };</td></tr>
</table>


{ ![](Data-Binding_images/Data-Binding_img1.png) | markdownify }
{:.image }




