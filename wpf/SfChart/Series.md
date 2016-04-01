---
layout: post
title: Series| SfChart | Wpf | Syncfusion
description: series
platform: wpf
control: SfChart
documentation: ug
---

# Series

ChartSeries is the visual representation of the data. SfChart offers many types of series ranging from LineSeries to FinancialSeries like HiLo and Candle. Based on your requirements and specifications, any type of Series can be added for data visualization. 

The following APIs are common for the most of the series types:

* XBindingPath-A string property that represents the X values for the series.
* YBindingPath-A string property that represents the Y values for the series.
* Stroke-Represents the brush for the series outline.
* StrokeThickness-Represents the thickness of the for the series outline.
* Interior-Represents the brush to fill the series.
* Palette-Used to define the set of pre-defined color for the series.

## Column and Bar Charts

### Column

Column charts plot discrete rectangles for the given values. The following code example demonstrates the usage of [`ColumnSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ColumnSeries.html#).

{% highlight xaml %}

<chart:ColumnSeries Interior="#7F7F7F"ItemsSource="{Binding SneakersDetail}"           

XBindingPath="Brand" YBindingPath="ItemsCount1"   />

{% endhighlight %}

![](Series_images/column.png)

### Bar

Bar series are similar to column series, excepts its orientation. The following code examples shows how to use [`BarSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.BarSeries.html#).

{% highlight xaml %}

<chart:BarSeries ItemsSource="{Binding CategoricalDatas}" XBindingPath="Category" 

YBindingPath="Value" Interior="#7F7F7F" />

{% endhighlight %}

![](Series_images/bar.png)

## Line and Spline Charts

### Line

Line series join points on a plot by straight lines, showing data trends at equal intervals. The following code example explains how to create a simple [`LineSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.LineSeries.html#) using given data

{% highlight xaml %}

<chart:LineSeries  XBindingPath="Year

ItemsSource="{Binding List}" YBindingPath="India"               

Interior="#4A4A4A"/>

<chart:LineSeries  XBindingPath="Year"     

ItemsSource="{Binding List}" YBindingPath="America"               

Interior="#4A4A4A"/>

{% endhighlight %}

![](Series_images/line.png)


### Spline

[`SplineSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.SplineSeries.html#) resembles line series, but the difference between them is that instead of connecting the data points with line segments, the data points are connected by smooth Bezier curves.

{% highlight xaml %}

<chart:SplineSeries  XBindingPath="Year"     

ItemsSource="{Binding List}" YBindingPath="India"               

Interior="#4A4A4A"/>

<chart:SplineSeries  XBindingPath="Year"     

ItemsSource="{Binding List}" YBindingPath="America"               

Interior="#4A4A4A"/>

{% endhighlight %}

![](Series_images/spline.png)


## Bubble and Scatter 

### Bubble

[`BubbleSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.BubbleSeries.html#) is represented by closely packed circles, whose areas are proportional to the quantities. 

The size of the bubble series is relative proportional to the value bind with the series using [`Size`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.BubbleSeries~Size.html#)  property. You can set the constraints on this size using [`MinimumRadius`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.BubbleSeries~MaximumRadius.html#) and [`MaximumRadius`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.BubbleSeries~MaximumRadius.html#).

{% highlight xaml %}

<chart:BubbleSeries  ItemsSource="{Binding Fruits}"  XBindingPath="FruitName" 

YBindingPath="People"   Size="Size" MinimumRadius="5" 

MaximumRadius="10"

Interior="#BCBCBC" />

{% endhighlight %}

![](Series_images/bubble.png)

### Scatter

[`ScatterSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ScatterSeries.html#) is similar to bubble series, where each point being represented by an ellipse with equal size. This size can be defined using [`ScatterHeight`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ScatterSeries~ScatterHeight.html#) and [`ScatterWidth`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ScatterSeries~ScatterWidth.html#) property.

{% highlight xaml %}

<chart:ScatterSeries Interior="#4A4A4A" ScatterHeight="4" ScatterWidth="4" 

ItemsSource="{Binding DataPoints}" XBindingPath="Eruptions 

YBindingPath="WaitingTime"/>

{% endhighlight %}

![](Series_images/scatter.png)

## Area Charts

### Area

[`AreaSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.AreaSeries.html#) is rendered using a collection of line segments connected to form a closed loop area, filled with the specified color.

The following code example initializes the AreaSeries:

{% highlight xaml %}

<chart:AreaSeries XBindingPath="FruitName" Interior="#BCBCBC" 

YBindingPath="People" ItemsSource="{Binding Fruits}" >   

{% endhighlight %}

![](Series_images/area.png)

### Spline Area

[`SplineAreaSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.SplineAreaSeries.html#) connects a series of data points using smooth Bezier line curves, with the underlying areas filled. 

{% highlight xaml %}

<chart:SplineAreaSeries Interior="#7F7F7F"              

ItemsSource="{Binding Products}" XBindingPath="ProdName"     

YBindingPath="Price" />

{% endhighlight %}

![](Series_images/splinearea.png)


### Step Area

[`StepAreaSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.StepAreaSeries.html#) is similar to AreaSeries but it does not use the shortest distance to connect two data points using Bezier curves. Instead, this ChartSeries uses vertical and horizontal lines to connect the data points in a series forming a step-like progression.

{% highlight xaml %}

<chart:StepAreaSeries  Interior="#7F7F7F"  

ItemsSource="{Binding SneakersDetail}" XBindingPath="Brand" 

YBindingPath="ItemsCount"/>

{% endhighlight %}

![](Series_images/steparea.png)

### Closed Area

If you wish to draw the open area series (Area with stroke only at top), SfChart provides [`IsClosed`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.AreaSeries~IsClosed.html#) property. By default, this property is true.

{% highlight xaml %}

<chart:AreaSeries  IsClosed="False"

XBindingPath="FruitName" Interior="#BCBCBC" 

YBindingPath="People" ItemsSource="{Binding Fruits}" /> 

{% endhighlight %}

![](Series_images/closedarea.png)


## Pie and Doughnut Charts

### Pie

[`PieSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.PieSeries.html#) is divided into sectors, illustrating numerical proportion. The following code example illustrates the PieSeries.

{% highlight xaml %}

<chart:PieSeries  Palette="Custom"

XBindingPath="Category" 

ItemsSource="{Binding Tax}" 

YBindingPath="Percentage"/>

{% endhighlight %}

![](Series_images/pie.png)

The rendering size of the PieSeries can be controlled using [`PieCoefficient`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.PieSeries~PieCoefficient.html#) property as in below code example.

{% highlight xaml %}

<chart:PieSeries PieCoefficient="0.9" Palette="Custom"

XBindingPath="Category" 

ItemsSource="{Binding Tax}" 

YBindingPath="Percentage"/>

{% endhighlight %}

![](Series_images/pie_1.png)

### Doughnut

[`DoughnutSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.DoughnutSeries.html#) is similar to PieSeries. It is used to show the relationship between parts of data and whole data. 

The DoughnutSeries can be added to chart as in below code example:

{% highlight xaml %}

<chart:DoughnutSeries Palette="Custom"

XBindingPath="Category"

ItemsSource="{Binding Tax}" 

YBindingPath="Percentage"/>

{% endhighlight %}


![](Series_images/doughnut.png)

The Doughnut also having coefficient property, [`DoughnutCoefficient`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.DoughnutSeries~DoughnutCoefficient.html#) which defines the inner circle. Also it has [`DoughnutSize`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.DoughnutSeries~DoughnutSize.html#), used to define the size for this series like [`PieCoefficient`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.PieSeries~PieCoefficient.html#) in PieSeries.

{% highlight xaml %}

<chart:DoughnutSeries x:Name="DouughnutSeries" DoughnutCoefficient="0.7"                    

Palette="Custom"

XBindingPath="Category" ItemsSource="{Binding Tax}" 

Label="Tax" YBindingPath="Percentage" />

{% endhighlight %}

![](Series_images/doughnut_1.png)

### Semi Pie and Doughnut

By having custom [`StartAngle`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CircularSeriesBase~StartAngle.html#) and [`EndAngle`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CircularSeriesBase~EndAngle.html#), you can draw pie series in different shapes like semicircular or quarter circular series.

{% highlight xaml %}

<syncfusion:PieSeries x:Name="PieSeries" StartAngle="180" EndAngle="360"    

XBindingPath="Utilization" 

YBindingPath="ResponseTime"

ItemsSource="{Binding}"

Palette="Custom"/>

{% endhighlight %}

![](Series_images/semipie.png)

{% highlight xaml %}

<syncfusion:DoughnutSeries Palette="Custom"

StartAngle="180" EndAngle="360" 

XBindingPath="Utilization"

YBindingPath="ResponseTime" 

ItemsSource="{Binding}"/>

{% endhighlight %}

![](Series_images/semidoughnut.png)

### Explode Segments

The following properties are used to explode the individual segments in Pie, Doughnut, Funnel and Pyramid.

* ExplodeAll  - Used to explode all the segments of these series.
* ExplodeIndex - Used to explode any specific segment.
* ExplodeRadius- Used to define the explode distance.

**Explode** **Index**

{% highlight xaml %}

<syncfusion:PieSeries x:Name="PieSeries" ItemsSource="{Binding}"          

ExplodeIndex="2"

ExplodeRadius="10"

XBindingPath="Utilization" 

YBindingPath="ResponseTime" 

Palette="Custom"/>

{% endhighlight %}

![](Series_images/exploderadius.png)

N> We have defined ExplodeRadius as 10, by default its value is zero. So you need to define explode, when you set ExplodeIndex or ExplodeAll.

**Explode** **All**

{% highlight xaml %}

<chart:PieSeries Palette="Custom" ExplodeAll="True"

ExplodeRadius="15"

XBindingPath="Category" 

ItemsSource="{Binding Tax}" 

YBindingPath="Percentage">

{% endhighlight %}

![](Series_images/explodeall.png)

## Funnel and Pyramid Charts

### Pyramid

PyramidSeries has the form of a triangle with lines dividing it into sections and each section has a different width. Depending on the Y co-ordinates, this width indicates a level of hierarchy among other categories.

{% highlight xaml %}

<chart:PyramidSeries XBindingPath="Category" Palette="Custom" 

ItemsSource="{Binding Tax}"       

YBindingPath="Percentage"/>

{% endhighlight %}


![](Series_images/pyramid.png)


The [`PyramidMode`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.PyramidSeries~PyramidMode.html#) is used to define the rendering mode of the pyramid segments.

**PyramidMode** **as** **Surface**

{% highlight xaml %}

<chart:PyramidSeries XBindingPath="Category" Palette="Custom"

PyramidMode="Surface"

ItemsSource="{Binding Tax}"        

YBindingPath="Percentage"/>

{% endhighlight %}

![](Series_images/pyramidsurface.png)


**PyramidMode** **as** **Linear**

{% highlight xaml %}

<chart:PyramidSeries XBindingPath="Category" 

Palette="Custom"

PyramidMode="Linear"

ItemsSource="{Binding Tax}"          

YBindingPath="Percentage"/>

{% endhighlight %}

![](Series_images/pyramidlinear.png)

### Funnel

FunnelSeries is similar to PyramidSeries, displays data in a funnel shape that equals to 100% when totaled. It is a single series, representing data as portions of 100% and does not use any axes. 

The following code example shows how to use the funnel series:

{% highlight xaml %}

<chart:FunnelSeries XBindingPath="Category" ItemsSource="{Binding list}"  

YBindingPath="Percentage" Palette="Custom"/>

{% endhighlight %}


![](Series_images/funnel.png)


### Funnel Mode

The FunnelMode defines a rendering mode for the funnel series which define, where to bind your values (to height or width).

**ValueIsHeight**

{% highlight xaml %}

<chart:FunnelSeries XBindingPath="Category" ItemsSource="{Binding list}"    

FunnelMode="ValueIsHeight" 

YBindingPath="Percentage" Palette="Custom"/>

{% endhighlight %}

![](Series_images/valueisheight.png)

**ValueIsWidth**

{% highlight xaml %}

<chart:FunnelSeries XBindingPath="Category" ItemsSource="{Binding list}"    

FunnelMode="ValueIsWidth" 

YBindingPath="Percentage" Palette="Custom/>

{% endhighlight %}

![](Series_images/valueiswidth.png)

### Explode Segments

The following properties are used to explode the individual segments in Pie, Doughnut, Funnel and Pyramid.

* [`ExplodeAll`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.AccumulationSeriesBase~ExplodeAll.html#) - Used to explode all the segments of these series.
* [`ExplodeIndex`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.AccumulationSeriesBase~ExplodeIndex.html#) - Used to explode any specific segment.
* [`ExplodeOffset`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.TriangularSeriesBase~ExplodeOffset.html#)- Used to define the explode distance like ExplodeRadius for Pie.

**Explode** **Offset**

{% highlight xaml %}

<chart:FunnelSeries XBindingPath="Category" ItemsSource="{Binding list}"   

ExplodeIndex="4"  ExplodeOffset="70" YBindingPath="Percentage"     

Palette="Custom">

</chart:FunnelSeries>

![](Series_images/funnelexplode_1.png)

{% endhighlight %}

**Gap** **Ratio**

The gap between each segment using [`GapRatio`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.TriangularSeriesBase~GapRatio.html#) property as in the following code example.

{% highlight xaml %}

<chart:FunnelSeries XBindingPath="Category" ItemsSource="{Binding list}"     

GapRatio="0.5" YBindingPath="Percentage" Palette="Custom">

</chart:FunnelSeries>

{% endhighlight %}

![](Series_images/funnelexplode_2.png)

## Radar and Polar Charts

### Radar

[`RadarSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.RadarSeries.html# "") represents a collection of data, displayed by quantitative variables, represented on axes starting from the same point. The relative position and angle of the axes is not uniform. 

The following code example illustrates the use of radar series:

{% highlight xaml %}

<chart:RadarSeries ItemsSource="{Binding PlantDetails}" 

Interior="#BCBCBC"

XBindingPath="Direction"

YBindingPath="Tree" >

</chart:RadarSeries>        

{% endhighlight %}

![](Series_images/radar.png)


### Polar

[`PolarSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.PolarSeries.html#) displays data points that are grouped by category, on a 360 degree circle. The following code example shows how to use polar series.

{% highlight xaml %}

<chart:PolarSeries Interior="#4A4A4A" 

ItemsSource="{Binding PlantDetails}"  

XBindingPath="Direction"

YBindingPath="Tree" />                 

{% endhighlight %}

![](Series_images/polar.png)


The Radar and Polar charts having the following properties in common:

* [`IsClosed`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.PolarRadarSeriesBase~IsClosed.html#)
* [`DrawType`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.PolarRadarSeriesBase~DrawType.html# )

### IsClosed


This property used to draw the closed path as below.

{% highlight xaml %}

<chart:PolarSeries x:Name="series1" Interior="#4A4A4A" 

ItemsSource="{Binding PlantDetails}"  

Label="Amount Spent" DrawType="Line" IsClosed="False" 

XBindingPath="Direction" YBindingPath="Tree" 

StrokeThickness="2" />

{% endhighlight %}


![](Series_images/Series_img28.jpeg)

### DrawType

This property defines type of curve, whether its line or area.

**DrawType** **as** **Area**

{% highlight xaml %}

<chart:PolarSeries x:Name="series1" Interior="#4A4A4A" 

ItemsSource="{Binding PlantDetails}"  

DrawType="Area" IsClosed="True" 

XBindingPath="Direction" YBindingPath="Tree" />

{% endhighlight %}

![](Series_images/drawtype_area.png)

**DrawType** **as** **Line**

{% highlight xaml %}

<chart:PolarSeries x:Name="series1" Interior="#4A4A4A" 

ItemsSource="{Binding PlantDetails}"  

Lab DrawType="Line" IsClosed="True" 

XBindingPath="Direction" YBindingPath="Tree" 

StrokeThickness="2" />

{% endhighlight %}

![](Series_images/drawtype_line.png)

## Financial Charts

### OHLC

[`HiLoOpenCloseSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.HiLoOpenCloseSeries.html#) displays each data point as a group of horizontal and one vertical line. The values for this series can be bind using [`High`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~High.html#), [`Low`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~Low.html#), [`Open`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~Open.html# "") and [`Close`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~Close.html#) property.

The following code example shows how to use OHLC series:

{% highlight xaml %}

<chart:HiLoOpenCloseSeries Name="series" ItemsSource="{Binding StockPriceDetails}" 

XBindingPath="Date"  High="High" Low="Low"                         

Interior="#4A4A4A"

Open="Open" Close="Close" 

Label="HiloOpenClose" />

{% endhighlight %}

![](Series_images/ohlc.png)

### Candle

[`CandleSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CandleSeries.html#) displays each data point as a combination of a vertical column and a vertical line. This series is most widely used in decision making places, like the stock market.

The values for this series can be bind using [`High`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~High.html#), [`Low`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~Low.html#), [`Open`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~Open.html#) and [`Close`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FinancialSeriesBase~Close.html#) property and the following code example shows the usage of candle series.

{% highlight xaml %}

<chart:CandleSeries Name="series" ItemsSource="{Binding StockPriceDetails}" 

XBindingPath="Date"  High="High" Open="Open"  

Close="Close" Low="Low"  

Interior="#4A4A4A"/>

{% endhighlight %}

![](Series_images/candle.png)


The APIs present in the Candle series are,

<chart:CandleSeries Name="series" ItemsSource="{Binding StockPriceDetails}" XBindingPath="Date"  High="High" Open="Open"  Close="Close" Low="Low"  BearFillColor="Black" BullFillColor="#BCBCBC"/>

![](Series_images/Series_img33.jpeg)

### HiLo

In [`HiLoSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.HiLoSeries.html#), each segment is represented by a line. The height of the line depends on the value of the data point, high or low. The values for this series can be bind using [`High`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.RangeSeriesBase~High.html#) and [`Low`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.RangeSeriesBase~Low.html#).

The following code example shows the use of HiLo series:

{% highlight xaml %}

<chart:HiLoSeries Name="series" Interior="#4A4A4A" 

ItemsSource="{Binding StockPriceDetails}" 

XBindingPath="Date" StrokeThickness="3" 

High="High" Low="Low" />

{% endhighlight %}

![](Series_images/hilo.png)

## Stacking Charts

### Stacking Column

[`StackingColumnSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.StackingColumnSeries.html#) resembles multiple types of series of the ColumnSeries. Each series is vertically stacked one above the other. When there is only one series, then it is ColumnSeries. 

The following code example illustrates how to use StackingColumnSeries:

{% highlight xaml %}

<chart:StackingColumnSeries  

XBindingPath="CountryName"    

YBindingPath="GoldMedals" 

Interior="#4A4A4A"

ItemsSource="{Binding MedalDetails}"/>

<chart:StackingColumnSeries 

Interior="#BCBCBC"

XBindingPath="CountryName" 

YBindingPath="SilverMedals"

ItemsSource="{Binding MedalDetails}"/> 

<chart:StackingColumnSeries 

Interior="#7F7F7F"

XBindingPath="CountryName" 

YBindingPath="BronzeMedals" />

{% endhighlight %}

![](Series_images/stackingcolumn.png)

### Stacking Column 100

[`StackingColumn100Series`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.StackingColumn100Series.html#) resembles StackingColumnSeries but the cumulative portion of each stacked element always comes to a total of 100%. 

{% highlight xaml %}

<chart:StackingColumn100Series  XBindingPath="CountryName" 

YBindingPath="GoldMedals" Interior="#4A4A4A"

ItemsSource="{Binding MedalDetails}"/>

<chart:StackingColumn100Series ItemsSource="{Binding MedalDetails}"

XBindingPath="CountryName"  

YBindingPath="SilverMedals"

Interior="#BCBCBC"/>

<chart:StackingColumn100Series Interior="#7F7F7F"

XBindingPath="CountryName" 

YBindingPath="BronzeMedals"

ItemsSource="{Binding MedalDetails}"/>

{% endhighlight %}

![](Series_images/stackingcolumn100.png)

### Stacking Bar

[`StackingBarSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.StackingBarSeries.html#) is a multiple series type of BarSeries. Each BarSeries is then stacked horizontally, side by side to each other. When there exists only one series, it resembles a simple BarSeries. 

{% highlight xaml %}

<chart:StackingBarSeries XBindingPath="CountryName"        

Interior="#BCBCBC"

YBindingPath="GoldMedals" 

ItemsSource="{Binding MedalDetails}" >

</chart:StackingBarSeries>

<chart:StackingBarSeries Interior="#4A4A4A"

XBindingPath="CountryName" 

YBindingPath="SilverMedals" 

ItemsSource="{Binding MedalDetails}">

</chart:StackingBarSeries>

<chart:StackingBarSeries Interior="#7F7F7F"

XBindingPath="CountryName" 

YBindingPath="BronzeMedals"

ItemsSource="{Binding MedalDetails}" >

</chart:StackingBarSeries>

{% endhighlight %}

![](Series_images/stackingbar.png)


### Stacking Bar 100

[`StackingBar100Series`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.StackingBar100Series.html#) resembles a StackingBarSeries. StackingBar100Series displays multiple series as stacked bars and the cumulative portion of each stacked element is always 100%. 

{% highlight xaml %}

<chart:StackingBar100Series Interior="#BCBCBC"

XBindingPath="CountryName" 

YBindingPath="GoldMedals" 

ItemsSource="{Binding MedalDetails}" />

<chart:StackingBar100Series Interior="#4A4A4A" 

XBindingPath="CountryName"                          

YBindingPath="SilverMedals" 

ItemsSource="{Binding MedalDetails}" />

<chart:StackingBar100Series Interior="#7F7F7F" 

XBindingPath="CountryName" 

YBindingPath="BronzeMedals" 

ItemsSource="{Binding MedalDetails}" />

{% endhighlight %}

![](Series_images/stackingbar100.png)

### Stacking Area

[`StackingAreaSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.StackingAreaSeries.html#) is representing areas stacked vertically one above the other. 

{% highlight xaml %}

<chart:StackingAreaSeries Interior="#BCBCBC" 

XBindingPath="Month" YBindingPath="Bus" 

ItemsSource="{Binding Accidents}" />

<chart:StackingAreaSeries Interior="#4A4A4A"                  

XBindingPath="Month" YBindingPath="Car" 

ItemsSource="{Binding Accidents}" />

<chart:StackingAreaSeries  Interior="#7F7F7FC"                     

XBindingPath="Month" 

YBindingPath="Truck" 

ItemsSource="{Binding Accidents}" />

{% endhighlight %}

![](Series_images/stackingarea.png)

### Stacking Area 100

StackingArea100Series is similar to StackingAreaSeries, but the cumulative portion of each stacked element always totals 100%. 

The following code example shows the way to add stacking area 100 series:

{% highlight xaml %}

<chart:StackingArea100Series Interior="#BCBCBC" 

XBindingPath="Month"         

YBindingPath="Bus" 

ItemsSource="{Binding Accidents}" 

/>

<chart:StackingArea100Series Interior="#4A4A4A" 

XBindingPath="Month" YBindingPath="Car" 

ItemsSource="{Binding Accidents}" />

<chart:StackingArea100Series Interior="#7F7F7F" 

XBindingPath="Month" 

YBindingPath="Truck" 

ItemsSource="{Binding Accidents}" />

{% endhighlight %}


![](Series_images/stackingarea100.png)

You can draw open curve like Area using this [`IsClosed`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.StackingAreaSeries~IsClosed.html#) property.

{% highlight xaml %}

<chart:StackingAreaSeries  Interior="#BCBCBC" Stroke="Black" StrokeThickness="3"

IsClosed="False" XBindingPath="Month" 

YBindingPath="Bus" 

ItemsSource="{Binding Accidents}"/>

<chart:StackingAreaSeries  Interior="#777777" Stroke="White" StrokeThickness="3"

IsClosed="False"  XBindingPath="Month"             

YBindingPath="Car"

ItemsSource="{Binding Accidents}"/>

<chart:StackingAreaSeries  Interior="#7F7F7F" Stroke="Black"   

StrokeThickness="3" IsClosed="False"   

XBindingPath="Month" 

YBindingPath="Truck" 

ItemsSource="{Binding Accidents}" />

{% endhighlight %}

![](Series_images/stackingareaclosed.png)


### Grouping Stacked Series

You can group the stacked series using [`GroupingLabel`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.StackingSeriesBase~GroupingLabel.html#) property. The following code example shows how to group the stacking series.

{% highlight xaml %}

<chart:StackingColumnSeries   Interior="#4A4A4A"

GroupingLabel="Group1" 

XBindingPath="Year" 

YBindingPath="Quarter1" 

ItemsSource="{Binding AnnualDetails}"/>

<chart:StackingColumnSeries Interior="#BCBCBC"

GroupingLabel="Group1" 

XBindingPath="Year" 

YBindingPath="Quarter2" 

ItemsSource="{Binding AnnualDetails}"/>

<chart:StackingColumnSeries Interior="#7F7F7F"

XBindingPath="Year" 

GroupingLabel="Group2" 

YBindingPath="Quarter3" 

ItemsSource="{Binding AnnualDetails}"/>

<chart:StackingColumnSeries XBindingPath="Year" 

GroupingLabel="Group2"

Interior="#343434"

YBindingPath="Quarter4" 

ItemsSource="{Binding AnnualDetails}"/>

{% endhighlight %}

![](Series_images/groupingstacking.png)


## Range Series

### Range Column

[`RangeColumnSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.RangeColumnSeries.html#) is a collection of vertical columns where positioning and height depends on the high and low values of each data point. RangeColumnSeries is used when minimum and maximum need to be specified for the ColumnSeries.

{% highlight xaml %}

<chart:RangeColumnSeries EnableAnimation="False" 

ItemsSource="{Binding FinancialDatas}" 

XBindingPath="Time" Interior="#4A4A4A"

High="High" Low="Low" 

Label="Financial Deployment in Each Year" />

{% endhighlight %}

![](Series_images/rangeseries.png)


### Range Area

[`RangeAreaSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.RangeAreaSeries.html#) is used to display continuous data points as a set of lines that vary between [`High`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.RangeSeriesBase~High.html#) and [`Low`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.RangeSeriesBase~Low.html#) values over intervals of time and across different categories. 

{% highlight xaml %}

<chart:RangeAreaSeries x:Name="RangeAreaSeries" XBindingPath="ProdName" 

High="Stock" Low="Price"   

Interior="#BCBCBC"        

ItemsSource="{Binding Products}" />

{% endhighlight %}

![](Series_images/rangearea.png)


The APIs present in the RangeArea series are,

**Properties**

* HighValueInterior -Gets or sets the brush that represents the interior color for the high value data.
* LowValueInterior- Gets or sets the brush that represents the interior color for the high value data.

{% highlight xaml %}

<chart:RangeAreaSeries x:Name="RangeAreaSeries" XBindingPath="ProdName" 

High="Stock" Low="Price"   

LowValueInterior="#4A4A4A"

HighValueInterior="#777777"

ItemsSource="{Binding Products}" />

{% endhighlight %}

![](Series_images/rangearea_closed.png)

### Histogram 

[`HistogramSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.HistogramSeries.html#) is one of the seven basic tools of quality control. HistogramSeries is often used to plot the density of data.

The following code example shows how to add the HistogramSeries:

{% highlight xaml %}

<chart:HistogramSeries x:Name="histogramSeries" 

HistogramInterval="5" 

Interior="#BCBCBC"

ItemsSource="{Binding Product}"

XBindingPath="Price" 

YBindingPath="Value"/>

{% endhighlight %}

![](Series_images/histogram.png)


You can customize interval using [`HistogramInterval`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.HistogramSeries~HistogramInterval.html#) property and the normal distribution curve can be collapsed using [`ShowNormalDistributionCurve`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.HistogramSeries~ShowNormalDistributionCurve.html#).

{% highlight xaml %}

<chart:HistogramSeries x:Name="histogramSeries" 

HistogramInterval="5"

ShowNormalDistributionCurve="False"

Interior="#BCBCBC"

ItemsSource="{Binding Product}"

XBindingPath="Price" 

YBindingPath="Value"/>

{% endhighlight %}

![](Series_images/histogram_interval.png)

## Fast Charts

### Fast Line

The [`FastLineSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FastLineSeries.html#) is a special kind of line series that can render a collection with a huge number of datapoints. This was rendered using polyline segment. 

{% highlight xaml %}

<chart:FastLineSeries x:Name="FastLineSeries" ItemsSource="{Binding Data}"

XBindingPath="Date" Interior="#7F7F7F"

YBindingPath="Value"/>

{% endhighlight %}

![](Series_images/fastline.png)

The following line properties are available for FastLineSeries:

* [`Stroke`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeries~Stroke.html#)
* [`StrokeDashArray`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FastLineSeries~StrokeDashArray.html#)
* [`StrokeDashOffset`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FastLineSeries~StrokeDashOffset.html# )
* [`StrokeDashCap`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FastLineSeries~StrokeDashOffset.html#)
* [`StrokeThickness`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeries~StrokeThickness.html#)

### Fast Line Bitmap 

[`FastLineBitmapSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FastLineBitmapSeries.html#) displays a series of line segments rendered using WritableBitmap. The advantage of FastLineBitmapSeries renders a million data point in a fraction of seconds.

The following code example shows how to use the fast line bitmap series:

{% highlight xaml %}

<chart:FastLineBitmapSeries x:Name="FastLineSeries" ItemsSource="{Binding Data}"

XBindingPath="Date" Interior="#7F7F7F" 

YBindingPath="Value" />

{% endhighlight %}

![](Series_images/fastlinebitmap.png)

Like FastLineSeries, this bitmap series is also having line properties. 

N> As it was rendered using bitmap, there might be some jagged lines at edges. This is can be reduced using [`EnableAntiAliasing`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FastLineBitmapSeries~EnableAntiAliasing.html#) property.

{% highlight xaml %}

<chart:FastLineBitmapSeries x:Name="FastLineSeries" 

XBindingPath="Date" Interior="#7F7F7F" 

StrokeDashArray="5,5"

YBindingPath="Value" EnableAntiAliasing="True"/>

{% endhighlight %}

![](Series_images/fastlinealiasing.png)


### Fast Column

[`FastColumnBitmapSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FastColumnBitmapSeries.html#) is used to boost up the performance of the ColumnSeries.

{% highlight xaml %}

<chart:FastColumnBitmapSeries x:Name="FastColumnSeries" Interior="#7F7F7F"

ItemsSource="{Binding List}" 

XBindingPath="Date" YBindingPath="Price" 

ShowTooltip="True"/>

{% endhighlight %}

![](Series_images/fastcolumn.png)

### Fast Bar

FastBarBitmapSeries is used to boost up the performance of the series.

{% highlight xaml %}

<chart:FastBarBitmapSeries x:Name="FastBarBitmapSeries" ItemsSource="{Binding List}" 

XBindingPath="Date" YBindingPath="Price" 

Interior="#7F7F7F"/>

{% endhighlight %}

![](Series_images/fastbar.png)


### Fast Candle

FastCandleBitmapSeries renders using bitmap and it displays each data point as a combination of a vertical column and a vertical line, like CandleSeries. 

{% highlight xaml %}

<chart:FastCandleBitmapSeries ItemsSource="{Binding TestingModel}" 

XBindingPath="X" High="Y" 

Low="Y1" Open="Y2" Close="Y3" 

BullFillColor="#BCBCBC" 

BearFillColor="#4A4A4A"  />

{% endhighlight %}

![](Series_images/fastcandle.png)


### Fast HiLo

[`FastHiLoBitmapSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FastHiLoBitmapSeries.html#) represents a series of line segments with high and low values rendered using WritableBitmap. 

{% highlight xaml %}

<chart:FastHiLoBitmapSeries StrokeThickness="5" ItemsSource="{Binding List}"          

Interior="#7F7F7F XBindingPath="Date" High="Stock"     

Low="Price"/>

{% endhighlight %}

{% highlight C# %}

{% endhighlight %}

![](Series_images/fasthilo.png)

### Fast OHLC

[`FastHiLoOpenCloseBitmapSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FastHiLoOpenCloseBitmapSeries.html# "") are rendered using WritableBitmap like other bitmap series. The following code example illustrates the use of OHLC bitmap series.

{% highlight xaml %}

<chart:FastHiLoOpenCloseBitmapSeries ItemsSource="{Binding TestingModel}" 

XBindingPath="X" High="Y" Low="Y1" Open="Y2"        

Close="Y3"   BullFillColor="#7F7F7F"      

BearFillColor="#4A4A4A"/>

{% endhighlight %}

![](Series_images/fastohlc.png)

### Fast Scatter

[`FastScatterBitmapSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FastScatterBitmapSeries.html#) used to render high number scatter points. The [`ScatterHeight`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FastScatterBitmapSeries~ScatterHeight.html#) and [`ScatterWidth`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FastScatterBitmapSeries~ScatterWidth.html#) also available as in ScatterSeries.

{% highlight xaml %}

<chart:FastScatterBitmapSeries Interior="#7F7F7F"   

ItemsSource="{Binding Data}"                         

x:Name="FastScatterSeries"  XBindingPath="Date" 

YBindingPath="Value" ScatterHeight="4"  

ScatterWidth="4"/>

{% endhighlight %}

{% highlight C# %}

{% endhighlight %}

![](Series_images/fastscatter.png)


### Fast Step Line

[`FastStepLineBitmapSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FastStepLineBitmapSeries.html#) is the high performance version of StepLineSeries.

{% highlight xaml %}

<chart:FastStepLineBitmapSeries ItemsSource="{Binding Data}"

XBindingPath="Date"                                 

YBindingPath="Value" Interior="#4A4A4A" />

{% endhighlight %}


![](Series_images/faststepline.png)


The antialiasing property, [`EnableAntiAliasing`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FastStepLineBitmapSeries~EnableAntiAliasing.html#) is available for FastStepLineBitmapSeries also.

{% highlight xaml %}

<chart:FastStepLineBitmapSeries EnableAntiAliasing="True" ItemsSource="{Binding Data}"

x:Name="FastStepLineSeries" XBindingPath="Date" 

YBindingPath="Value" Interior="#4A4A4A"/>

{% endhighlight %}


![](Series_images/faststepline_alias.png)


### Fast Stacking Column

[`FastStackingColumnSeries`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.FastStackingColumnBitmapSeries.html#) similar to StackingColumnSeries except that it loads faster and provides better performance. 

{% highlight xaml %}

<chart:FastStackingColumnBitmapSeries StrokeThickness="5"

ItemsSource="{Binding MedalDetails}”       

XBindingPath="CountryName" YBindingPath="GoldMedals"  

Interior="#4A4A4A" />

{% endhighlight %}

![](Series_images/faststackingcolumn.png)


# Listening Property Changes

You can notify the source the [`XBindingPath`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~XBindingPath.html#) and [`YBindingPath`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.XyDataSeries~YBindingPath.html#) properties changes by setting [`ListenPropertyChange`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~ListenPropertyChange.html#) as true as shown in the below code snippet.

{% highlight xaml %}

<chart:ScatterSeries ScatterWidth="20" ScatterHeight="20"  Label="Coal" ListenPropertyChange="True"

ItemsSource="{Binding EnergyProductions}" Interior="#BCBCBC"

XBindingPath="ID" YBindingPath="Coal">

</chart:ScatterSeries>

{% endhighlight %}

N>By default, the property change was disabled. So the dynamic updates will not get reflect in chart. You need to enable this property.

