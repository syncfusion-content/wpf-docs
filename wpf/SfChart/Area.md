---
layout: post
title: Area| SfChart | Wpf | Syncfusion
description: area
platform: wpf
control: SfChart
documentation: ug
---

# Area

ChartArea represents the entire chart and all its elements. It’s a virtual rectangular area, that includes all the chart elements like axis, legends, series, etc. 

## Multiple Panes

Creating multiple panes for the chart improves readability of the series. When the chart areas are aligned properly, it proves to be a better comparison for the series. They can be aligned the way you visualized it.

In SfChart, you can split areas into multiple rows and columns using ChartRowDefinition and ChartColumnDefinition like GridRow and Column Definition. The following code example demonstrates how you can create multiple panes in the chart area.

{% highlight xml %}

<syncfusion:SfChart.RowDefinitions>

<syncfusion:ChartRowDefinition/>

<syncfusion:ChartRowDefinition/>

</syncfusion:SfChart.RowDefinitions>



<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis ShowGridLines="False" FontSize="20" Header="Company Name"/>

</syncfusion:SfChart.PrimaryAxis>



<syncfusion:SfChart.SecondaryAxis>

<syncfusion:NumericalAxis syncfusion:ChartBase.Row="0"  Interval="40" FontSize="20" Header="Gross Revenue (cr.)"/>

</syncfusion:SfChart.SecondaryAxis>



<syncfusion:LineSeries  Stroke="Red" StrokeThickness="3" XBindingPath="CompanyName" YBindingPath="CompanyTurnOver" ItemsSource="{Binding CompanyDetails}"/>



<syncfusion:LineSeries    Stroke="Green" StrokeThickness="3" XBindingPath="CompanyName" YBindingPath="CompanyTurnOver" ItemsSource="{Binding CompanyDetails}">



<syncfusion:LineSeries.YAxis>

<syncfusion:NumericalAxis syncfusion:ChartBase.Row="1" syncfusion:ChartBase.Column="0" Header="Additional Axis" PlotOffset="30"/>

</syncfusion:LineSeries.YAxis>

</syncfusion:LineSeries>
{% endhighlight %}


The following is the output for the multiple panes.

![C:/Users/rachel/Desktop/wpf/1.png](Area_images/Area_img1.png)



### Chart area customization APIs

The chart area can be customized to enrich your application’s look and feel. SfChart provides APIs to customize chart area, based on your requirements. Chart area includes many elements, and each element can be customized using the API that you can learn from the respective sections of those elements. This section explains about the elements and API for common customization of chart area.



<table>
<tr>
<th>
Property</th><th>
Definition</th></tr>
<tr>
<td>
PrimaryAxis</td><td>
Gets or sets the primary X-Axis for the chart.</td></tr>
<tr>
<td>
SecondaryAxis</td><td>
Gets or sets the primary Y-Axis for the chart.</td></tr>
<tr>
<td>
AreaBorderBrush</td><td>
Gets or sets the brush that describes border of chart area excludes Axis, Header and Legend.</td></tr>
<tr>
<td>
AreaBorderThickness     </td><td>
Gets or sets the thickness for the chart area border excludes Axis, Header and Legend.</td></tr>
<tr>
<td>
AreaBackground</td><td>
Gets or sets the brush that represents the background color for a chart area excluding Axis, Header and Legend.</td></tr>
<tr>
<td>
SeriesClipRect</td><td>
Gets the rectangle that represents the bounding value of chart area excluding Axis, Legend and Header.</td></tr>
<tr>
<td>
Palette</td><td>
Gets or sets the color palette for the chart series. The default palette of SfChart is “Metro”.</td></tr>
<tr>
<td>
SideBySideSeriesPlacement</td><td>
Represents the series placement for the entire chart with multiple series.</td></tr>
<tr>
<td>
Header</td><td>
Gets or sets the object that represents the content of a chart header. This property is used to specify any object as Header for chart</td></tr>
<tr>
<td>
ColorModel</td><td>
Represents the ChartColorModel for entire chart.</td></tr>
</table>


The following code example shows the customization of chart with different chart area properties.

{% highlight xml %}



<syncfusion:SfChart HorizontalAlignment="Center" VerticalAlignment="Center" Height="600" Width="700" 

AreaBackground="Green"

Palette="Metro">



<syncfusion:SfChart.Header>

<Border CornerRadius="5" BorderBrush="AntiqueWhite" BorderThickness="2">

<TextBlock Text="Demand Comparison of Gold" FontSize="20" FontStyle="Italic" FontFamily="Arial"/>

</Border>

</syncfusion:SfChart.Header>



<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis Header="Demands" FontSize="14"/>

</syncfusion:SfChart.PrimaryAxis>

<syncfusion:SfChart.SecondaryAxis>

<syncfusion:NumericalAxis Header="Values( In Tonnes)" FontSize="14"/>

</syncfusion:SfChart.SecondaryAxis>



<syncfusion:SfChart.Legend>

<syncfusion:ChartLegend Visibility="Visible"/>

</syncfusion:SfChart.Legend>



<syncfusion:ColumnSeries Label="2011" 

ItemsSource="{Binding Demands}"

XBindingPath="Demand"

YBindingPath="Year2011"

/>



<syncfusion:LineSeries Label="2010"

ItemsSource="{Binding Demands}"

XBindingPath="Demand"

YBindingPath="Year2010"

StrokeThickness="2"

/>



</syncfusion:SfChart>

{% endhighlight %}

![C:/Users/rachel/Desktop/snaps/2.png](Area_images/Area_img2.png)



## SideBySideSeriesPlacement

It defines the placement pattern of bar type series like Column, Bar, RangeColumn, etc. It is a Boolean property and its default value is True. When you disable this property, all the series overlap as shown in the following image.

{% highlight xml %}

<syncfusion:SfChart HorizontalAlignment="Center" SideBySideSeriesPlacement="False" VerticalAlignment="Center" Height="600" Width="700" >

<!--Initialize the Chart Series for SfChart-->



<syncfusion:ColumnSeries  Label="2010" ItemsSource="{Binding Demands}" XBindingPath="Demand" YBindingPath="Year2010" />



<syncfusion:ColumnSeries Label="2011" ItemsSource="{Binding Demands}" XBindingPath="Demand" YBindingPath="Year2011" SegmentSpacing="0.5" />

{% endhighlight %}

![](Area_images/Area_img3.png)



N> Here Spacing for Series 2 is defined to differentiate both series. Otherwise, both the series of same width



