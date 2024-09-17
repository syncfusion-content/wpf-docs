---
layout: post
title: Surface Area in WPF Surface Chart control | Syncfusion
description: Learn here all about Surface Area support in Syncfusion WPF Surface Chart (SfSurfaceChart) control and more.
platform: wpf
control: SfSurfaceChart
documentation: ug
---

# Surface Area in WPF Surface Chart (SfSurfaceChart)

Surface area represents the entire surface chart and all its elements, such as the axis, color bar and walls.It is a virtual rectangular space that contains these elements.

The surface chart can be customized to enrich your application’s look and feel. SfSurfaceChat provides API’s to customize surface area based on your requirement. This section explains about the elements and API for common customization of surface area.

## Properties

<table>
<tr>
<th>
Name</th><th>
Description</th></tr>
<tr>
<td>
{{'[EnableRotation](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceBase.html#Syncfusion_UI_Xaml_Charts_SurfaceBase_EnableRotation)'| markdownify }}<br/><br/></td><td>
Gets or sets the bool value that represent the value to enable the rotation for surface chart.  <br/><br/></td></tr>
<tr>
<td>
{{'[Rotate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceBase.html#Syncfusion_UI_Xaml_Charts_SurfaceBase_Rotate)'| markdownify }}<br/><br/></td><td>
Gets or sets the double value that represents a rotation value for surface chart. <br/><br/></td></tr>
<tr>
<td>
{{'[Tilt](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceBase.html#Syncfusion_UI_Xaml_Charts_SurfaceBase_Tilt)'| markdownify }}<br/><br/></td><td>
Gets or sets the double value that represents a tilt value for surface chart.  <br/><br/></td></tr>
<tr>
<td>
{{'[CameraProjection](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_CameraProjection)'| markdownify }}<br/><br/></td><td>
Gets or sets the value that represents type of camera projection in surface chart.  <br/><br/></td></tr>
<tr>
<td>
{{'[Header](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceBase.html#Syncfusion_UI_Xaml_Charts_SurfaceBase_Header)'| markdownify }}<br/><br/></td><td>
Gets or sets the object that represents the content of a surface header. This property is used to specify any object as Header for surface chart.  <br/><br/></td></tr>
<tr>
<td>
{{'[LeftWallBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceBase.html#Syncfusion_UI_Xaml_Charts_SurfaceBase_LeftWallBrush)'| markdownify }}<br/><br/></td><td>
Gets or sets a brush for left wall.  <br/><br/></td></tr>
<tr>
<td>
{{'[BottomWallBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceBase.html#Syncfusion_UI_Xaml_Charts_SurfaceBase_BottomWallBrush)'| markdownify }}<br/><br/></td><td>
Gets or sets a brush for bottom wall.  <br/><br/></td></tr>
<tr>
<td>
{{'[BackWallBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceBase.html#Syncfusion_UI_Xaml_Charts_SurfaceBase_BackWallBrush)'| markdownify }}<br/><br/></td><td>
Gets or sets a brush for back wall.  <br/><br/></td></tr>
<tr>
<td>
{{'[WallThickness](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceBase.html#Syncfusion_UI_Xaml_Charts_SurfaceBase_WallThickness)'| markdownify }}<br/><br/></td><td>
Gets or sets the wall thickness for surface chart.  <br/><br/></td></tr>
<tr>
<td>
{{'[WireframeStrokeThickness](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_WireframeStrokeThickness)'| markdownify }}<br/><br/></td><td>
Gets or sets the double value that represents wireframe stroke thickness.  <br/><br/></td></tr>
<tr>
<td>
{{'[WireframeStroke](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_WireframeStroke)'| markdownify }}<br/><br/></td><td>
Gets or sets a brush for wireframe stroke.  <br/><br/></td></tr>
<tr>
<td>
{{'[Palette](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceBase.html#Syncfusion_UI_Xaml_Charts_SurfaceBase_Palette)'| markdownify }}<br/><br/></td><td>
Gets or sets the color palette for the chart surface chart.  <br/><br/></td></tr>
<tr>
<td>
{{'[ZoomLevel](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_ZoomLevel)'| markdownify }}<br/><br/></td><td>
Gets or sets double value that represent the zoom level value for surface chart.  <br/><br/></td></tr>
<tr>
<td>
{{'[Type](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_Type)'| markdownify }}<br/><br/></td><td>
Gets or sets type for choosing surface chart type.  <br/><br/></td></tr>
<tr>
<td>
{{'[XAxis](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_XAxis)'| markdownify }}<br/><br/></td><td>
Gets or sets the X-Axis for the surface chart.  <br/><br/></td></tr>
<tr>
<td>
{{'[YAxis](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_YAxis)'| markdownify }}<br/><br/></td><td>
Gets or sets the Y-Axis for the surface chart.  <br/><br/></td></tr>
<tr>
<td>
{{'[ZAxis](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_ZAxis)'| markdownify }}<br/><br/></td><td>
Gets or sets the Z-Axis for the surface chart.  <br/><br/></td></tr>
<tr>
<td>
{{'[ItemsSource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_ItemsSource)'| markdownify }}<br/><br/></td><td>
Gets or sets items source for surface chart.  <br/><br/></td></tr>
<tr>
<td>
{{'[XBindingPath](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_XBindingPath)'| markdownify }}<br/><br/></td><td>
Gets or sets a string that represents the X member path value of items source.  <br/><br/></td></tr>
<tr>
<td>
{{'[YBindingPath](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_YBindingPath)'| markdownify }}<br/><br/></td><td>
Gets or sets a string that represents the Y  member path value of items source.  <br/><br/></td></tr>
<tr>
<td>
{{'[ZBindingPath](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_ZBindingPath)'| markdownify }}<br/><br/></td><td>
Gets or sets a string that represents the Z  member path value of items source.  <br/><br/></td></tr>
<tr>
<td>
{{'[ColorBar](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_ColorBar)'| markdownify }}<br/><br/></td><td>
Gets or sets color bar for surface chart.  <br/><br/></td></tr>
<tr>
<td>
{{'[ApplyGradientBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_ApplyGradientBrush)'| markdownify }}<br/><br/></td><td>
Gets or sets the bool value that represents a value for applying the gradient brush in surface chart.  <br/><br/></td></tr>
<tr>
<td>
{{'[EnableZooming](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_EnableZooming)'| markdownify }}<br/><br/></td><td>
Gets or sets the bool value that represents a value to enable zooming in surface chart.  <br/><br/></td></tr>
<tr>
<td>
{{'[ShowContourLine](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_ShowContourLine)'| markdownify }}<br/><br/></td><td>
Gets or sets the bool value that represents a value whether to show the contour line for surface chart.  <br/><br/></td></tr>
<tr>
<td>
{{'[BrushCount](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_BrushCount)'| markdownify }}<br/><br/></td><td>
Gets or sets the double value that represents a value of brush count in surface chart.  <br/><br/></td></tr>
</table>

