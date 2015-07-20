---
layout: post
title: Displaying-Items-on-a-Map
description: displaying items on a map
platform: wpf
control: SfMap
documentation: ug
---

# Displaying Items on a Map

Along with bubbles, the ItemsSource data can be visualized with other elements. The ItemsTemplate property is used to define the template for the items that are displayed on the map. By default, the map elements show the values of the object that is defined in the ShapeValuePath of the ShapeFileLayer’s shape setting.

ItemsTemplate

ItemsTemplate is a type of DataTemplate that is used to override the default template for map items. “Data” is the property that holds the object for a map item.

Code Sample

Implement the Model and ViewModel, as mentioned in the Data Binding topic, and include the following code in the XAML page:

[XAML]

&lt;syncfusion:SfMap&gt;

            &lt;syncfusion:SfMap.Layers&gt;

                &lt;syncfusion:ShapeFileLayer Background="White" ItemsSource="{Binding Countries}" ShapeIDPath="NAME" ShapeIDTableField="NAME" Uri="BubbleVisualization.ShapeFiles.world1.shp"&gt;

                    &lt;syncfusion:ShapeFileLayer.ItemsTemplate&gt;

                        &lt;DataTemplate&gt;

                            &lt;Grid Background="#332D2D2D"&gt;

                                &lt;TextBlock Margin="5" Foreground="White" Opacity="1" FontSize="12" FontWeight="SemiBold" FontFamily="Segoe UI" Text="{Binding Data.NAME}"/&gt;

                            &lt;/Grid&gt;

                        &lt;/DataTemplate&gt;

                    &lt;/syncfusion:ShapeFileLayer.ItemsTemplate&gt;

                    &lt;syncfusion:ShapeFileLayer.ShapeSettings&gt;

                        &lt;syncfusion:ShapeSetting ShapeFill="#E5E5E5" ShapeStroke="#C1C1C1" ShapeStrokeThickness="0.5" ShapeValuePath="Population" ShapeColorValuePath="Population" &gt;

                            &lt;syncfusion:ShapeSetting.FillSetting&gt;

                                &lt;syncfusion:ShapeFillSetting AutoFillColors="False"&gt;

                                    &lt;syncfusion:ShapeFillSetting.ColorMappings&gt;

                                        &lt;syncfusion:RangeColorMapping To="1500000000" From="750000000" Color="#2A91CF"/&gt;

                                        &lt;syncfusion:RangeColorMapping To="750000000" From="1000" Color="#3D9FD8"/&gt;

                                        &lt;syncfusion:RangeColorMapping From="0" To="1000" Color="#C7E9FA"/&gt;

                                    &lt;/syncfusion:ShapeFillSetting.ColorMappings&gt;

                                &lt;/syncfusion:ShapeFillSetting&gt;

                            &lt;/syncfusion:ShapeSetting.FillSetting&gt;

                        &lt;/syncfusion:ShapeSetting&gt;

                    &lt;/syncfusion:ShapeFileLayer.ShapeSettings&gt;

                &lt;/syncfusion:ShapeFileLayer&gt;

            &lt;/syncfusion:SfMap.Layers&gt;

        &lt;/syncfusion:SfMap&gt;



{ ![](Displaying-Items-on-a-Map_images/Displaying-Items-on-a-Map_img1.png) | markdownify }
{:.image }


