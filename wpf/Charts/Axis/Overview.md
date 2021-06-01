---
layout: post
title: Overview in WPF Chart control | Syncfusion 
description: Learn here all about the chart axis overview of syncfusion WPF Chart control and their 
Key feature.
platform: wpf
control: SfChart
documentation: ug
---

# Axis in WPF Chart (SfChart)

[`ChartAxis`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#) is used to locate a data point inside the chart area. Charts typically have two axes that are used to measure and categorize data: a vertical (Y) axis, and a horizontal (X) axis.

Vertical(Y) axis always uses numerical scale. Horizontal(X) axis supports the following types of scale:

* Category
* Numeric
* Date time
* Logarithmic Axis

The following are the API’s in ChartAxis

* [`ArrangeRect`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_ArrangeRect) – Represents the bounds of chart axis size. 

* [`VisibleRange`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_VisibleRange) – Represents the axis start and end visible values as follows.

<table>
<tr>
<td>
[`Start`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoubleRange.html#Syncfusion_UI_Xaml_Charts_DoubleRange_Start)
</td>
<td>
Gets the start value of the visible range.
</td>
</tr>
<tr>
<td>
[`End`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoubleRange.html#Syncfusion_UI_Xaml_Charts_DoubleRange_End)
</td>
<td>
Gets the end value of the visible range.
</td>
</tr>
<tr>
<td>
[`Delta`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoubleRange.html#Syncfusion_UI_Xaml_Charts_DoubleRange_Delta)
</td>
<td>
Gets the delta value of the visible range.
</td>
</tr>
<tr>
<td>
[`Empty`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoubleRange.html#Syncfusion_UI_Xaml_Charts_DoubleRange_Empty)
</td>
<td>
Gets the empty value of the visible range.
</td>
</tr>
<tr>
<td>
[`IsEmpty`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoubleRange.html#Syncfusion_UI_Xaml_Charts_DoubleRange_IsEmpty)
</td>
<td>
Gets a value indicating whether the visible range is empty or not.
</td>
</tr>
<tr>
<td>
[`Median`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.DoubleRange.html#Syncfusion_UI_Xaml_Charts_DoubleRange_Median)
</td>
<td>
Gets the median value of the visible range.
</td>
</tr>
</table>

* [`VisibleLabels`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_VisibleLabels) – Represents the axis label collection which are visible in axis.


## Key Feature


* Axis support different type of axis Category, Numeric, Date time ,Date time category ,Logarithmic and time span axis.
* Allow you customize the chart axis line GridLine, TickLine and support to customize the style of the axis line by defining the [`AxisLineStyle`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxis.html#Syncfusion_UI_Xaml_Charts_ChartAxis_AxisLineStyle). 
* Axis allow you to customize the origin of the chart axis. 
* Multiple Axes provide a way to arrange multiple series inside the same chart area, gives more space for X and Y axis.
* Axis can be customized with multiple levels of label by using its [`MultiLevelLabels`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartAxisBase2D.html#Syncfusion_UI_Xaml_Charts_ChartAxisBase2D_MultiLevelLabels) property. These labels are placed based on the provided Start and End range values. You can add any number of labels to an axis.
 



