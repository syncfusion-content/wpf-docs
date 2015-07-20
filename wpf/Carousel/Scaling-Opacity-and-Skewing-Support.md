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

Adding Scaling, Opacity and Skewing Support to an Application 

You can enable or disable this feature, using OpacityEnabled, ScalingEnabled, SkewXEnabled, SkewYEnabled properties.

The following code illustrates the usage of these properties.

[XAML]



&lt;syncfusion:Carousel x:Name="carousel" Height="400" Width="450" ItemsPerPage="5" OpacityEnabled="True" ScalingEnabled="True" SkewAngleXEnabled="False"                     TopItemPosition="0"&gt;
    &lt;syncfusion:Carousel.Path&gt;
        &lt;Path Data="M0,300 L600,300" Stroke="Blue" StrokeThickness="2" HorizontalAlignment="Stretch" VerticalAlignment="Stretch"/&gt;
    &lt;/syncfusion:Carousel.Path&gt;
    &lt;syncfusion:Carousel.OpacityFractions&gt;
        &lt;syncfusion:PathFractionCollection&gt;
            &lt;!--Fraction represents the position in Path-                Value represents the Opacity of Carousel item in a particular point--&gt;
            &lt;syncfusion:FractionValue Fraction="0" Value="1"/&gt;
            &lt;syncfusion:FractionValue Fraction="1" Value="0.5"/&gt;
        &lt;/syncfusion:PathFractionCollection&gt;
    &lt;/syncfusion:Carousel.OpacityFractions&gt;

    &lt;syncfusion:Carousel.ScaleFractions&gt;
         &lt;syncfusion:PathFractionCollection&gt;
            &lt;syncfusion:FractionValue Fraction="0" Value="1"/&gt;
            &lt;syncfusion:FractionValue Fraction="1" Value="0.5"/&gt;
        &lt;/syncfusion:PathFractionCollection&gt;
    &lt;/syncfusion:Carousel.ScaleFractions&gt;

    &lt;syncfusion:Carousel.ItemTemplate&gt;
        &lt;DataTemplate&gt;
            &lt;Border Height="100" Width="100"&gt;
                &lt;Border.Background&gt;
                    &lt;LinearGradientBrush EndPoint="0.5,1" StartPoint="0.5,0"&gt;
                        &lt;GradientStop Color="#FF8B8B8B" Offset="0"/&gt;
                        &lt;GradientStop Color="#FFDADADA" Offset="1"/&gt;
                        &lt;GradientStop Color="#FFF3F3F3" Offset="0.536"/&gt;
                    &lt;/LinearGradientBrush&gt;
                &lt;/Border.Background&gt;
                &lt;ContentControl Content="{Binding}" HorizontalAlignment="Center" VerticalAlignment="Center"/&gt;
            &lt;/Border&gt;
        &lt;/DataTemplate&gt;
    &lt;/syncfusion:Carousel.ItemTemplate&gt;
&lt;/syncfusion:Carousel&gt;







{ ![](Scaling-Opacity-and-Skewing-Support_images/Scaling-Opacity-and-Skewing-Support_img1.png) | markdownify }
{:.image }




Properties



 _Properties Table_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Type </td><td>
Data Type </td><td>
Reference links </td></tr>
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