The following code sample explains the customization of the surface area. This customization of the SfSurfaceChart sets up a wireframe 3D surface chart that dynamically binds to data from the view model. It enhances the visual appearance with custom colors, rotation, tilt, and a perspective projection

{% tabs %}

{% highlight xaml %}

            <chart:SfSurfaceChart ItemsSource="{Binding DataValues}"            
                                  Type="WireframeSurface"
                                  XBindingPath="X" 
                                  YBindingPath="Y" 
                                  ZBindingPath="Z" 
                                  RowSize="{Binding RowSize}"
                                  ColumnSize="{Binding ColumnSize}" 
                                  ApplyGradientBrush="True" 
                                  BrushCount="4"
                                  LeftWallBrush="BlanchedAlmond" 
                                  WireframeStroke="Green" 
                                  WireframeStrokeThickness="1"
                                  CameraProjection="Perspective" 
                                  Tilt="10" 
                                  Rotate="20">
            </chart:SfSurfaceChart>

{% endhighlight %}

{% highlight c# %}

            SfSurfaceChart chart = new SfSurfaceChart();
            chart.Type = SurfaceType.WireframeSurface;
            chart.SetBinding(SfSurfaceChart.ItemsSourceProperty, "DataValues");
            chart.SetBinding(SfSurfaceChart.RowSizeProperty, "RowSize");
            chart.SetBinding(SfSurfaceChart.ColumnSizeProperty, "ColumnSize");
            chart.XBindingPath = "X";
            chart.YBindingPath = "Y";
            chart.ZBindingPath = "Z";
            chart.BrushCount = 4;
            chart.LeftWallBrush = new SolidColorBrush(Colors.BlanchedAlmond);
            chart.WireframeStroke = new SolidColorBrush(Colors.Green);
            chart.WireframeStrokeThickness = 1;
            chart.CameraProjection = CameraProjection.Perspective;
            chart.Tilt = 10;
            chart.Rotate = 20;
            grid.Children.Add(chart);

{% endhighlight %}

{% endtabs %}

![Area customization.](surface_chart_images/AreaCustomization.png)