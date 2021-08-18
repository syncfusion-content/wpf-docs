---
layout: post
title: Surface Axis in WPF Surface Chart control | Syncfusion
description: Learn here all about Surface Axis support in Syncfusion WPF Surface Chart (SfSurfaceChart) control and more.
platform: wpf
control: SfSurfaceChart
documentation: ug
---

# Surface Axis in WPF Surface Chart (SfSurfaceChart)

SurfaceAxis is used to locate a data point inside the surface area. In surface, you require three axis to locate data points, such as X-Axis, Y-Axis and Z-Axis. You can define axis in surface using the following code example. If you do not define the axis, then it automatically takes the default axis with default properties values.

XAML:

{% tabs %}

{% highlight xaml %}

	<chart:SfSurfaceChart>

	<chart:SfSurfaceChart.XAxis>
	
		<chart:SurfaceAxis  />
		
	</chart:SfSurfaceChart.XAxis>

	<chart:SfSurfaceChart.YAxis>
	
		<chart:SurfaceAxis />
		
	</chart:SfSurfaceChart.YAxis>

	<chart:SfSurfaceChart.ZAxis>
	
		<chart:SurfaceAxis />
		
	</chart:SfSurfaceChart.ZAxis>
	
	<chart:SfSurfaceChart />
	
{% endhighlight %}

