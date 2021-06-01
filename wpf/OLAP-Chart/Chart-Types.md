---
layout: post
title: Chart Types in WPF Olap Chart control | Syncfusion
description: Learn about Chart Types support in Syncfusion Essential Studio WPF Olap Chart control, its elements and more details.
platform: wpf
control: OLAP Chart
 documentation: ug
---

# Chart Types in WPF Olap Chart

The OLAP chart supports the following 16 types of charts:

* Column
* Stacking column
* Stacking column 100
* Bar
* Stacking bar
* Stacking bar 100
* Area
* Stacking area
* Spline area
* Step area
* Line
* Spline
* Rotated spline
* Step line
* Scatter
* Pie

N> Chart type must be set before invoking the DataBind() method. Whenever you change the chart type, you need to call the DataBind() method to get the changes reflected.

## Column chart

Column chart is the most basic type of all charts. Column charts are widely used for comparison analysis.

![Column chart](Chart-types_images/Chart-types_img1.png)

The following code sample shows how to select a simple column chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart Name="olapChart" ChartType="Column" />

{% endhighlight %}

{% highlight c# %}

OlapChart olapChart = new OlapChart();
olapChart.ChartType = ChartTypes.Column;

{% endhighlight %}

{% highlight vbnet %}

Dim olapChart As OlapChart = New OlapChart()
olapChart.ChartType = ChartTypes.Column

{% endhighlight %}

{% endtabs %}

A sample demo is available at the following location.  

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Chart Types\Column Chart Demo

## Stacking column chart

The stacking column chart is a simple form of chart, which contains segments in each series. This chart type is widely used for proportional analysis over a particular period of time.

![StackingColumn chart](Chart-types_images/Chart-types_img2.png)

The following code sample shows how to select a stacking column chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart Name="olapChart" ChartType="StackingColumn" />

{% endhighlight %}

{% highlight c# %}

OlapChart olapChart = new OlapChart();
olapChart.ChartType = ChartTypes.StackingColumn;

{% endhighlight %}

{% highlight vbnet %}
  
Dim olapChart As OlapChart = New OlapChart()
olapChart.ChartType = ChartTypes.StackingColumn

{% endhighlight %}

{% endtabs %}

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Chart Types\Column Chart Demo

## Stacking column 100 chart

Stacking column 100 chart is a simple form of chart. Like stacking column chart, the stacking column 100 chart also contains segments in each series, which is added to equate each series to 100%. This chart type is widely used for proportional analysis over a particular period of time.

![StackingColumn100 chart](Chart-types_images/Chart-types_img3.png)

The following code sample shows how to select a stacking column 100 chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart Name="olapChart" ChartType="StackingColumn100" />

{% endhighlight %}

{% highlight c# %}
 
OlapChart olapChart = new OlapChart();
olapChart.ChartType = ChartTypes.StackingColumn100;

{% endhighlight %}

{% highlight vbnet %}
  
Dim olapChart As OlapChart = New OlapChart()
olapChart.ChartType = ChartTypes.StackingColumn100

{% endhighlight %}

{% endtabs %}

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Chart Types\Column Chart Demo

## Bar chart

The bar chart is same as the column chart, but it can be rotated to 90 degrees in the clockwise direction. This chart type is widely used for comparison analysis over a particular period of time.

![Bar chart](Chart-types_images/Chart-types_img4.png)

The following code sample shows how to select a bar chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart Name="olapChart" ChartType="Bar" />

{% endhighlight %}

{% highlight c# %}
 
OlapChart olapChart = new OlapChart();
olapChart.ChartType = ChartTypes.Bar;

{% endhighlight %}

{% highlight vbnet %}
  
Dim olapChart As OlapChart = New OlapChart()
olapChart.ChartType = ChartTypes.Bar

{% endhighlight %}

{% endtabs %}

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Chart Types\Bar Chart Demo

## Stacking bar chart

Stacking bar chart functions same as the stacking column chart, but it can be rotated to 90 degrees in the clockwise direction. This chart type is widely used for proportional analysis over a particular period of time.

![StackingBar chart](Chart-types_images/Chart-types_img5.png)

The following code sample shows how to select a stacking bar chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart Name="olapChart" ChartType="StackingBar" />

{% endhighlight %}

{% highlight c# %}
 
OlapChart olapChart = new OlapChart();
olapChart.ChartType = ChartTypes.StackingBar;

{% endhighlight %}

{% highlight vbnet %}

Dim olapChart As OlapChart = New OlapChart()
olapChart.ChartType = ChartTypes.StackingBar

{% endhighlight %}

{% endtabs %}

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Chart Types\Bar Chart Demo

## Stacking bar 100 chart

The stacking bar 100 chart functions same as the stacking column 100 chart, but it can be rotated to 90 degrees in the clockwise direction. This chart type is widely used for proportional analysis over a particular period of time.

![StackingBar100 chart](Chart-types_images/Chart-types_img6.png)

The following code sample shows how to select a stacking bar 100 chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart Name="olapChart" ChartType="StackingBar100" />

{% endhighlight %}

{% highlight c# %}

OlapChart olapChart = new OlapChart();
olapChart.ChartType = ChartTypes.StackingBar100;

{% endhighlight %}

{% highlight vbnet %}
  
Dim olapChart As OlapChart = New OlapChart()
olapChart.ChartType = ChartTypes.StackingBar100

{% endhighlight %}

{% endtabs %}

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Chart Types\Bar Chart Demo

## Area chart

The area chart fills the quantitative data over a period of time. It is mainly used to compare the quantity plotted over two or more series.

![Area chart](Chart-types_images/Chart-types_img7.png)

The following code sample shows how to select an area chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart Name="olapChart" ChartType="Area" />

{% endhighlight %}

{% highlight c# %}

OlapChart olapChart = new OlapChart();
olapChart.ChartType = ChartTypes.Area;

{% endhighlight %}

{% highlight vbnet %}
  
Dim olapChart As OlapChart = New OlapChart()
olapChart.ChartType = ChartTypes.Area

{% endhighlight %}

{% endtabs %}

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Chart Types\Area Chart Demo

## Stacking area chart

The stacking area chart fills the quantitative data over a period of time just like the line area chart, but it differs by the plotting method. In the stacking area chart, each series is plotted on the top of the previous series rather than starting from 0 of the horizontal axis. It is mainly used to compare the quantity plotted over two or more series.

![StackingArea chart](Chart-types_images/Chart-types_img8.png)

The following code sample shows how to select a stacking area chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart Name="olapChart" ChartType="StackingArea" />

{% endhighlight %}

{% highlight c# %}
 
OlapChart olapChart = new OlapChart();
olapChart.ChartType = ChartTypes.StackingArea;

{% endhighlight %}

{% highlight vbnet %}

Dim olapChart As OlapChart = New OlapChart()
olapChart.ChartType = ChartTypes.StackingArea

{% endhighlight %}

{% endtabs %}

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Chart Types\Area Chart Demo

## Spline area chart

The spline area chart is usually used in the case of approximating the intervals by using the spline curve. It is often used when data points are in limited number.

![SplineArea chart](Chart-types_images/Chart-types_img9.png)

The following code sample shows how to select a spline area chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart Name="olapChart" ChartType="SplineArea" />

{% endhighlight %}

{% highlight c# %}
 
OlapChart olapChart = new OlapChart();
olapChart.ChartType = ChartTypes.SplineArea;

{% endhighlight %}

{% highlight vbnet %}
  
Dim olapChart As OlapChart = New OlapChart()
olapChart.ChartType = ChartTypes.SplineArea

{% endhighlight %}

{% endtabs %}

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Chart Types\Area Chart Demo

## Step area chart

In the step area chart, the points are plotted instead of a straight line tracing the shortest path between points. The values are connected by continuous vertical and horizontal lines.

![StepArea chart](Chart-types_images/Chart-types_img10.png)

The following code sample shows how to select a step area chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart Name="olapChart" ChartType="StepArea" />

{% endhighlight %}

{% highlight c# %}
 
OlapChart olapChart = new OlapChart();
olapChart.ChartType = ChartTypes.StepArea;

{% endhighlight %}

{% highlight vbnet %}
  
Dim olapChart As OlapChart = New OlapChart()
olapChart.ChartType = ChartTypes.StepArea

{% endhighlight %}

{% endtabs %}

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Chart Types\Area Chart Demo

## Line chart

The line chart is a simple form of chart, which connects a series of data points. Usually, it is used for Trend analysis, Forecasting, or in the case of large data points.

![Line chart](Chart-types_images/Chart-types_img11.png)

The following code sample shows how to select a line chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart Name="olapChart" ChartType="Line" />

{% endhighlight %}

{% highlight c# %}
 
OlapChart olapChart = new OlapChart();
olapChart.ChartType = ChartTypes.Line;

{% endhighlight %}

{% highlight vbnet %}
  
Dim olapChart As OlapChart = New OlapChart()
olapChart.ChartType = ChartTypes.Line

{% endhighlight %}

{% endtabs %}
 
A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Chart Types\Line Chart Demo

## Spline chart

The spline chart is a simple form of chart, which connects the series of data points with an arc rather than a straight line. 

![Spline chart](Chart-types_images/Chart-types_img12.png)

The following code sample shows how to select a spline chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart Name="olapChart" ChartType="Spline" />

{% endhighlight %}

{% highlight c# %}
 
OlapChart olapChart = new OlapChart();
olapChart.ChartType = ChartTypes.Spline;

{% endhighlight %}

{% highlight vbnet %}
  
Dim olapChart As OlapChart = New OlapChart()
olapChart.ChartType = ChartTypes.Spline

{% endhighlight %}

{% endtabs %}

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Chart Types\Line Chart Demo

## Rotated spline chart

The rotated spline chart is similar to the spline chart, but it can be rotated to 90 degrees in the clockwise direction.

![RotatedSpline chart](Chart-types_images/Chart-types_img13.png)

The following code sample shows how to select a rotated spline chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart Name="olapChart" ChartType="RotatedSpline" />

{% endhighlight %}

{% highlight c# %}

OlapChart olapChart = new OlapChart();
olapChart.ChartType = ChartTypes.RotatedSpline;

{% endhighlight %}

{% highlight vbnet %}
  
Dim olapChart As OlapChart = New OlapChart()
olapChart.ChartType = ChartTypes.RotatedSpline

{% endhighlight %}

{% endtabs %}

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Chart Types\Line Chart Demo

## Step line chart

The step line chart is another form of chart, which connects the series of data points by using horizontal and vertical lines.

![StepLine chart](Chart-types_images/Chart-types_img14.png)

The following code sample shows how to select a step line chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart Name="olapChart" ChartType="StepLine" />

{% endhighlight %}

{% highlight c# %}
 
OlapChart olapChart = new OlapChart();
olapChart.ChartType = ChartTypes.StepLine;

{% endhighlight %}

{% highlight vbnet %}
  
Dim olapChart As OlapChart = New OlapChart()
olapChart.ChartType = ChartTypes.StepLine

{% endhighlight %}

{% endtabs %}

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Chart Types\Line Chart Demo

## Scatter chart

The scatter chart is a collection of points plotted in the rectangular co-ordinate system. It is often used in relationship analysis upto one independent variable.

![Scatter chart](Chart-types_images/Chart-types_img15.png)

The following code sample shows how to select a scatter chart.

{% tabs %} 

{% highlight xaml %}

<syncfusion:OlapChart Name="olapChart" ChartType="Scatter" />

{% endhighlight %}

{% highlight c# %}
 
OlapChart olapChart = new OlapChart();
olapChart.ChartType = ChartTypes.Scatter;

{% endhighlight %}

{% highlight vbnet %}

Dim olapChart As OlapChart = New OlapChart()
olapChart.ChartType = ChartTypes.Scatter

{% endhighlight %}

{% endtabs %}

A sample demo is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Chart Types\Scatter Chart Demo

## Pie chart

The pie chart renders the data points in segments. It can render only one series at a time. Usually, it is used for proportional analysis for a small set of data points.

![Pie chart](Chart-types_images/Chart-types_img16.png)

The following code sample shows how to select a pie chart.

{% tabs %}

{% highlight xaml %}

<syncfusion:OlapChart Name="olapChart" ChartType="Pie" />

{% endhighlight %}

{% highlight c# %}
 
OlapChart olapChart = new OlapChart();
olapChart.ChartType = ChartTypes.Pie;

{% endhighlight %}

{% highlight vbnet %}
  
Dim olapChart As OlapChart = New OlapChart()
olapChart.ChartType = ChartTypes.Pie

{% endhighlight %}

{% endtabs %}

N> The pie chart should not be used for comparison analysis of large data points, because it is harder for people to estimate angles rather than distance.

A sample demo is available at the following location:

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\WPF\OlapChart.WPF\Samples\Chart Types\Pie Chart Demo
