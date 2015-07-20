---
layout: post
title: Styling-and-Customization
description: styling and customization
platform: wpf
control: SfChart
documentation: ug
---

# Styling and Customization

SfChart support various customizing and styling options that allows you to enrich the application. 

## Palettes

SfChart provides options to apply different kinds of themes or palettes to your chart. You can define Palette either for the entire chart or for an individual series. 

We have some predefined palette such as

* Metro
* AutumnBrights
* FloraHues
* Pineapple
* TomotoSpectrum
* RedChrome
* PurpleChrome
* BlueChrome
* GreenChrome
* Elite
* LightCandy
* SandyBeach
> 
_Note: Elite, SandyBeach and LightCandy palettes are not supported in the bitmap series types._

The Palette brushes defined in the chart are applied to the series, to differentiate each of them. Likewise, series palette brushes are applied for each segment in a particular series.

Applying predefined Palettes for each series

The following section shows you how to define the various palettes for each series.

Metro Palette

Itis the default palette for SfChart, used to apply a set of predefined brushes to the series, in a predefined order. The following code example illustrates how to set the MetroPalette for the chart.

[XAML]



&lt;syncfusion:SfChart HorizontalAlignment="Center" VerticalAlignment="Center" Height="400"Width="650" Palette="Metro" /&gt;

The following is the screenshot for the series with multiple palettes.

