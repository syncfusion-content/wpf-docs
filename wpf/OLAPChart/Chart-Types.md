---
layout: post
title: Chart Types| OLAP Chart | Wpf | Syncfusion
description: Chart Types
platform: wpf
control: OLAP Chart
documentation: ug
---

# Chart Types

OlapChart includes a comprehensive set of more than 16 chart types for all your business needs.

The supported chart types are as follows: 

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

The default chart type is Column chart. The following illustration shows a column chart:

![](Core-Features_images/Core-Features_img16.png)


N> The ChartType must be set before invoking the DataBind() method. Whenever you change the ChartType, you need to call the DataBind() method to reflect the changes.

## How to create a simple column chart?

Column chart is the most basic type of chart. Column charts are widely used for comparison analysis.

The following illustration shows the basic column chart:

![](Core-Features_images/Core-Features_img17.png)


The following code snippet shows how to select a simple column chart:

  {% highlight xaml %}

   



<syncfusion:OlapChart Name="olapchart1" ChartType="Column" />

    {% endhighlight %}


  {% highlight c# %}

    



OlapChart olapChart = new OlapChart();

olapChart.ChartType = ChartTypes.Column;

    {% endhighlight %}






  {% highlight vbnet %}

   



Dim olapChart As OlapChart = New OlapChart()

olapChart.ChartType = ChartTypes.Column

    {% endhighlight %}






A sample, which demonstrates all the available type of Column charts, can be found in the following installation location:

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Chart Types\Column Chart Demo

## How to create a stacking column chart?

Stacking column chart is a simple form of chart, which contains segments in each series. This chart type is widely used for proportional analysis over a particular period of time.

The following illustration shows the stacking column chart:

![](Core-Features_images/Core-Features_img18.png)


The following code snippet shows how to select a stacking column chart:

  {% highlight xaml %}

   



<syncfusion:OlapChart Name="olapchart1" ChartType="StackingColumn" />

    {% endhighlight %}


  {% highlight c# %}

   



OlapChart olapChart = new OlapChart();

olapChart.ChartType = ChartTypes.StackingColumn;

    {% endhighlight %}





	
	{% highlight vbnet %}
  
   



Dim olapChart As OlapChart = New OlapChart()

olapChart.ChartType = ChartTypes.StackingColumn

 {% endhighlight %}







A sample, which demonstrates all the available type of Column charts, can be found in the following installation location:

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Chart Types\Column Chart Demo

## How to create a stacking column 100 chart?

Stacking column 100 chart is a simple form of chart.  Similar to the stacking column chart, the stacking column 100 chart contains segments in each series added so that each series is equated to 100%. This chart type is widely used for proportional analysis over a particular period of time.

The following illustration shows the stacking column 100 chart:

![](Core-Features_images/Core-Features_img19.png)


The following code snippet shows how to select a stacking column 100 chart:

	 {% highlight xaml %}

    



<syncfusion:OlapChart Name="olapchart1" ChartType="StackingColumn100" />

 {% endhighlight %}



 {% highlight c# %}
 
    




OlapChart olapChart = new OlapChart();

olapChart.ChartType = ChartTypes.StackingColumn100;

 {% endhighlight %}




 {% highlight vbnet %}
  
   



Dim olapChart As OlapChart = New OlapChart()

olapChart.ChartType = ChartTypes.StackingColumn100

 {% endhighlight %}


A sample, which demonstrates all the available type of Column charts, can be found in the following installation location:

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Chart Types\Column Chart Demo

## How to create a bar chart?

Bar chart is the same as the Column chart, the variation is it is rotated 90 degrees in the clockwise direction. This chart type is widely used for comparison analysis over a particular period of time.

The following illustration shows the simple bar chart:

![](Core-Features_images/Core-Features_img20.png)


The following code snippet shows how to select a bar chart:

	 {% highlight xaml %}

    



<syncfusion:OlapChart Name="olapchart1" ChartType="Bar" />

 {% endhighlight %}



 {% highlight c# %}
 
  



OlapChart olapChart = new OlapChart();

olapChart.ChartType = ChartTypes.Bar;

 {% endhighlight %}




 {% highlight vbnet %}
  
  



Dim olapChart As OlapChart = New OlapChart()

olapChart.ChartType = ChartTypes.Bar

 {% endhighlight %}

A sample, which demonstrates all the available type of Bar charts, can be found in the following installation location:

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Chart Types\Bar Chart Demo

## How to create a stacking bar chart?

StackingBar chart is the same as the StackingColumn chart, the variation is it is rotated 90 degrees in the clockwise direction. This chart type is widely used for proportional analysis over a particular period of time.

The following illustration shows the simple bar chart:

![](Core-Features_images/Core-Features_img21.png)


The following code snippet shows how to select a bar chart:

	 {% highlight xaml %}

    



<syncfusion:OlapChart Name="olapchart1" ChartType="StackingBar" />

 {% endhighlight %}



 {% highlight c# %}
 
   



OlapChart olapChart = new OlapChart();

olapChart.ChartType = ChartTypes.StackingBar;

 {% endhighlight %}




 {% highlight vbnet %}
  
   



Dim olapChart As OlapChart = New OlapChart()

olapChart.ChartType = ChartTypes.StackingBar

 {% endhighlight %}













A sample, which demonstrates all the available type of Bar charts, can be found in the following installation location:

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Chart Types\Bar Chart Demo

## How to create a stacking bar 100 chart?

StackingBar100 chart is the same as the StackingColumn100 chart, the variation is it is rotated 90 degree in the clockwise direction. This chart type is widely used for proportional analysis over a particular period of time.

The following illustration shows the StackingBar100 chart:

![](Core-Features_images/Core-Features_img22.png)


The following code snippet shows how to select a bar chart:

	 {% highlight xaml %}

    



<syncfusion:OlapChart Name="olapchart1" ChartType="StackingBar100" />

 {% endhighlight %}



 {% highlight c# %}
 
  



OlapChart olapChart = new OlapChart();

olapChart.ChartType = ChartTypes.StackingBar100;

 {% endhighlight %}




 {% highlight vbnet %}
  
   



Dim olapChart As OlapChart = New OlapChart()

olapChart.ChartType = ChartTypes.StackingBar100

 {% endhighlight %}


A sample, which demonstrates all the available type of Bar charts, can be found in the following installation location:

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Chart Types\Bar Chart Demo

## How to create an Area chart?

Area chart fills the quantitative data over a period of time. It is mainly used to compare the quantity plotted over two or more series.

The following illustration shows the simple Area chart:

![](Core-Features_images/Core-Features_img23.png)


The following code snippet shows how to select an Area chart:

	 {% highlight xaml %}

    



<syncfusion:OlapChart Name="olapchart1" ChartType="Area" />

 {% endhighlight %}



 {% highlight c# %}
 
   



OlapChart olapChart = new OlapChart();

olapChart.ChartType = ChartTypes.Area;

 {% endhighlight %}




 {% highlight vbnet %}
  
 



Dim olapChart As OlapChart = New OlapChart()

olapChart.ChartType = ChartTypes.Area

 {% endhighlight %}











A sample, which demonstrates all the available type of Area charts, can be found in the following installation location:

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Chart Types\Area Chart Demo

## How to create a stacking area chart?

StackingArea chart fills the quantitative data over a period of time just like the line Area chart. The variation in the StackingArea is while plotting the series. Each series is plotted on the top of the previous series rather than starting from 0 of the horizontal axis. It is mainly used to compare the quantity plotted over two or more series.

The following illustration shows the StackingArea chart:

![](Core-Features_images/Core-Features_img24.png)


The following code snippet shows how to select a StackingArea chart:

	 {% highlight xaml %}

    



<syncfusion:OlapChart Name="olapchart1" ChartType="StackingArea" />

 {% endhighlight %}



 {% highlight c# %}
 
  




OlapChart olapChart = new OlapChart();

olapChart.ChartType = ChartTypes.StackingArea;

 {% endhighlight %}




 {% highlight vbnet %}
  
   




Dim olapChart As OlapChart = New OlapChart()

olapChart.ChartType = ChartTypes.StackingArea

 {% endhighlight %}


A sample, which demonstrates all the available type of Area charts, can be found in the following installation location:

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Chart Types\Area Chart Demo

## How to create a spline area?

Spline area chart is usually used in the case of approximating the intervals by using spline curve. It is often used when data points are in limited number.

The following illustration shows the Spline area chart:

![](Core-Features_images/Core-Features_img25.png)


The following code snippet shows how to select a Spline area chart:

	 {% highlight xaml %}

   



<syncfusion:OlapChart Name="olapchart1" ChartType="SplineArea" />

 {% endhighlight %}



 {% highlight c# %}
 
    



OlapChart olapChart = new OlapChart();

olapChart.ChartType = ChartTypes.SplineArea;

 {% endhighlight %}




 {% highlight vbnet %}
  
   



Dim olapChart As OlapChart = New OlapChart()

olapChart.ChartType = ChartTypes.SplineArea

 {% endhighlight %}

A sample, which demonstrates all the available type of Area charts, can be found in the following installation location:

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Chart Types\Area Chart Demo

### How to create a step area?

In the Step area chart, the points are plotted instead of a straight line tracing the shortest path between points; the values are connected by continuous vertical and horizontal lines. 

The following illustration shows the Step area chart:

![](Core-Features_images/Core-Features_img26.png)


The following code snippet shows how to select a Step area chart:

	 {% highlight xaml %}

    



<syncfusion:OlapChart Name="olapchart1" ChartType="StepArea" />

 {% endhighlight %}



 {% highlight c# %}
 
   




OlapChart olapChart = new OlapChart();

olapChart.ChartType = ChartTypes.StepArea;

 {% endhighlight %}




 {% highlight vbnet %}
  
   



Dim olapChart As OlapChart = New OlapChart()

olapChart.ChartType = ChartTypes.StepArea

 {% endhighlight %}

A sample, which demonstrates all the available type of Area charts, can be found in the following installation location:

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Chart Types\Area Chart Demo

## How to create a line chart?

Line chart is a simple form of chart, which connects a series of data points. Usually, it is used for Trend analysis, Forcasting, or in the case of large data points.

The following illustration shows the Line chart:

![](Core-Features_images/Core-Features_img27.png)


The following code snippet shows how to select a Line chart:

	 {% highlight xaml %}

    



<syncfusion:OlapChart Name="olapchart1" ChartType="Line" />

 {% endhighlight %}



 {% highlight c# %}
 
  



OlapChart olapChart = new OlapChart();

olapChart.ChartType = ChartTypes.Line;

 {% endhighlight %}




 {% highlight vbnet %}
  
 



Dim olapChart As OlapChart = New OlapChart()

olapChart.ChartType = ChartTypes.Line

 {% endhighlight %}

A sample, which demonstrates all the available type of Line charts, can be found in the following installation location.

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Chart Types\Line Chart Demo

## How to create a spline chart?

Spline chart is a simple form of chart, which connects the series of data points with an arc rather than a straight line. 

The following illustration shows the Spline chart:

![](Core-Features_images/Core-Features_img28.png)


The following code snippet shows how to select a Spline chart:

	 {% highlight xaml %}

    



<syncfusion:OlapChart Name="olapchart1" ChartType="Spline" />

 {% endhighlight %}



 {% highlight c# %}
 
   



OlapChart olapChart = new OlapChart();

olapChart.ChartType = ChartTypes.Spline;

 {% endhighlight %}




 {% highlight vbnet %}
  
    



Dim olapChart As OlapChart = New OlapChart()

olapChart.ChartType = ChartTypes.Spline

 {% endhighlight %}


A sample, which demonstrates all the available type of Line charts, can be found in the following installation location:

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Chart Types\Line Chart Demo

## How to create a rotate spline chart?

RotatedSpline chart is similar to the Spline chart, but is rotated 90 degrees in the clockwise direction.

The following illustration shows the RotatedSpline chart:

![](Core-Features_images/Core-Features_img29.png)


The following code snippet shows how to select a RotatedSpline chart.

	 {% highlight xaml %}

    



<syncfusion:OlapChart Name="olapchart1" ChartType="RotatedSpline" />

 {% endhighlight %}



 {% highlight c# %}
 
    



OlapChart olapChart = new OlapChart();

olapChart.ChartType = ChartTypes.RotatedSpline;

 {% endhighlight %}




 {% highlight vbnet %}
  
   



Dim olapChart As OlapChart = New OlapChart()

olapChart.ChartType = ChartTypes.RotatedSpline

 {% endhighlight %}













A sample, which demonstrates all the available type of Line charts, can be found in the following installation location:

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Chart Types\Line Chart Demo

## How to create a step line chart?

StepLine chart is another form of chart, which connects the series of data points by using horizontal and vertical lines.

The following illustration shows the StepLine chart:

![](Core-Features_images/Core-Features_img30.png)


The following code snippet shows how to select a StepLine chart:

	 {% highlight xaml %}

   



<syncfusion:OlapChart Name="olapchart1" ChartType="StepLine" />

 {% endhighlight %}



 {% highlight c# %}
 
  



OlapChart olapChart = new OlapChart();

olapChart.ChartType = ChartTypes.StepLine;

 {% endhighlight %}




 {% highlight vbnet %}
  
   



Dim olapChart As OlapChart = New OlapChart()

olapChart.ChartType = ChartTypes.StepLine

 {% endhighlight %}















A sample, which demonstrates all the available type of Line charts, can be found in the following installation location:

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Chart Types\Line Chart Demo

## How to create a scatter chart?

Scatter chart is a collection of points plotted in the rectangular co-ordinate system. It is often used in relationship analysis upto one independent variable.

The following illustration shows the Scatter chart:

![](Core-Features_images/Core-Features_img31.png)


The following code snippet shows how to select a Scatter chart:

	 {% highlight xaml %}

    

<syncfusion:OlapChart Name="olapchart1" ChartType="Scatter" />

 {% endhighlight %}



 {% highlight c# %}
 
  



OlapChart olapChart = new OlapChart();

olapChart.ChartType = ChartTypes.Scatter;



 {% endhighlight %}




 {% highlight vbnet %}
  
    



Dim olapChart As OlapChart = New OlapChart()

olapChart.ChartType = ChartTypes.Scatter

 {% endhighlight %}


A sample, which demonstrates the Scatter chart, can be found in the following installation location:

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Chart Types\Scatter Chart Demo

## How to create a pie chart?

Pie chart renders the data points in segments. It is capable of rendering only one series at a time. Usually, it is used for proportional analysis for a small set of data points.

The following illustration shows the Pie chart:

![](Core-Features_images/Core-Features_img32.png)


The following code snippet shows how to select a Pie chart:

	 {% highlight xaml %}

   



<syncfusion:OlapChart Name="olapchart1" ChartType="Pie" />

 {% endhighlight %}



 {% highlight c# %}
 
    



OlapChart olapChart = new OlapChart();

olapChart.ChartType = ChartTypes.Pie;

 {% endhighlight %}




 {% highlight vbnet %}
  
   



Dim olapChart As OlapChart = New OlapChart()

olapChart.ChartType = ChartTypes.Pie

 {% endhighlight %}


N> Pie chart should not be used for Comparison analysis of large data points, because it is harder for people to estimate angles rather than distance.

A sample, which demonstrates the Pie chart, can be found in the following installation location:

..\Syncfusion\<Version Number>\BI\WPF\OlapChart.WPF\Samples\Chart Types\Pie Chart Demo
