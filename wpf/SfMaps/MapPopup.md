---
layout: post
title: MapPopup
description: mappopup
platform: wpf
control: SfMap
documentation: ug
---

# MapPopup

MapPopup is a hanging window, displayed when the shape is tapped. It shows additional information from the object bounded with the shape. By default, it takes the property of the bounded object that is referred in the ShapeValuePathand displays its content when the corresponding shape is tapped.

MapPopup is displayed only when “MapPopupVisibility” set to true in the shape file layer.

It also customizes the MapPopup template. “MapPopupCustomTemplate” is a DataTemplate type API that is used to expose the custom template for the MapPopup.

[XAML]

&lt;syncfusion:SfMap &gt;

            &lt;syncfusion:SfMap.Layers&gt;

                &lt;syncfusion:ShapeFileLayer TranslateZoomLevel="5"  ShapeIDPath="NAME" MapPopupVisibility="Visible" Background="#FFCFCECD" ShapeIDTableField="NAME"   ItemsSource="{Binding Countries}" Uri="MapApp.world1.shp"&gt;

                    &lt;syncfusion:ShapeFileLayer.PopupCustomTemplate&gt;

                        &lt;DataTemplate&gt;

                            &lt;Border&gt;

                                &lt;Grid Width="200"&gt;

                                    &lt;Grid.RowDefinitions&gt;

                                        &lt;RowDefinition /&gt;

                                        &lt;RowDefinition /&gt;

                                        &lt;RowDefinition /&gt;

                                    &lt;/Grid.RowDefinitions&gt;

                                    &lt;Grid.ColumnDefinitions&gt;

                                        &lt;ColumnDefinition/&gt;

                                    &lt;/Grid.ColumnDefinitions&gt;

                                    &lt;Border VerticalAlignment="Center" Padding="10,5,0,0" Height="30" Background="#FF4B4A4A"  Grid.ColumnSpan="2"&gt;

                                        &lt;TextBlock Foreground="White" FontFamily="Segoe UI" FontSize="14"  Text="{Binding NAME}"/&gt;

                                    &lt;/Border&gt;

                                    &lt;Border Padding="3,10,3,3"  Background="White"  Grid.Row="1" Grid.ColumnSpan="2"&gt;

                                        &lt;StackPanel HorizontalAlignment="Center" VerticalAlignment="Center"  Height="35" Background="White" Orientation="Horizontal"&gt;

                                            &lt;TextBlock  Foreground="Black" FontFamily="Segoe UI"  FontSize="16" Text="Total Sales:" /&gt;

                                            &lt;TextBlock Foreground="Black"  FontFamily="Segoe UI" FontSize="16" Text="{Binding Population}"/&gt;

                                        &lt;/StackPanel&gt;

                                    &lt;/Border&gt;

                                    &lt;Border HorizontalAlignment="Center" Grid.Row="2"&gt;

                                        &lt;StackPanel Orientation="Horizontal"&gt;

                                            &lt;ItemsControl Background="White" x:Name="ProductName"  ItemsSource="{Binding NAME}" DisplayMemberPath="NAME"/&gt;

                                            &lt;ItemsControl  Background="White"  ItemsSource="{Binding Population}" DisplayMemberPath="Population"/&gt;

                                        &lt;/StackPanel&gt;

                                    &lt;/Border&gt;

                                &lt;/Grid&gt;

                            &lt;/Border&gt;

                        &lt;/DataTemplate&gt;

                    &lt;/syncfusion:ShapeFileLayer.PopupCustomTemplate&gt;

                    &lt;syncfusion:ShapeFileLayer.ShapeSettings&gt;

                        &lt;syncfusion:ShapeSetting  ShapeStroke="#FF1978AA" ShapeValuePath="Population" ColorPalette="CustomPalette" ShapeStrokeThickness="0.5"  &gt;

                            &lt;syncfusion:ShapeSetting.CustomColors&gt;

                                &lt;syncfusion:MapColorPalette FillBrush="#FFC6EAFB"/&gt;

                                &lt;syncfusion:MapColorPalette FillBrush="#FF93D3F4"/&gt;

                                &lt;syncfusion:MapColorPalette FillBrush="#FF5FB5E6"/&gt;

                                &lt;syncfusion:MapColorPalette FillBrush="#FF3E9FD8"/&gt;

                                &lt;syncfusion:MapColorPalette FillBrush="#FF2991CF"/&gt;



                            &lt;/syncfusion:ShapeSetting.CustomColors&gt;

                            &lt;syncfusion:ShapeSetting.FillSetting&gt;

                                &lt;syncfusion:ShapeFillSetting AutoFillColors="True"/&gt;

                            &lt;/syncfusion:ShapeSetting.FillSetting&gt;

                        &lt;/syncfusion:ShapeSetting&gt;

                    &lt;/syncfusion:ShapeFileLayer.ShapeSettings&gt;



                &lt;/syncfusion:ShapeFileLayer&gt;



            &lt;/syncfusion:SfMap.Layers&gt;

        &lt;/syncfusion:SfMap &gt;



{ ![](MapPopup_images/MapPopup_img1.png) | markdownify }
{:.image }