{% highlight c# %}

SfSurfaceChart surface = new SfSurfaceChart();

surface.XAxis = new SurfaceAxis();

surface.YAxis = new SurfaceAxis();

surface.ZAxis = new SurfaceAxis();
	
{% endhighlight %}

{% endtabs %}

## Axis customization.

Axis of the surface chart can be customized using the following properties.

The following APIs are used to customize the surface axis. 

### Properties

<table>
<tr>
<th>
Name</th><th>
Definition</th></tr>
<tr>
<td>
[`Header`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceAxis.html#Syncfusion_UI_Xaml_Charts_SurfaceAxis_Header)<br/><br/></td><td>
Gets or sets the object that represents the content of a surface axis header. This property is used to specify any object as Header for surface axis.<br/><br/></td></tr>
<tr>
<td>
[`HeaderTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceAxis.html#Syncfusion_UI_Xaml_Charts_SurfaceAxis_HeaderTemplate) <br/><br/></td><td>
Gets or sets template for surface axis header.<br/><br/></td></tr>
<tr>
<td>
[`LabelTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceAxis.html#Syncfusion_UI_Xaml_Charts_SurfaceAxis_LabelTemplate)<br/><br/></td><td>
Gets or sets template for surface axis label.<br/><br/></td></tr>
<tr>
<td>
[`LabelFormat`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceAxis.html#Syncfusion_UI_Xaml_Charts_SurfaceAxis_LabelFormat)<br/><br/></td><td>
Gets or sets format for surface axis label.<br/><br/></td></tr>
<tr>
<td>
[`Minimum`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceAxis.html#Syncfusion_UI_Xaml_Charts_SurfaceAxis_Minimum)<br/><br/></td><td>
Gets or sets the double that represents the minimum value for the axis. <br/><br/></td></tr>
<tr>
<td>
[`Maximum`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceAxis.html#Syncfusion_UI_Xaml_Charts_SurfaceAxis_Maximum)<br/><br/></td><td>
Gets or sets the double that represents the maximum value for the axis.<br/><br/></td></tr>
<tr>
<td>
[`RangePadding`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceAxis.html#Syncfusion_UI_Xaml_Charts_SurfaceAxis_RangePadding) <br/><br/></td><td>
Gets or sets NumericalPadding that specifies how to render the surface in surface area.  <br/><br/></td></tr>
<tr>
<td>
[`EdgeLabelsDrawingMode`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceAxis.html#Syncfusion_UI_Xaml_Charts_SurfaceAxis_EdgeLabelsDrawingMode)<br/><br/></td><td>
Gets or sets EdgeLabelsDrawingMode that specifies how to place edge axis label. <br/><br/></td></tr>
<tr>
<td>
[`Interval`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceAxis.html#Syncfusion_UI_Xaml_Charts_SurfaceAxis_HeaderTemplate)<br/><br/></td><td>
Gets or sets the double that represents the interval between labels.<br/><br/></td></tr>
<tr>
<td>
[`SmallTicksPerInterval`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceAxis.html#Syncfusion_UI_Xaml_Charts_SurfaceAxis_SmallTicksPerInterval)<br/><br/></td><td>
Gets or sets the double that represents the small ticks per interval. <br/><br/></td></tr>
<tr>
<td>
[`TickLineSize`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceAxis.html#Syncfusion_UI_Xaml_Charts_SurfaceAxis_TickLineSize)<br/><br/></td><td>
Gets or sets the double that represents the axis tick line size. <br/><br/></td></tr>
<tr>
<td>
[`ShowGridLines`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceAxis.html#Syncfusion_UI_Xaml_Charts_SurfaceAxis_RangePadding)<br/><br/></td><td>
Gets or sets bool that represent whether displaying the axis grid lines. <br/><br/></td></tr>
<tr>
<td>
[`GridLineStroke`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceAxis.html#Syncfusion_UI_Xaml_Charts_SurfaceAxis_GridLineStroke)<br/><br/></td><td>
Gets or sets the brush for grid line stroke. <br/><br/></td></tr>
<tr>
<td>
[`GridLineThickness`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceAxis.html#Syncfusion_UI_Xaml_Charts_SurfaceAxis_GridLineThickness)<br/><br/></td><td>
Gets or sets the double for grid line thickness. <br/><br/></td></tr>
<tr>
<td>
[`AxisLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceAxis.html#Syncfusion_UI_Xaml_Charts_SurfaceAxis_AxisLineStyle)<br/><br/></td><td>
Gets or sets the style for axis line.  <br/><br/></td></tr>
<tr>
<td>
[`MajorTickLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceAxis.html#Syncfusion_UI_Xaml_Charts_SurfaceAxis_MajorTickLineStyle)<br/><br/></td><td>
Gets or sets the style for axis major tick lines.  <br/><br/></td></tr>
<tr>
<td>
[`MinorTickLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SurfaceAxis.html#Syncfusion_UI_Xaml_Charts_SurfaceAxis_MinorTickLineStyle)<br/><br/></td><td>
Gets or sets the style for axis minor tick lines.  <br/><br/></td></tr>
</table>

The following code snippet explains how to customize the axis using the above properties.

{% tabs %}

{% highlight xaml %}

  		<Grid.Resources>
            <DataTemplate x:Key="labelTemplate">
                <TextBlock Text="{Binding LabelContent}" Foreground="Red"></TextBlock>
            </DataTemplate>

            <DataTemplate x:Key="headerTemplate">
                <TextBlock Text="YAxis" FontFamily="Comic Sans MS"></TextBlock>
            </DataTemplate>

            <Style TargetType="Line" x:Key="lineStyle">
                <Setter Property="Stroke" Value="Green"/>
                <Setter Property="StrokeThickness" Value="2"/>
            </Style>
        </Grid.Resources>


 	<chart:SfSurfaceChart ItemsSource="{Binding DataValues}"  XBindingPath="X"  Type="Surface"
                              YBindingPath="Y" ZBindingPath="Z" RowSize="{Binding RowSize}"
                              ColumnSize="{Binding ColumnSize}">

            <chart:SfSurfaceChart.XAxis>

                <chart:SurfaceAxis  GridLineStroke="Red" GridLineThickness="1" 
                                   SmallTicksPerInterval="1" Header="XAxis" AxisLineStyle="{StaticResource lineStyle }"
                                    LabelTemplate="{StaticResource labelTemplate}">  
                </chart:SurfaceAxis>

            </chart:SfSurfaceChart.XAxis>

            <chart:SfSurfaceChart.YAxis>
                <chart:SurfaceAxis HeaderTemplate="{StaticResource headerTemplate}" />
            </chart:SfSurfaceChart.YAxis>

            <chart:SfSurfaceChart.ZAxis>
                <chart:SurfaceAxis />
            </chart:SfSurfaceChart.ZAxis>

            </chart:SfSurfaceChart>


{% endhighlight %}

{% highlight c# %}

            chart = new SfSurfaceChart();
            chart.Type = SurfaceType.Surface;
            chart.SetBinding(SfSurfaceChart.ItemsSourceProperty, "DataValues");
            chart.SetBinding(SfSurfaceChart.RowSizeProperty, "RowSize");
            chart.SetBinding(SfSurfaceChart.ColumnSizeProperty, "ColumnSize");
            chart.XBindingPath = "X";
            chart.YBindingPath = "Y";
            chart.ZBindingPath = "Z";

            SurfaceAxis xAxis = new SurfaceAxis();
            xAxis.Header = "X-Axis";
            chart.XAxis = xAxis;

            xAxis.GridLineStroke = new SolidColorBrush(Colors.Red);
            xAxis.GridLineThickness = 1;
            xAxis.SmallTicksPerInterval = 1;           
            xAxis.AxisLineStyle = grid.Resources["lineStyle"] as Style;
            xAxis.LabelTemplate = grid.Resources["labelTemplate"] as DataTemplate;

            SurfaceAxis yAxis = new SurfaceAxis();
            yAxis.Header = "Y-Axis";
            chart.YAxis = yAxis;

            yAxis.HeaderTemplate = grid.Resources["headerTemplate"] as DataTemplate;

            SurfaceAxis zAxis = new SurfaceAxis();
            zAxis.Header = "Z-Axis";
            chart.ZAxis = zAxis;

            grid.Children.Add(chart);

{% endhighlight %}

{% endtabs %}

![Axis customization](surface_chart_images/AxisCustomization.png)