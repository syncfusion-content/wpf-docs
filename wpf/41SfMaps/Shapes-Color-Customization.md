---
layout: post
title: Shapes-Color-Customization
description: shapes color customization
platform: wpf
control: SfMap
documentation: ug
---

# Shapes Color Customization

Maps highly support the customization of the shape’s color. The shape’s color can be customized by using the following methods:

1. Using the ShapeFill, ShapeStroke and ShapeStrokeThickness properties.
2. Using tree map-like support.
3. Using the color palette.

The important property that makes an impact on shape colors is AutoFillColors. This is a Boolean type property. This property is available in the FillSetting. The use of this property is explained in the following sections.

About ShapeFill, ShapeStroke and ShapeStrokeThickness

The above mentioned properties are available in the ShapesSettingproperty of the ShapeFileLayer. ShapeSettingdefines the basic customization settings of shapes in the map. 

ShapeFill

ShapeFill is a Brush type property that sets the fill color of the shapes in the map.

ShapeStroke

ShapeStroke is also a brush type property that sets the border color of the shape in the map.

ShapeStrokeThickness

ShapeStrokeThickness is a double type property that sets the border thickness of the shape in the map.

These setting works only when “AutoFillColor” is set as false.

[XAML]



&lt;syncfusion:SfMap&gt;

            &lt;syncfusion:SfMap.Layers&gt;

                &lt;syncfusion:ShapeFileLayer Uri="MapApp.usa_st.shp"&gt;

                    &lt;syncfusion:ShapeFileLayer.ShapeSettings&gt;

                        &lt;syncfusion:ShapeSetting ShapeFill="Gray" ShapeStroke="Black" ShapeStrokeThickness="1"&gt;

                            &lt;syncfusion:ShapeSetting.FillSetting&gt;

                                &lt;syncfusion:ShapeFillSetting AutoFillColors="False"/&gt;

                            &lt;/syncfusion:ShapeSetting.FillSetting&gt;

                        &lt;/syncfusion:ShapeSetting&gt;

                    &lt;/syncfusion:ShapeFileLayer.ShapeSettings&gt;

                &lt;/syncfusion:ShapeFileLayer&gt;

            &lt;/syncfusion:SfMap.Layers&gt;

        &lt;/syncfusion:SfMap &gt;



{ ![C:/Users/karthikeyanp/Desktop/UGPics/ShapeFill.png](Shapes-Color-Customization_images/Shapes-Color-Customization_img1.png) | markdownify }
{:.image }


Tree map-like support

ShapeFill is set based on the under-bound values of the shape. This provides a tree map-like impact on the map UI. The RangeColorMapping property provides a tree map-like fill for the shapes.

Range Color Mapping

Range color mapping is one of the features used to differentiate the shape’s fill based on its under-bound value and color ranges. Range color mapping contains the following properties:

_Property Table_

<table>
<tr>
<td>
Property</td><td>
Type</td><td>
Description</td></tr>
<tr>
<td>
From </td><td>
Double</td><td>
Gets or sets the From value of ColorValuePath</td></tr>
<tr>
<td>
To</td><td>
Double</td><td>
Gets or sets the To value of ColorValuePath</td></tr>
<tr>
<td>
Color</td><td>
Color</td><td>
Gets or sets the color values for the given range based on the From and To .</td></tr>
</table>


The fill color of a particular bubble fill is determined by its under-bound value and color range. To provide a Tree Map like impact on the map, the data binding should work properly. For example, consider the following color ranges.

[XAML]

&lt;syncfusion:ShapeSetting ShapeFill="#E5E5E5" ShapeStroke="#C1C1C1" ShapeStrokeThickness="0.5" ShapeValuePath="Population"&gt;

    &lt;syncfusion:ShapeSetting.FillSetting&gt;

        &lt;syncfusion:ShapeFillSetting AutoFillColors="False"&gt;

           &lt;syncfusion:ShapeFillSetting.ColorMappings&gt;

              &lt;syncfusion:RangeColorMapping To="1500000000" From="750000000" Color="#2A91CF"/&gt;

              &lt;syncfusion:RangeColorMapping To="750000000" From="0" Color="#3D9FD8"/&gt;

              &lt;syncfusion:RangeColorMapping To="0" From="0" Color="#C7E9FA"/&gt;

           &lt;/syncfusion:ShapeFillSetting.ColorMappings&gt;

       &lt;/syncfusion:ShapeFillSetting&gt;

   &lt;/syncfusion:ShapeSetting.FillSetting&gt;

 &lt;/syncfusion:ShapeSetting&gt;



When under-bound object value is 750000000, then the fill color of the corresponding bubble is set to #3D9FD8. As mentioned earlier, the under-bound value of the bubble is set through the ShapeValuePath in the ShapeSetting.

When the under-bound value is under any of the given sorted range or above the sorted range, then the fill is set to Black.

AutoFillColor must be set to false to enable the range color mapping.

> _Note: The shape’s under-bound object value must have numeric property and should be mentioned in ShapeValuePath to work on this. The color between the given ranges is applied only to the shapes that have a proper under-bound values. The color for other shapes is the ShapeFill’s color._

[XAML]

