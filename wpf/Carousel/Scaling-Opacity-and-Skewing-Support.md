---
layout: post
title: Scaling-Opacity-and-Skewing-Support
description: scaling, opacity and skewing support
platform: wpf
control: Carousel
documentation: ug
---

# Scaling, Opacity and Skewing Support

You can control Scaling, Opacity and Skewing for CarouselItem’s using ScaleFractions, OpacityFractions and SkewAngleXFractions,SkewAngleYFractions properties. Using TopItemPosition property, you can change the position of SelectedItem in a given path.

## Adding Scaling, Opacity and Skewing Support to an Application 

You can enable or disable this feature, using OpacityEnabled, ScalingEnabled, SkewXEnabled, SkewYEnabled properties.

The following code illustrates the usage of these properties.

{% highlight xml %}


<syncfusion:Carousel x:Name="carousel" Height="400" Width="450" ItemsPerPage="5" OpacityEnabled="True" ScalingEnabled="True" SkewAngleXEnabled="False"                     TopItemPosition="0">
    <syncfusion:Carousel.Path>
        <Path Data="M0,300 L600,300" Stroke="Blue" StrokeThickness="2" HorizontalAlignment="Stretch" VerticalAlignment="Stretch"/>
    </syncfusion:Carousel.Path>
    <syncfusion:Carousel.OpacityFractions>
        <syncfusion:PathFractionCollection>
            <!--Fraction represents the position in Path-                Value represents the Opacity of Carousel item in a particular point-->
            <syncfusion:FractionValue Fraction="0" Value="1"/>
            <syncfusion:FractionValue Fraction="1" Value="0.5"/>
        </syncfusion:PathFractionCollection>
    </syncfusion:Carousel.OpacityFractions>

    <syncfusion:Carousel.ScaleFractions>
         <syncfusion:PathFractionCollection>
            <syncfusion:FractionValue Fraction="0" Value="1"/>
            <syncfusion:FractionValue Fraction="1" Value="0.5"/>
        </syncfusion:PathFractionCollection>
    </syncfusion:Carousel.ScaleFractions>

    <syncfusion:Carousel.ItemTemplate>
        <DataTemplate>
            <Border Height="100" Width="100">
                <Border.Background>
                    <LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0">
                        <GradientStop Color="#FF8B8B8B" Offset="0"/>
                        <GradientStop Color="#FFDADADA" Offset="1"/>
                        <GradientStop Color="#FFF3F3F3" Offset="0.536"/>
                    </LinearGradientBrush>
                </Border.Background>
                <ContentControl Content="{Binding}" HorizontalAlignment="Center" VerticalAlignment="Center"/>
            </Border>
        </DataTemplate>
    </syncfusion:Carousel.ItemTemplate>
</syncfusion:Carousel>



{% endhighlight %}



![](Scaling-Opacity-and-Skewing-Support_images/Scaling-Opacity-and-Skewing-Support_img1.png)



## Properties



 _Properties Table_

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
OpacityEnabled</td><td>
Enables or disables the Opacity support in Carousel.</td><td>
DependencyProperty</td><td>
Bool</td><td>
</td></tr>
<tr>
<td>
ScalingEnabled</td><td>
Enables or disables the Scaling support in Carousel.</td><td>
DependencyProperty</td><td>
Bool</td><td>
</td></tr>
<tr>
<td>
SkewAngleXEnabled</td><td>
Enables or disables the SkewAngleX support in Carousel.</td><td>
DependencyProperty</td><td>
Bool</td><td>
</td></tr>
<tr>
<td>
SkewAngleYEnabled</td><td>
Enables or disables the SkewAngleY support in Carousel.</td><td>
DependencyProperty</td><td>
Bool</td><td>
</td></tr>
<tr>
<td>
OpacityFractions</td><td>
Sets the Opacity Value for CarouselItem in the Path.</td><td>
DependencyProperty</td><td>
PathFractionCollection</td><td>
</td></tr>
<tr>
<td>
ScalingFractions</td><td>
Sets the Scale Value for CarouselItem in the Path.</td><td>
DependencyProperty</td><td>
PathFractionCollection</td><td>
</td></tr>
<tr>
<td>
SkewAngleXFraction</td><td>
 Sets the SkewAngleX Value for CarouselItem in the Path.</td><td>
DependencyProperty</td><td>
PathFractionCollection</td><td>
</td></tr>
<tr>
<td>
SkewAngleYFractions</td><td>
 Sets the SkewAngleY Value for CarouselItem in the Path.</td><td>
DependencyProperty</td><td>
PathFractionCollection</td><td>
</td></tr>
</table>


