---
layout: post
title: Change-SelectedItem-position
description: change selecteditem position
platform: wpf
control: Carousel
documentation: ug
---

### Change SelectedItem position

Using TopItemPosition property, you can change the position of SelectedItem in a given path.



  _Property table_

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
TopItemPosition</td><td>
Sets the SelectedItemPosition in Panel.</td><td>
DependencyProperty</td><td>
Double</td><td>
</td></tr>
</table>


In the following example, TopItemPosition is set to 0.0. So the SelectedItem is displayed at the beginning of the Path.



[XAML]



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





{{ '![](Change-SelectedItem-position_images/Change-SelectedItem-position_img1.png)' | markdownify }}
{:.image }