&lt;syncfusion:SfMap&gt;

            &lt;syncfusion:SfMap.Layers&gt;

                &lt;syncfusion:ShapeFileLayer ItemsSource="{Binding Countries}" Uri="BubbleVisualization.world1.shp" ShapeIDPath="NAME" ShapeIDTableField="NAME"&gt;

                    &lt;syncfusion:ShapeFileLayer.ShapeSettings &gt;

                        &lt;syncfusion:ShapeSetting ShapeFill="#E5E5E5" ShapeStroke="Black" ShapeStrokeThickness="1" ShapeColorValuePath="Population" ShapeValuePath="Population"&gt;

                            &lt;syncfusion:ShapeSetting.FillSetting&gt;

                                &lt;syncfusion:ShapeFillSetting AutoFillColors="False"&gt;

                                    &lt;syncfusion:ShapeFillSetting.ColorMappings&gt;

                                        &lt;syncfusion:RangeColorMapping To="1500000000" From="750000000" Color="#2A91CF"/&gt;

                                        &lt;syncfusion:RangeColorMapping To="750000000" From="0" Color="#3D9FD8"/&gt;

                                        &lt;syncfusion:RangeColorMapping To="0" From="0" Color="#C7E9FA"/&gt;

                                    &lt;/syncfusion:ShapeFillSetting.ColorMappings&gt;

                                &lt;/syncfusion:ShapeFillSetting&gt;

                            &lt;/syncfusion:ShapeSetting.FillSetting&gt;

                        &lt;/syncfusion:ShapeSetting&gt;

                    &lt;/syncfusion:ShapeFileLayer.ShapeSettings&gt;

                &lt;/syncfusion:ShapeFileLayer&gt;

            &lt;/syncfusion:SfMap.Layers&gt;

        &lt;/syncfusion:SfMap &gt;



{ ![](Shapes-Color-Customization_images/Shapes-Color-Customization_img2.png) | markdownify }
{:.image }


ColorPalette

ColorPalette is a set of colors that are applied on the shapes. Map contains two build in color palettes. They are: 

1. Metro 
2. CoolBlue 

ColorPalette has to be set in the ShapeSetting’s ColorPalette property. ColorPalette is the enum property that accepts Metro, CoolBlue and CustomPalette.

[XAML]



&lt;syncfusion:SfMap &gt;

            &lt;syncfusion:SfMap.Layers&gt;

                &lt;syncfusion:ShapeFileLayer Uri="MapApp.usa_st.shp"&gt;

                    &lt;syncfusion:ShapeFileLayer.ShapeSettings&gt;

                        &lt;syncfusion:ShapeSetting ColorPalette="Metro"&gt;

                            &lt;syncfusion:ShapeSetting.FillSetting&gt;

                                &lt;syncfusion:ShapeFillSetting AutoFillColors="True"/&gt;

                            &lt;/syncfusion:ShapeSetting.FillSetting&gt;

                        &lt;/syncfusion:ShapeSetting&gt;

                    &lt;/syncfusion:ShapeFileLayer.ShapeSettings&gt;

                &lt;/syncfusion:ShapeFileLayer&gt;

            &lt;/syncfusion:SfMap.Layers&gt;

        &lt;/syncfusion:SfMap &gt;



{ ![](Shapes-Color-Customization_images/Shapes-Color-Customization_img3.png) | markdownify }
{:.image }


About CustomColorPalette

Besides the build in the color palettes, the custom colors can be defined for the color palette. The custom colors are defined in the “CustomColors” in “ShapeSetting.” CustomColors is the collection property that accepts the “MapColorPalette.” To apply the custom colors, “ColorPalette” must be set to “CustomPalette” and CustomColors should be defined.

About MapColorPalette

MapColorPalette contains a property named “FillBrush”. This property sets the fill color of the shape when custom palette is set.

Code to set CustomColorPalette:

[XAML]



 &lt;syncfusion:SfMap&gt;

            &lt;syncfusion:SfMap.Layers&gt;

                &lt;syncfusion:ShapeFileLayer Uri="MapApp.usa_st.shp"&gt;

                    &lt;syncfusion:ShapeFileLayer.ShapeSettings&gt;

                        &lt;syncfusion:ShapeSetting ColorPalette="CustomPalette"&gt;

                            &lt;syncfusion:ShapeSetting.CustomColors&gt;

                                &lt;syncfusion:MapColorPalette FillBrush="Gray"/&gt;

                                &lt;syncfusion:MapColorPalette FillBrush="Gold"/&gt;

                                &lt;syncfusion:MapColorPalette FillBrush="LightBlue"/&gt;

                                &lt;syncfusion:MapColorPalette FillBrush="LightCyan"/&gt;

                            &lt;/syncfusion:ShapeSetting.CustomColors&gt;

                            &lt;syncfusion:ShapeSetting.FillSetting&gt;

                                &lt;syncfusion:ShapeFillSetting AutoFillColors="True"/&gt;

                            &lt;/syncfusion:ShapeSetting.FillSetting&gt;

                        &lt;/syncfusion:ShapeSetting&gt;

                    &lt;/syncfusion:ShapeFileLayer.ShapeSettings&gt;

                &lt;/syncfusion:ShapeFileLayer&gt;

            &lt;/syncfusion:SfMap.Layers&gt;

        &lt;/syncfusion:SfMap &gt;



{ ![](Shapes-Color-Customization_images/Shapes-Color-Customization_img4.png) | markdownify }
{:.image }


