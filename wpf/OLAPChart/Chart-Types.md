---
layout: post
title: Chart Types| OlapChart | Wpf | Syncfusion
description: Chart Types
platform: wpf
control: OlapChart
documentation: ug
---

# Chart Types

OlapChart supports 16 different types of Charts as follows:

* Column
* StackingColumn
* StackingColumn100
* Bar
* StackingBar
* StackingBar100
* Area
* StackingArea
* SplineArea
* StepArea
* Line
* Spline
* RotatedSpline
* StepLine
* Scatter
* Pie

N> Chart type must be set before invoking the DataBind() method. Whenever you change the Chart type, you need to call the DataBind() method to get the changes reflected.

## Column Chart

Column chart is the most basic type of all charts. Column charts are widely used for comparison analysis.

![](Chart-types_images/Chart-types_img1.png)

The following code sample shows how to select a simple Column chart:

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

A sample demo is available at the following link:  

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapChart.WPF\Samples\Chart Types\Column Chart Demo

## Stacking Column Chart

Stacking Column Chart is a simple form of chart, which contains segments in each series. This chart type is widely used for proportional analysis over a particular period of time.

![](Chart-types_images/Chart-types_img2.png)

The following code sample shows how to select a Stacking Column chart:

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

A sample demo is available at the following link:  

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapChart.WPF\Samples\Chart Types\Column Chart Demo

## Stacking Column 100 Chart

Stacking Column 100 Chart is a simple form of chart.  Similar to the Stacking Column chart, the Stacking Column 100 chart contains segments in each series added so that each series is equated to 100%. This chart type is widely used for proportional analysis over a particular period of time.

![](Chart-types_images/Chart-types_img3.png)

The following code sample shows how to select a Stacking Column 100 chart:

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

A sample demo is available at the following link:  

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapChart.WPF\Samples\Chart Types\Column Chart Demo

## Bar Chart

Bar Chart is the same as the Column chart, the variation is it is rotated 90 degrees in the clockwise direction. This chart type is widely used for comparison analysis over a particular period of time.

![](Chart-types_images/Chart-types_img4.png)

The following code sample shows how to select a Bar chart:

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

A sample demo is available at the following link: 

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapChart.WPF\Samples\Chart Types\Bar Chart Demo

## Stacking Bar Chart

Stacking Bar Chart is the same as the Stacking Column chart, the variation is it is rotated 90 degrees in the clockwise direction. This chart type is widely used for proportional analysis over a particular period of time.

![](Chart-types_images/Chart-types_img5.png)

The following code sample shows how to select a Stacking Bar chart:

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

A sample demo is available at the following link: 

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapChart.WPF\Samples\Chart Types\Bar Chart Demo

## Stacking Bar 100 Chart

Stacking Bar 100 Chart is the same as the Stacking Column 100 chart, the variation is it is rotated 90 degree in the clockwise direction. This chart type is widely used for proportional analysis over a particular period of time.

![](Chart-types_images/Chart-types_img6.png)

The following code sample shows how to select a Stacking Bar 100 chart:

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

A sample demo is available at the following link: 

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapChart.WPF\Samples\Chart Types\Bar Chart Demo

## Area Chart

Area Chart fills the quantitative data over a period of time. It is mainly used to compare the quantity plotted over two or more series.

![](Chart-types_images/Chart-types_img7.png)

The following code sample shows how to select an Area chart:

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

A sample demo is available at the following link:

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapChart.WPF\Samples\Chart Types\Area Chart Demo

## Stacking Area Chart

Stacking Area Chart fills the quantitative data over a period of time just like the line Area chart. The variation in the StackingArea is while plotting the series. Each series is plotted on the top of the previous series rather than starting from 0 of the horizontal axis. It is mainly used to compare the quantity plotted over two or more series.

![](Chart-types_images/Chart-types_img8.png)

The following code sample shows how to select a Stacking Area chart:

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

A sample demo is available at the following link:

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapChart.WPF\Samples\Chart Types\Area Chart Demo

## Spline Area Chart

Spline Area Chart is usually used in the case of approximating the intervals by using spline curve. It is often used when data points are in limited number.

![](Chart-types_images/Chart-types_img9.png)

The following code sample shows how to select a Spline Area chart:

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

A sample demo is available at the following link:

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapChart.WPF\Samples\Chart Types\Area Chart Demo

## Step Area Chart

In the Step Area Chart, the points are plotted instead of a straight line tracing the shortest path between points; the values are connected by continuous vertical and horizontal lines. 

![](Chart-types_images/Chart-types_img10.png)

The following code sample shows how to select a Step Area chart:

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

A sample demo is available at the following link:

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapChart.WPF\Samples\Chart Types\Area Chart Demo

## Line Chart

Line Chart is a simple form of chart, which connects a series of data points. Usually, it is used for Trend analysis, Forecasting, or in the case of large data points.

![](Chart-types_images/Chart-types_img11.png)

The following code sample shows how to select a Line chart:

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
 
A sample demo is available at the following link:

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapChart.WPF\Samples\Chart Types\Line Chart Demo

## Spline Chart

Spline Chart is a simple form of chart, which connects the series of data points with an arc rather than a straight line. 

![](Chart-types_images/Chart-types_img12.png)

The following code sample shows how to select a Spline chart:

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

A sample demo is available at the following link:

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapChart.WPF\Samples\Chart Types\Line Chart Demo

## Rotated Spline Chart

Rotated Spline Chart is similar to the Spline chart, but is rotated 90 degrees in the clockwise direction.

![](Chart-types_images/Chart-types_img13.png)

The following code sample shows how to select a Rotated Spline chart.

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

A sample demo is available at the following link:

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapChart.WPF\Samples\Chart Types\Line Chart Demo

## Step Line Chart

Step Line Chart is another form of chart, which connects the series of data points by using horizontal and vertical lines.

![](Chart-types_images/Chart-types_img14.png)

The following code sample shows how to select a Step Line chart:

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

A sample demo is available at the following link:

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapChart.WPF\Samples\Chart Types\Line Chart Demo

## Scatter Chart

Scatter Chart is a collection of points plotted in the rectangular co-ordinate system. It is often used in relationship analysis upto one independent variable.

![](Chart-types_images/Chart-types_img15.png)

The following code sample shows how to select a Scatter chart:

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

A sample demo is available at the following link:

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapChart.WPF\Samples\Chart Types\Scatter Chart Demo

## Pie Chart

Pie Chart renders the data points in segments. It is capable of rendering only one series at a time. Usually, it is used for proportional analysis for a small set of data points.

![](Chart-types_images/Chart-types_img16.png)

The following code sample shows how to select a Pie chart:

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

N> Pie Chart should not be used for Comparison analysis of large data points, because it is harder for people to estimate angles rather than distance.

A sample demo is available at the following link:

{system drive}:\Users\\{User Name}\AppData\Local\Syncfusion\EssentialStudio\\{Version Number}\WPF\OlapChart.WPF\Samples\Chart Types\Pie Chart Demo
