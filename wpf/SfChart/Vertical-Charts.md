---
layout: post
title: Vertical Charts feature of SfChart.
description: Vertical Charts feature of SfChart.
platform: wpf
control: SfChart
documentation: ug
---

# Vertical Charts

SfChart provides support for vertical charts. You can plot vertical chart for any chart using [`IsTransposed`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CartesianSeries~IsTransposed.html# "") and [`OpposedPosition`](http://help.syncfusion.com/cr/cref_files/wpf/sfchart/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAxis~OpposedPosition.html# "") properties.

# OpposedPosition

Allows to position the axis in the opposite direction to the default position. The following code example illustrates placing the primary axis in opposite direction.

{% highlight xaml %}

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis   OpposedPosition="True" >

</chart:CategoryAxis>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis Minimum="0" Maximum="40" Interval="10"                                   

OpposedPosition="True"/>

</chart:SfChart.SecondaryAxis>

{% endhighlight %}

![](Vertical-Charts_images/VerticalCharts_1.png)


# IsTransposed

This property used to switch the plotting of the series to vertical.

{% highlight xaml %}

<chart:LineSeries  IsTransposed="True"

ItemsSource="{Binding SneakersDetail}"  XBindingPath="Brand" 

YBindingPath="ItemsCount" >

{% endhighlight %}

![](Vertical-Charts_images/VerticalCharts_2.png)


The following example demonstrates the vertical charts.

{% highlight xaml %}

<chart:SfChart>

<chart:SfChart.ColumnDefinitions>

<chart:ChartColumnDefinition />

<chart:ChartColumnDefinition/>

</chart:SfChart.ColumnDefinitions>

<chart:SfChart.PrimaryAxis>

<chart:CategoryAxis  ShowGridLines="False“ >

</chart:CategoryAxis>

</chart:SfChart.PrimaryAxis>

<chart:SfChart.SecondaryAxis>

<chart:NumericalAxis/>

</chart:SfChart.SecondaryAxis>          

<chart:LineSeries   IsTransposed="True"  

ItemsSource="{Binding SneakersDetail}"  XBindingPath="Brand" 

YBindingPath="ItemsCount" >

<chart:LineSeries.AdornmentsInfo>

<chart:ChartAdornmentInfo  ShowMarker="True" Symbol="Ellipse" 

SymbolHeight="10" SymbolInterior="#7f7f7f" SymbolWidth="10">                        

</chart:ChartAdornmentInfo>                        

</chart:LineSeries.AdornmentsInfo>

</chart:LineSeries>

<chart:LineSeries  Interior="DarkGray" IsTransposed="True"

ItemsSource="{Binding SneakersDetail}"  XBindingPath="Brand" 

YBindingPath="postion" >

<chart:LineSeries.AdornmentsInfo>

<chart:ChartAdornmentInfo ShowLabel="False" ShowMarker="True" Symbol="Ellipse" SymbolHeight="10" 

SymbolInterior="DarkGray" SymbolWidth="10"></chart:ChartAdornmentInfo>

</chart:LineSeries.AdornmentsInfo>

<chart:LineSeries.YAxis>

<chart:NumericalAxis />

</chart:LineSeries.YAxis>

</chart:LineSeries>

</chart:SfChart>

{% endhighlight %}

![](Vertical-Charts_images/VerticalCharts_3.png)


