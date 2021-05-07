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


The following APIs are used to customize the surface axis. 

### Properties

<table>
<tr>
<th>
Name</th><th>
Definition</th></tr>
<tr>
<td>
Header<br/><br/></td><td>
Gets or sets the object that represents the content of a surface axis header. This property is used to specify any object as Header for surface axis.<br/><br/></td></tr>
<tr>
<td>
HeaderTemplate <br/><br/></td><td>
Gets or sets template for surface axis header.<br/><br/></td></tr>
<tr>
<td>
LabelTemplate<br/><br/></td><td>
Gets or sets template for surface axis label.<br/><br/></td></tr>
<tr>
<td>
LabelFormat<br/><br/></td><td>
Gets or sets format for surface axis label.<br/><br/></td></tr>
<tr>
<td>
Minimum<br/><br/></td><td>
Gets or sets the double that represents the minimum value for the axis. <br/><br/></td></tr>
<tr>
<td>
Maximum<br/><br/></td><td>
Gets or sets the double that represents the maximum value for the axis.<br/><br/></td></tr>
<tr>
<td>
RangePadding <br/><br/></td><td>
Gets or sets NumericalPadding that specifies how to render the surface in surface area.  <br/><br/></td></tr>
<tr>
<td>
EdgeLabelsDrawingMode<br/><br/></td><td>
Gets or sets EdgeLabelsDrawingMode that specifies how to place edge axis label. <br/><br/></td></tr>
<tr>
<td>
Interval<br/><br/></td><td>
Gets or sets the double that represents the interval between labels.<br/><br/></td></tr>
<tr>
<td>
SmallTicksPerInterval<br/><br/></td><td>
Gets or sets the double that represents the small ticks per interval. <br/><br/></td></tr>
<tr>
<td>
TickLineSize<br/><br/></td><td>
Gets or sets the double that represents the axis tick line size. <br/><br/></td></tr>
<tr>
<td>
ShowGridLines<br/><br/></td><td>
Gets or sets bool that represent whether displaying the axis grid lines. <br/><br/></td></tr>
<tr>
<td>
GridLineStroke<br/><br/></td><td>
Gets or sets the brush for grid line stroke. <br/><br/></td></tr>
<tr>
<td>
GridLineThickness<br/><br/></td><td>
Gets or sets the double for grid line thickness. <br/><br/></td></tr>
<tr>
<td>
AxisLineStyle<br/><br/></td><td>
Gets or sets the style for axis line.  <br/><br/></td></tr>
<tr>
<td>
MajorTickLineStyle<br/><br/></td><td>
Gets or sets the style for axis major tick lines.  <br/><br/></td></tr>
<tr>
<td>
MinorTickLineStyle<br/><br/></td><td>
Gets or sets the style for axis minor tick lines.  <br/><br/></td></tr>
</table>