{ ![http://help.syncfusion.com/ug/wpf/ImagesExt/image249_149.jpg](Styling-and-Customization_images/Styling-and-Customization_img1.jpeg) | markdownify }
{:.image }


Custom palettes for each series

The Custom Palette option enables you to define your own color brushes for the Palette using ColorModel property as given in the following code example.

[XAML]



     <syncfusion:SfChart HorizontalAlignment="Center" VerticalAlignment="Center"Height="400" Width="650"

                            Palette="Custom">



            &lt;syncfusion:SfChart.ColorModel&gt;



                &lt;syncfusion:ChartColorModel&gt;

                    &lt;syncfusion:ChartColorModel.CustomBrushes&gt;

                        &lt;SolidColorBrush Color="Green"/&gt;

                        &lt;SolidColorBrush Color="Blue"/&gt;

                        &lt;SolidColorBrush Color="Red" /&gt;

                        &lt;SolidColorBrush Color="Yellow"/&gt;

                        &lt;SolidColorBrush Color="Gray"/&gt;

                    &lt;/syncfusion:ChartColorModel.CustomBrushes&gt;

                &lt;/syncfusion:ChartColorModel&gt;



            &lt;/syncfusion:SfChart.ColorModel&gt;



        &lt;/syncfusion:SfChart&gt;





The following screenshot demonstrates series with CustomPalette.

{ ![http://help.syncfusion.com/ug/wpf/ImagesExt/image249_150.jpg](Styling-and-Customization_images/Styling-and-Customization_img2.jpeg) | markdownify }
{:.image }


None Palette

This palette sets the transparent color to the series. You can identify the series existence with the help of [legends](http://help.syncfusion.com/ug/wpf/Documents/legend.htm) or [adornments](http://help.syncfusion.com/ug/wpf/Documents/databinding2.htm).

Applying predefined Palette for each segment

The following section shows you how to define the various palettes for each segment of a series.

Metro Palette

It is the default palette for series also. This palette applies a set of predefined brushes to the segments of a series in a predefined order. The following code example shows you how to set the Metro Palette for the chart series.

[XAML]



     <syncfusion:LineSeries Label="2010" Palette="Metro"

                                     ItemsSource="{Binding Demands}"

                                     XBindingPath="Demand"

                                     YBindingPath="Year2010"

                                     />



{ ![http://help.syncfusion.com/ug/wpf/ImagesExt/image249_151.jpg](Styling-and-Customization_images/Styling-and-Customization_img3.jpeg) | markdownify }
{:.image }


None Palette

It applies the same color to all the segments, as shown in the following screenshot. And the brushes vary for additional series based on that predefined order.

{ ![http://help.syncfusion.com/ug/wpf/ImagesExt/image249_152.jpg](Styling-and-Customization_images/Styling-and-Customization_img4.jpeg) | markdownify }
{:.image }


Applying Custom Palette for each segment

The Custom Palette option enables you to define your own color brushes for the Palette, using ColorModel as shown in the following code example.

[XAML]



<syncfusion:LineSeries Label="2010" Palette="Custom"

                                     ItemsSource="{Binding Demands}"

                                     XBindingPath="Demand"

                                     YBindingPath="Year2010"

                                     >



            &lt;syncfusion:LineSeries.ColorModel&gt;

                &lt;syncfusion:ChartColorModel &gt;

                    &lt;syncfusion:ChartColorModel.CustomBrushes&gt;

                        &lt;SolidColorBrush Color="Green"/&gt;

                        &lt;SolidColorBrush Color="Blue"/&gt;

                        &lt;SolidColorBrush Color="Red" /&gt;

                        &lt;SolidColorBrush Color="Yellow"/&gt;

                        &lt;SolidColorBrush Color="Gray"/&gt;

                    &lt;/syncfusion:ChartColorModel.CustomBrushes&gt;

                &lt;/syncfusion:ChartColorModel&gt;

            &lt;/syncfusion:LineSeries.ColorModel&gt;



        &lt;/syncfusion:LineSeries&gt;





## Customize Legends

SfChart provides you with the option to customize the legends depending on the application’s requirement.

[XAML]

&lt;syncfusion:SfChart.Legend&gt;

            &lt;syncfusion:ChartLegend&gt;



                &lt;!-- Custom panel for legend items--&gt;

                &lt;syncfusion:ChartLegend.ItemsPanel&gt;

                    &lt;ItemsPanelTemplate &gt;

                        &lt;WrapPanel  Width="300"/&gt;

                    &lt;/ItemsPanelTemplate&gt;

                &lt;/syncfusion:ChartLegend.ItemsPanel&gt;



                &lt;!--Custom template for legend item--&gt;

                &lt;syncfusion:ChartLegend.ItemTemplate&gt;

                    &lt;DataTemplate&gt;

                        &lt;Grid&gt;

                            &lt;Grid.ColumnDefinitions&gt;

                                &lt;ColumnDefinition/&gt;

                                &lt;ColumnDefinition/&gt;

                            &lt;/Grid.ColumnDefinitions&gt;



                            &lt;!--For Legend icon--&gt;

                            &lt;Ellipse Margin="35,0,0,0"  Width="15" Height="15" Fill="{Binding Interior}"&gt;&lt;/Ellipse&gt;



                            &lt;!--For Legend label--&gt;

                            &lt;TextBlock Margin="10,5,5,0" FontSize="16" Grid.Column="1" Foreground="{Binding Interior}" Text="{Binding Label}"&gt;&lt;/TextBlock&gt;

                        &lt;/Grid&gt;

                    &lt;/DataTemplate&gt;

                &lt;/syncfusion:ChartLegend.ItemTemplate&gt;

            &lt;/syncfusion:ChartLegend&gt;

        &lt;/syncfusion:SfChart.Legend&gt;

    &lt;/Grid&gt;



{ ![C:/Users/rachel/Desktop/snaps/17.png](Styling-and-Customization_images/Styling-and-Customization_img5.png) | markdownify }
{:.image }


## Customize Series

You can use the CustomTemplate property to customize the series of the SfChart. This support is available for the following series:

* [LineSeries](http://help.syncfusion.com/ug/wpf/)
* [BubbleSeries](http://help.syncfusion.com/ug/wpf/)
* [ScatterSeries](http://help.syncfusion.com/ug/wpf/)
* [ColumnSeries](http://help.syncfusion.com/ug/wpf/)
* [BarSeries](http://help.syncfusion.com/ug/wpf/)
* [SplineSeries](http://help.syncfusion.com/ug/wpf/)
* [StepLineSeries](http://help.syncfusion.com/ug/wpf/)
* [StackingColumnSeries](http://help.syncfusion.com/ug/wpf/)
* [StackingBarSeries](http://help.syncfusion.com/ug/wpf/)
* [Stackingcolumn100Series](http://help.syncfusion.com/UG/Windows%20Phone%208/documents/stackingcolumn100ser.htm)
* [StackingBar100Series](http://help.syncfusion.com/UG/Windows%20Phone%208/documents/stackingbar100series.htm)



By using this feature, you can draw custom shapes for the above types of series. Define the DataTemplate for the CustomTemplate and this template is applied to each segment (data point) of the series. 

In this DataTemplate, the respective Segments come as DataContext. For instance, when the CustomTemplate is defined for the LineSeries, the LineSegment comes as data context that is useful for binding the series properties like Fill, Y value, Height, Width, etc.

The following table illustrates the properties available in the corresponding segment class of the series.

_Properties in the segment class_

<table>
<tr>
<td>
Series Types</td><td>
Properties</td><td>
Description</td></tr>
<tr>
<td>
LineSeries </td><td>
X1, Y1, X2, Y2</td><td>
These properties define the two points for drawing that line segment.</td></tr>
<tr>
<td>
BubbleSeries</td><td>
Size, RectX, RectY</td><td>
The Size defines the pixel size of each BubbleSegment. The RectX and RectY define the pixel positions where each segment plots.</td></tr>
<tr>
<td>
ScatterSeries,</td><td rowspan = "3">
Height, Width, RectX, RectY</td><td rowspan = "3">
The Height and Width define the size of that particular segment.The RectX and RectY define the pixel positions where each segment plots.</td></tr>
<tr>
<td>
ColumnSeries,StackingColumn,StackingColumn100</td></tr>
<tr>
<td>
BarSeriesStackingBarStackingBar100</td></tr>
<tr>
<td>
SplineSeries</td><td>
P1, P2Q1, Q2Data</td><td>
The P1 and P2 define the starting and ending points of that segment. The Q1 and Q2 defines the control points for the spline (Bezier curve).The Data gives the geometric path of that spline segment.</td></tr>
<tr>
<td>
StepLineSeries</td><td>
X1, Y1, X2,Y2,X3,Y3Points</td><td>
The X1, Y1, and X2, Y2 are the start and end points of that segment and X3 and Y3 represent step points that are useful to draw Waterfall like charts.The Points represent the point collection of the step line segment.</td></tr>
</table>


Other than the above properties, all the segments have the following properties like a metadata for the datapoint and series.

XData - This property returns the actual Y value of that particular segment.  

YData - This property returns the actual Y value of that particular segment. 

Item - This gives the underlying model object, so that you can get any property other than X and Y values.

Interior - This property gives the fill brush for that particular segment.

The following code example illustrates the use of CustomTemplate property.

[XAML]



 <syncfusion:ScatterSeries ItemsSource="{Binding Demands}"

                XBindingPath="Demand" ScatterHeight="40"

                YBindingPath="Year2010" ScatterWidth="40"

>

&lt;syncfusion:ScatterSeries.CustomTemplate&gt; 

&lt;DataTemplate&gt;

    &lt;Canvas&gt;

       <Path Data="M20.125,32l0.5,12.375L10.3125,

        12.375L10.3125,0.5L29.9375,0.5L29.9375,

        12.375L39.75,12.375Z" Stretch="Fill"

        Fill="{Binding Interior}"

        Height="{Binding ScatterHeight}"   

        Width="{Binding ScatterWidth}" 

        Canvas.Left="{Binding RectX}" 

        Canvas.Top="{Binding RectY}"/>

    &lt;/Canvas&gt;

&lt;/DataTemplate&gt;

&lt;/syncfusion:ScatterSeries.CustomTemplate&gt;

&lt;/syncfusion:ScatterSeries&gt;





The following screenshot represents chart scatter series. By default, that series displays Ellipse symbol. By using the Custom Template feature, it can be changed to arrow shape:

{ ![C:/Users/sureshs/Desktop/wpf.png](Styling-and-Customization_images/Styling-and-Customization_img6.png) | markdownify }
{:.image }


## Customize Tooltip

SfChart provides the option to define your own template for Tooltip, based on your application’s requirement. The following code example demonstrates the CustomTooltip using the TooltipTemplate property.

[XAML]



<syncfusion:LineSeries Label="2010" 

                                ItemsSource="{Binding Demands}"

                                XBindingPath="Demand"

                                YBindingPath="Year2010" ShowTooltip="True"

                                Palette="None"

                                >

            &lt;syncfusion:LineSeries.TooltipTemplate&gt;



                &lt;DataTemplate&gt;

                    &lt;Grid &gt;



                        &lt;StackPanel HorizontalAlignment="Right"&gt;

                            &lt;Grid Background="OrangeRed"&gt;

                                <TextBlock Text="{Binding Item.Demand }" Width="85" Height="25" Margin="5"

                                VerticalAlignment="Center"    TextAlignment="Center"  Foreground="White" FontSize="15"/>

                            &lt;/Grid&gt;

                            &lt;Grid Background="MediumSpringGreen"&gt;

                                <TextBlock VerticalAlignment="Center" TextAlignment="Center" Margin="5" Text="{Binding YData}" Height="25"

                                 Width="85" HorizontalAlignment="Center" Foreground="White" FontSize="15"/>

                            &lt;/Grid&gt;

                        &lt;/StackPanel&gt;

                    &lt;/Grid&gt;

                &lt;/DataTemplate&gt;



            &lt;/syncfusion:LineSeries.TooltipTemplate&gt;



        &lt;/syncfusion:LineSeries&gt;





The following screenshot illustrates custom Tooltip.

{ ![C:/Users/rachel/Desktop/snaps/19.png](Styling-and-Customization_images/Styling-and-Customization_img7.png) | markdownify }
{:.image }


