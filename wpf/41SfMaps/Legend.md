---
layout: post
title: Legend
description: legend
platform: wpf
control: SfMap
documentation: ug
---

# Legend

A legend is a key to symbolism used on a map, usually containing swatches of symbols with descriptions. It provides valuable information for interpreting what the map is showing you, and can be represented in various colors and shapes based on the data.

Visibility of Legend 

Legends are visible only by setting the LegendVisibility property of the Visibility type as Visible in the ShapeFileLayer.

Positioning of Legend 

Map legends can be positioned by setting the LegendPosition property in ShapeFileLayer. Also, the legend can be positioned based on the margin values for the x axis and the y axis with the help of the LegendPositionX and LegendPositionY properties availablein ShapeFileLayer. For positioning the legend based on margins corresponding to a map, LegendPosition must be set with value of “Default”.

_Property Table_

<table>
<tr>
<td>
Property</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
LegendPosition</td><td>
LegendPosition (enum) </td><td>
Gets or sets the standard position for the legend.</td></tr>
<tr>
<td>
LegendPositionX</td><td>
Double</td><td>
Gets or sets the margin value for the x axis.</td></tr>
<tr>
<td>
LegendPositionY</td><td>
Double</td><td>
Gets or sets the margin value for the y axis.</td></tr>
</table>
Header for Legends 

A header for the legend can be added by setting the LegendHeader property of the string type.

Categories of Legend 

Legends are categorized as two types:

* Legends for shape layers.
* Legends for bubbles.

These can be set by using the LegendType property of the type LegendType.

Shapes for the Legend 

Bubble type legends are always bubbles with varying sizes.  The size of the bubbles is obtained from the SizeRatio from the BubbleMarkerSetting.

Layer shape type legends can be different shapes for the legend. The shapes can be set by using the LegendIcon, of the LegendIcon type. 

Arranging the Legends 

Legends are arranged in matrix format. The number of columns in the arranging matrix can be set by setting the LegendColumnSplit property of the int type. 

[XAML]

&lt;syncfusion:SfMap.Layers&gt;

                <syncfusion:ShapeFileLayer 

                    LegendType="Layers" LegendHeader="LegendHeader"

                    LegendColumnSplit="2" LegendPositionX="10"

                    LegendPositionY="200" LegendVisibility="Visible"

                    LegendIcon="Rectangle" ItemsSource="{Binding Countries}" ShapeIDPath="NAME"  

                    ShapeIDTableField="NAME" Uri="BubbleVisualization.ShapeFiles.world1.shp">



                    &lt;syncfusion:ShapeFileLayer.ShapeSettings&gt;

                        &lt;syncfusion:ShapeSetting ShapeColorValuePath="Population" ShapeFill="#E5E5E5" ShapeStroke="#C1C1C1" ShapeStrokeThickness="0.5" ShapeValuePath="Population" &gt;

                            &lt;syncfusion:ShapeSetting.FillSetting&gt;

                                &lt;syncfusion:ShapeFillSetting AutoFillColors="False"&gt;

                                    &lt;syncfusion:ShapeFillSetting.ColorMappings&gt;

                                        &lt;syncfusion:RangeColorMapping Color="#7F20BCEE" To="1347350000" From="314623001"/&gt;

                                        &lt;syncfusion:RangeColorMapping Color="#7FA7CE38" To="314623001" From="143228301"/&gt;

                                        &lt;syncfusion:RangeColorMapping Color="#7FF1B21A" To="143228301" From="82724090"/&gt;

                                        &lt;syncfusion:RangeColorMapping Color="#7F1DA249" To="50586757" From="22789702"/&gt;

                                        &lt;syncfusion:RangeColorMapping Color="#7FEB737C" To="22789702" From="0"/&gt;

                                        &lt;syncfusion:RangeColorMapping Color="#7FED2D95" To="82724090" From="50586757"/&gt;        

                                                                        &lt;/syncfusion:ShapeFillSetting.ColorMappings&gt;

                                &lt;/syncfusion:ShapeFillSetting&gt;

                            &lt;/syncfusion:ShapeSetting.FillSetting&gt;

                        &lt;/syncfusion:ShapeSetting&gt;

                    &lt;/syncfusion:ShapeFileLayer.ShapeSettings&gt;

                &lt;/syncfusion:ShapeFileLayer&gt;

            &lt;/syncfusion:SfMap.Layers&gt;

        &lt;/syncfusion:SfMap&gt;



{ ![](Legend_images/Legend_img1.png) | markdownify }
{:.image }


_Legend for shape layers_

[XAML]

&lt;syncfusion:SfMap&gt;

            &lt;syncfusion:SfMap.Layers&gt;

                <syncfusion:ShapeFileLayer 

                    LegendType="Bubbles" LegendHeader="LegendHeader"

                    LegendColumnSplit="2" LegendPositionX="10"

                    LegendPositionY="200" LegendVisibility="Visible"

                    LegendIcon="Rectangle" ItemsSource="{Binding Countries}" ShapeIDPath="NAME"  

                    ShapeIDTableField="NAME" Uri="BubbleVisualization.ShapeFile.world1.shp">

                    &lt;syncfusion:ShapeFileLayer.BubbleMarkerSetting&gt;

                        &lt;syncfusion:BubbleMarkerSetting AutoFillColor="False" MaxSize="50" MinSize="20" StrokeThickness="0" ValuePath="Population"&gt;

                            &lt;syncfusion:BubbleMarkerSetting.ColorMappings&gt;

                                &lt;syncfusion:RangeColorMapping Color="#7F20BCEE" To="1347350000" From="314623001"/&gt;

                                &lt;syncfusion:RangeColorMapping Color="#7FA7CE38" To="314623001" From="143228301"/&gt;

                                &lt;syncfusion:RangeColorMapping Color="#7FF1B21A" To="143228301" From="82724090"/&gt;

                                &lt;syncfusion:RangeColorMapping Color="#7F1DA249" To="50586757" From="22789702"/&gt;

                                &lt;syncfusion:RangeColorMapping Color="#7FEB737C" To="22789702" From="0"/&gt;

                                &lt;syncfusion:RangeColorMapping Color="#7FED2D95" To="82724090" From="50586757"/&gt;

                            &lt;/syncfusion:BubbleMarkerSetting.ColorMappings&gt;

                        &lt;/syncfusion:BubbleMarkerSetting&gt;

                    &lt;/syncfusion:ShapeFileLayer.BubbleMarkerSetting&gt;

                &lt;/syncfusion:ShapeFileLayer&gt;

            &lt;/syncfusion:SfMap.Layers&gt;

        &lt;/syncfusion:SfMap&gt;



{ ![](Legend_images/Legend_img2.png) | markdownify }
{:.image }


_Legend for Bubbles_

