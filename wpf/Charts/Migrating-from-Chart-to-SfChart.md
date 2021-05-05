---
layout: post
title: Migrating from Chart to SfChart in WPF Charts control | Syncfusion
description: Learn here all about Migrating from Chart to SfChart support in Syncfusion WPF Charts (SfChart) control and more.
platform: wpf
control: SfChart
documentation: ug
---

# Migrating from Chart to SfChart in WPF Charts (SfChart)

SfChart is a new chart introduced in 11.1 version. SfChart is a very high performance chart enriched with several business features. This section helps you to identify equivalent Chart features/ APIs in SfChart.

## Adding Reference

Chart assembly Name: Syncfusion.Chart.Wpf assembly

SfChart assembly Name: Syncfusion.SfChart.WPF assembly

The following code example illustrates xmlns namespace for Chart. You can include the Syncfusion schema in WPF and both the charts are available in the WPF schema. 

### Chart

{% highlight xaml %}

xmlns:syncfusion=[https://schemas.syncfusion.com/wpf](https://schemas.syncfusion.com/wpf)


{% endhighlight %}

### SfChart

{% highlight xaml %}

xmlns:syncfusion="https://schemas.syncfusion.com/wpf"

                     (or)

xmlns:syncfusion="clr-namespace:Syncfusion.UI.Xaml.Charts;assembly=Syncfusion.SfChart.WPF"         

{% endhighlight %}

## Initialization

One of the biggest differences between Chart and SfChart is, Chart is constructed using one or more ChartArea. So, logically ChartArea is equivalent to SfChart. 

Note: In SfChart, you can split the area into multiple plotting areas using RowDefinitions and ColumnDefinitions API.

Following code example illustrates the initialization of Chart with ChartArea,

{% highlight xaml %}

<syncfusion:Chart>

<syncfusion:ChartArea BorderBrush="Green"  BorderThickness="5" Background="Gray" SideBySideSeriesPlacement="True"  />

</syncfusion:Chart>

{% endhighlight %}

{% highlight C# %}

Chart chart = new Chart();

ChartArea area = new ChartArea();

area.Background = Brushes.Gray;

area.BorderBrush = Brushes.Red;

area.BorderThickness = new Thickness(5);

area.SideBySideSeriesPlacement = true;

chart.Areas.Add(area);.

{% endhighlight %}

Following code example illustrates the initialization of SfChart that is equivalent to the above code example.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfChart Header="ChartArea" AreaBackground="Red" AreaBorderBrush="Gray" AreaBorderThickness="5" SideBySideSeriesPlacement="True"  />
{% endhighlight %}

{% highlight C# %}

SfChart chart = new SfChart();

chart.AreaBackground = Brushes.Gray;

chart.AreaBorderBrush = Brushes.Red;

chart.AreaBorderThickness = new Thickness(5);

chart.SideBySideSeriesPlacement = true;

{% endhighlight %}
{% endtabs %}

The following table illustrates the API comparison between ChartArea and SfChart.

<table>
<tr>
<th>
ChartArea</th><th>
SfChart</th><th>
Description</th></tr>
<tr>
<td>
Header</td><td>
Header</td><td>
Gets or sets the header name for Chart </td></tr>
<tr>
<td>
Background</td><td>
AreaBackground</td><td>
Gets or sets the Chart area background (rectangle bounds excluding Axis and legend)</td></tr>
<tr>
<td>
BorderBrush</td><td>
AreaBorderBrush</td><td>
Gets or sets the Chart area border brush.</td></tr>
<tr>
<td>
BorderThickness</td><td>
AreaBorderThickness</td><td>
Gets or sets the Chart area border thickness.</td></tr>
<tr>
<td>
SideBySideSeriesPlacement</td><td>
SideBySideSeriesPlacement</td><td>
Gets or sets Boolean value whether series is placed side by side or not.</td></tr>
<tr>
<td>
Series</td><td>
Series</td><td>
Gets or sets ChartSeriesCollection to Chart. </td></tr>
<tr>
<td>
ShowGridLines</td><td>
-</td><td>
Gets or sets Boolean value for showing the gridlines for both axes.</td></tr>
<tr>
<td>
EnableRangeSelection</td><td>
-</td><td>
Gets or sets Boolean value that enables you to select a particular range of a primary axis by using two cursors.</td></tr>
<tr>
<td>
StartValue</td><td>
-</td><td>
Gets or sets start value for range selection</td></tr>
<tr>
<td>
EndValue</td><td>
-</td><td>
Gets or sets end value for range selection</td></tr>
<tr>
<td>
ShowLegend</td><td>
-</td><td>
Gets or sets Boolean value for showing the chart legends.</td></tr>
<tr>
<td>
SplitterColor</td><td>
-</td><td>
Gets or sets color for SyncChartAreas splitter</td></tr>
<tr>
<td>
SplitterPosition</td><td>
-</td><td>
Gets or sets position for SyncChartAreas splitter</td></tr>
<tr>
<td>
SplitterStroke</td><td>
-</td><td>
Gets or sets stroke for SyncChartAreas splitter</td></tr>
<tr>
<td>
SplitterVisibility</td><td>
-</td><td>
Gets or sets visibility for SyncChartAreas splitter</td></tr>
<tr>
<td>
SplitterWidth</td><td>
-</td><td>
Gets or sets width for SyncChartAreas splitter</td></tr>
</table>

## Legend

The Legends are same for both Chart and SfChart except that you can add multiple Legends for the SfChart.
 The Legend property in ChartArea accepts single Legend for whole Chart. In case of SfChart, the Legend property of
 the SfChart is an object that accepts one or more Legends based on your requirement. 
 [For more details](https://help.syncfusion.com/winrt/sfchart/legend)

The following code example illustrates the usage of Legend in Chart and SfChart.

### Chart
{% tabs %}
{% highlight xaml %}

<syncfusion:ChartArea>

  <syncfusion:ChartArea.Legend>

 <syncfusion:ChartLegend syncfusion:Chart.Dock="Floating" Orientation="Vertical"  OffsetX="200" OffsetY="200" ItemTemplate="{StaticResourcelegend}" CheckBoxVisibility="Collapsed"/>

  </syncfusion:ChartArea.Legend>

</syncfusion:ChartArea>
{% endhighlight %}

{% highlight C# %}


ChartArea area = new ChartArea();

ChartLegend legend = new ChartLegend();

Chart.SetDock(legend, ChartDock.Floating);

legend.Orientation = Orientation.Vertical;

legend.OffsetX = 200d;

legend.OffsetY = 200d;

legend.CheckBoxVisibility = Visibility.Visible;

area.Legend = legend;

chart.Areas.Add(area)
{% endhighlight %}
{% endtabs %}

### SfChart

{% tabs %}
{% highlight xaml %}

<syncfusion:SfChart>

<syncfusion:SfChart.Legend>

<syncfusion:ChartLegend  ItemTemplate="{StaticResource legend}"CheckBoxVisibility="Visible" LegendPosition="Outside"  Orientation="Vertical"OffsetY="200" OffsetX="200"   DockPosition="Floating"/>

</syncfusion:SfChart.Legend>

</syncfusion:SfChart>
{% endhighlight %}

{% highlight C# %}

SfChart chart = new SfChart();

ChartLegend legend = new ChartLegend();

legend.ItemTemplate = grid.Resources["legend"] as DataTemplate;

legend.CheckBoxVisibility = Visibility.Visible;

legend.OffsetX = 200d;

legend.OffsetY = 200d;

legend.Orientation = ChartOrientation.Vertical;

legend.DockPosition = ChartDock.Top; 

legend.LegendPosition = LegendPosition.Outside;



chart.Legend = legend;
{% endhighlight %}
{% endtabs %}


The following table illustrates the API comparison between ChartArea and SfChart.

<table>
<tr>
<th>
ChartLegend (Chart)</th><th>
ChartLegend (SfChart)</th><th>
Description</th></tr>
<tr>
<td>
CheckBoxVisibility</td><td>
CheckBoxVisibility</td><td>
Gets or sets visibility for Legend check box </td></tr>
<tr>
<td>
Orientation</td><td>
Orientation</td><td>
Gets or sets orientation for Legends</td></tr>
<tr>
<td>
chart:Chart.Dock</td><td>
DockPosition</td><td>
Gets or sets docking position for Legends that decides the positioning for Legends.</td></tr>
<tr>
<td>
OffsetX</td><td>
OffsetX</td><td>
Gets or sets X-axis offset value for Legends horizontal placement. </td></tr>
<tr>
<td>
OffsetY</td><td>
OffsetY</td><td>
Gets or sets Y-axis offset value for Legends vertical placement. OffsetX and OffsetY are applicable when DockPosition is set as 'Floating'.</td></tr>
<tr>
<td>
ItemTemplate</td><td>
ItemTemplate</td><td>
Gets or sets template for the Legend items.</td></tr>
<tr>
<td>
IconVisibility</td><td>
IconVisibility</td><td>
Gets or sets the visibility of the Legend icon(s).</td></tr>
<tr>
<td>
IconHeight</td><td>
IconHeight</td><td>
Gets or sets the double value that represents the Legend icon(s) width.</td></tr>
<tr>
<td>
IconHeight</td><td>
IconHeight</td><td>
Gets or sets the double value that represents that  Legend icon(s) height.</td></tr>
<tr>
<td>
ItemMargin</td><td>
ItemMargin</td><td>
Gets or sets the margin of Legend items.</td></tr>
<tr>
<td>
ElementMargin</td><td>
Margin</td><td>
Gets or sets the margin for Legend element.</td></tr>
<tr>
<td>
ShowSymbol</td><td>
IconVisibility</td><td>
Gets or sets the visibility for Legend icon symbol.</td></tr>
</table>

## Axis

The class design for Axis is different for both ChartArea and SfChart. In ChartArea, Axis is the instance of ChartAxis type and its type is mentioned in ValueType property as in the following code example.

{% highlight xaml %}

<syncfusion:ChartArea.PrimaryAxis>

<syncfusion:ChartAxis  ValueType="DateTime"  />

</syncfusion:ChartArea.PrimaryAxis>
{% endhighlight %} 
In SfChart, Axis can be an instance of NumericalAxis, DateTimeAxis, CategoryAxis, LogarithmicAxis, TimeSpanAxis or DateTimeCategoryAxis. Class name represents the type of data it can plot. For example, NumericalAxis can plot numeric values and DateTimeAxis can plot DateTime values. Following code example illustrates this,

{% highlight xaml %}

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:DateTimeAxis Header="X-Axis"/>

</syncfusion:SfChart.PrimaryAxis>
{% endhighlight %}
The following table compares the APIs,

<table>
<tr>
<th>
ChartAxis</th><th>
NumericalAxis, DateTimeAxis, CategoryAxis, LogarithmicAxis, TimeSpanAxis and DateTimeCategoryAxis</th><th>
Description</th></tr>
<tr>
<td>
Header</td><td>
Header</td><td>
Gets or sets the header for the chart axis.</td></tr>
<tr>
<td>
IntersectAction</td><td>
LabelsIntersectAction</td><td>
Gets or sets a value that determines how to avoid overlapping of labels.</td></tr>
<tr>
<td>
RangePadding</td><td>
RangePadding</td><td>
Gets or sets the range padding for chart axis.</td></tr>
<tr>
<td>
IsAutoSetRange, Range</td><td>
Minimum, Maximum</td><td>
Gets or sets range for chart axis </td></tr>
<tr>
<td>
Interval</td><td>
Interval</td><td>
Gets or sets value for axis label</td></tr>
<tr>
<td>
LabelPosition</td><td>
LabelPosition</td><td>
Gets or sets placement position for label.</td></tr>
<tr>
<td>
AxisVisibility</td><td>
Visibility</td><td>
Gets or sets the visibility for Chart Axis.</td></tr>
<tr>
<td>
EnableAutoIntervalOnZooming</td><td>
EnableAutoIntervalOnZooming</td><td>
Gets or sets a Boolean value to enable auto interval calculation while zooming</td></tr>
<tr>
<td>
IsInversed</td><td>
IsInversed</td><td>
Gets or sets a value that indicates whether data is plotted reversely or not.</td></tr>
<tr>
<td>
TickLinesPosition</td><td>
TickLinesPosition</td><td>
Gets or sets tick line position</td></tr>
<tr>
<td>
TickLineSize</td><td>
TickLineSize</td><td>
Gets or sets tick line size</td></tr>
<tr>
<td>
SmallTickLineSize</td><td>
SmallTickLineSize</td><td>
Gets or sets small tick line size</td></tr>
<tr>
<td>
</td><td>
SmallTickLinesPosition</td><td>
Gets or sets small tick line position</td></tr>
<tr>
<td>
SmallTicksPerInterval</td><td>
SmallTicksPerInterval</td><td>
Gets or sets value to enable small ticks.</td></tr>
<tr>
<td>
LabelRotateAngle</td><td>
LabelRotateAngle</td><td>
Gets or sets label rotation angle.</td></tr>
<tr>
<td>
EdgeLabelsDrawingMode</td><td>
EdgeLabelsDrawingMode</td><td>
Gets or sets position for edge labels.</td></tr>
<tr>
<td>
DesiredIntervalsCount</td><td>
DesiredIntervalsCount</td><td>
Gets or sets desired interval count.</td></tr>
<tr>
<td>
OpposedPosition</td><td>
OpposedPosition</td><td>
Gets or sets a value that indicates axis is positioned opposite to its default position.</td></tr>
<tr>
<td>
LabelsSource</td><td>
LabelsSource</td><td>
Gets or sets label source for custom labels.</td></tr>
<tr>
<td>
ContentPath</td><td>
ContentPath</td><td>
Gets or sets content path property value.</td></tr>
<tr>
<td>
PositionPath</td><td>
PositionPath</td><td>
Gets or sets position path property value.</td></tr>
<tr>
<td>
LabelsPostfix</td><td>
PostfixLabelTemplate</td><td>
Gets or sets post fix label template.</td></tr>
<tr>
<td>
LabelsPrefix</td><td>
PrefixLabelTemplate</td><td>
Gets or sets prefix label template</td></tr>
<tr>
<td>
LabelDateTimeFormat, LabelLogarithmicFormat LabelTimeSpanFormat</td><td>
LabelFormat</td><td>
Gets or sets axis label format.</td></tr>
<tr>
<td>
LabelTemplate</td><td>
LabelTemplate</td><td>
Gets or sets label template.</td></tr>
<tr>
<td>
chart:ChartArea.ShowGridLines</td><td>
ShowGridline</td><td>
Gets or sets a value to enable grid lines.</td></tr>
<tr>
<td>
chart:ChartArea.SmallGridLineStroke</td><td>
MajorGridLineStyle</td><td>
Gets or sets major grid line style.</td></tr>
<tr>
<td>
chart:ChartArea.SmallGridLineStroke</td><td>
MajorTickLineStyle</td><td>
Gets or sets tick line style.</td></tr>
<tr>
<td>
ZoomFactor</td><td>
ZoomFactor</td><td>
Gets or sets the zoom factor value.</td></tr>
<tr>
<td>
ZoomPosition</td><td>
ZoomPosition</td><td>
Gets or sets the zoom position value.</td></tr>
</table>

### Chart

{% tabs %}
{% highlight xaml %}

<chart:ChartArea>

<chart:Chart.PrimaryAxis>

<chart:ChartAxis  ValueType="DateTime"  IntersectAction="Hide" 

IsAutoSetRange="False" DateTimeRange="2010/01/01,2011/01/01" 

SmallTickSize="6" SmallTicksPerInterval="5" 

TickLinesPosition="Outside" TickSize="10" 

LabelsSource="{Binding power}" ContentPath="Content" 

PositionPath="Position" 

LabelsPostfix="{StaticResource postLabel}" 

LabelsPrefix="{StaticResource preLabel}" 

DesiredIntervalsCount="5"  

LabelDateTimeFormat="MM:dd:yy" RangePadding="Normal"  

LabelPosition="Outside" Header="X-Axis" 

EdgeLabelsDrawingMode="Center"   IsInversed="False" 

LabelRotateAngle="0" AxisVisibility="Visible" 

EnableAutoIntervalOnZooming="False"  ZoomFactor="1" 

ZoomPosition="1" chart:ChartArea.ShowGridLines="True" />

</chart:Chart.PrimaryAxis>

</chart:ChartArea>

{% endhighlight %}

{% highlight C# %}

ChartArea area = new ChartArea();

ChartAxis primaryAxis = new ChartAxis();

primaryAxis.ValueType = ChartValueType.DateTime;

primaryAxis.LabelDateTimeFormat = "MM:dd:yy";

primaryAxis.LabelPosition = LabelPositions.Outside;

primaryAxis.AxisVisibility = Visibility.Visible;

primaryAxis.Header = "X-Axis";

primaryAxis.RangePadding = ChartRangePaddingType.Normal;

primaryAxis.TickLinesPosition = AxisPositions.Outside;

primaryAxis.EdgeLabelsDrawingMode = EdgeLabelsDrawingMode.Center;

primaryAxis.IsInversed = false;

primaryAxis.IsAutoSetRange = false;

primaryAxis.DateTimeRange = new DateTimeRange(new DateTime(2010, 01, 01), new DateTime(2011, 01, 01));

primaryAxis.DateTimeInterval = new TimeSpan(24, 0, 0);

primaryAxis.DesiredIntervalsCount = 5;

primaryAxis.TickLinesPosition = AxisPositions.Outside;

primaryAxis.TickSize = 10d;

primaryAxis.SmallTickSize = 6d;

primaryAxis.SmallTicksPerInterval = 5;

primaryAxis.IntersectAction = ChartLabelIntersectAction.Hide;

ChartArea.SetShowGridLines(primaryAxis, true);

primaryAxis.LabelsSource = viewmodel.power;

primaryAxis.ContentPath = "Content";

primaryAxis.PositionPath = "Position";

primaryAxis.ShowGridline= true;

primaryAxis.OpposedPosition = true;

primaryAxis.ZoomFactor = 1d;

primaryAxis.ZoomPosition = 0d;



area.PrimaryAxis = primaryAxis;

{% endhighlight %}
{% endtabs %}

### SfChart

{% tabs %}
{% highlight xaml %}

<sfchart:SfChart>

<sfchart:SfChart.PrimaryAxis>

<sfchart:DateTimeAxis Header="X-Axis" OpposedPosition="True" 

RangePadding="Auto" 

DesiredIntervalsCount="5"  IsInversed="False" 

LabelFormat="MM/dd/yy" RangePadding="Auto" 

Interval="1"  Minimum="2010/01/01" Maximum="2011/01/10" 

IntervalType="Years" LabelsPosition="Outside" 

LabelsIntersectAction="Hide"  TickLinesPosition="Outside" 

Visibility="Visible" EnableScrollBar="False" 

EdgeLabelsDrawingMode="Center" 

EnableAutoIntervalOnZooming="True"  

ShowTrackBallInfo="True" PlotOffset="20" 

LabelsSource="{Binding power}" ShowGridline="True" 

ContentPath="Content" PositionPath="Postion" 

PostfixLabelTemplate="{StaticResource postLabel}" 

PrefixLabelTemplate="{StaticResource preLabel}" 

SmallTickLinesPosition="Outside" SmallTicksPerInterval="5" 

TickLineSize="6" ZoomFactor="1" ZoomPosition="0"/>

<sfchart:SfChart.PrimaryAxis/>

</sfchart:SfChart>

{% endhighlight %}

{% highlight C# %}
SfChart chart = new SfChart();

DateTimeAxis primaryAxis = new DateTimeAxis();

primaryAxis.Interval = 1;

primaryAxis.LabelFormat = "MM/dd/yy";

primaryAxis.IntervalType = DateTimeIntervalType.Years;

primaryAxis.IsInversed = false;

primaryAxis.LabelsPosition = AxisElementPosition.Outside;

primaryAxis.LabelsIntersectAction = AxisLabelsIntersectAction.Hide;

primaryAxis.TickLinesPosition = AxisElementPosition.Outside;

primaryAxis.Visibility = Visibility.Visible;

primaryAxis.EnableScrollBar = false;

primaryAxis.EdgeLabelsDrawingMode = EdgeLabelsDrawingMode.Center;

primaryAxis.RangePadding = DateTimeRangePadding.Auto;

primaryAxis.PlotOffset = 10d;

primaryAxis.Header = "X-Axis";

primaryAxis.ShowTrackBallInfo = true;

primaryAxis.DesiredIntervalsCount = 5;

primaryAxis.OpposedPosition = true;

primaryAxis.SmallTickLineSize = 6d;

primaryAxis.SmallTickLinesPosition = AxisElementPosition.Outside;

primaryAxis.SmallTicksPerInterval = 5;

primaryAxis.TickLineSize = 10d;

primaryAxis.TickLinesPosition = AxisElementPosition.Outside;

primaryAxis.LabelsSource = viewmodel.power;

primaryAxis.ContentPath = "Content";

primaryAxis.PositionPath = "Position";

primaryAxis.ShowGridline= true;

primaryAxis.OpposedPosition = true;

primaryAxis.Minimum = new DateTime(2011, 1, 1);

primaryAxis.Maximum = new DateTime(2012, 1, 1);

primaryAxis.ZoomFactor = 1d;

primaryAxis.ZoomPosition = 0d;

chart.PrimaryAxis = primaryAxis;
{% endhighlight %}
{% endtabs %}

Following code example illustrates how to customize gridlines.

### Chart

{% tabs %}
{% highlight xaml %}

<chart:ChartArea.GridLineStroke>

<Pen Brush="#c6c6c6" >

<Pen.DashStyle>

<DashStyle Dashes="1,3"/>

</Pen.DashStyle>

</Pen>

</chart:ChartArea.GridLineStroke>

{% endhighlight %}

{% highlight C# %}

Pen pen = new Pen();

DashStyle style = new DashStyle() { Dashes = new DoubleCollection(3) };

pen.DashStyle = style;

pen.Brush = Brushes.Red;

ChartArea.SetGridLineStroke(primaryAxis, pen);
{% endhighlight %}
{% endtabs %}

### SfChart

{% tabs %}
{% highlight xaml %}

<sfchart:NumericalAxis.MajorGridLineStyle>

<Style TargetType="Line">

<Setter Property="StrokeDashArray" Value="1,3"></Setter>

<Setter Property="Stroke" Value="#c6c6c6" />

</Style>

</sfchart:NumericalAxis.MajorGridLineStyle>
{% endhighlight %}


{% highlight C# %}
Style lineStyle = new Style(typeof(Line));

lineStyle.Setters.Add(new Setter(Line.StrokeDashArrayProperty, new DoubleCollection(3)));

lineStyle.Setters.Add(new Setter(Line.StrokeProperty, Brushes.Red));

primaryAxis.MajorGridLineStyle = lineStyle;
{% endhighlight %}
{% endtabs %}

## Series

Like Axis, ChartSeries architecture is also different for Chart and SfChart. Instead of specifying the respective ChartType, you can create the instance of required series (Class name itself represents the type of series) in SfChart as in the following code example.

### Chart

{% highlight xaml %}

<syncfusion:ChartArea>

<syncfusion:ChartSeries Type="Line"  ShowToolTip="True" 

Interior="Blue" ShowSmartLabels="True"

LegendIcon="Diamond"

AdornmentIntersectAction="AdjustAroundPoints"

ColorEach="True" Palette="Metro"

StrokePalette="Metro" IsRotated="False"

IsIndexed="True" IsVisibleOnLegend="True"

IsSortData="False" SortBy="X"

SortDirection="Ascending"

ShowDataLabels="True"  EnableEffects="True" 

IsVisible="True"  StrokeThickness="3"

EnableAnimation="True" AnimateOption="Fade"

AnimateOneByOne="True" ShowEmptyPoints="True" 

EmptyPointInterior="Purple" EmptyPointValue="Average"

EmptyPointStyle="Interior" DataSource="{Binding power}"

BindingPathX="Year" BindingPathsY="Sports"

Label="LineSeries" >

<syncfusion:ChartSeries.YAxis>

<syncfusion:ChartAxis IsAutoSetRange="False" Range="20,50"/>

</syncfusion:ChartSeries.YAxis>

</syncfusion:ChartSeries>

</syncfusion:ChartArea>
{% endhighlight %}


{% highlight C# %}

ChartArea area = new ChartArea();

ChartSeries lineseries = new ChartSeries();

lineseries.BindingPathX = "Year";

lineseries.Label = "ColumnSeries";

lineseries.BindingPathsY = new string[] { "Sports" };

lineseries.DataSource = viewmodel.power;

lineseries.ShowToolTip = true;

lineseries.ShowEmptyPoints = true;

lineseries.EmptyPointValue = EmptyPointValue.Average;

lineseries.EmptyPointStyle = EmptyPointStyle.Interior;

lineseries.EmptyPointInterior = Brushes.Purple;

lineseries.EnableAnimation = true;

lineseries.IsSortData = true;

lineseries.IsRotated = true;

lineseries.IsVisible = true;

lineseries.SortBy = SortingAxis.X;

lineseries.SortDirection = Direction.Ascending;

lineseries.YAxis = new ChartSeries() { IsAutosetRange = false, Range = new DoubleRange(20,50) };

lineseries.ShowSmartLabels = true;

area.Series.Add(lineseries);
{% endhighlight %}


### SfChart

{% tabs %}
{% highlight xaml %}

<syncfusion:SfChart>

<syncfusion:LineSeries ItemsSource="{Binding power}"

XBindingPath="Year" YBindingPath="Sports"

Palette="Metro" AnimationDuration="00:00:03"

SortBy="X" SortDirection="Ascending" 

EnableSegmentDragging="True" LegendIcon="Diamond"

VisibilityOnLegend="Visible"  Label="LineSeries"

IsSeriesVisible="True" IsSortData="True"

IsTransposed="True" EnableAnimation="True"

ShowTooltip="True" StrokeThickness="3"

ShowEmptyPoints="True" EmptyPointValue="Average"

EmptyPointInterior="Purple" EmptyPointStyle="Interior"

<syncfusion:LineSeries.YAxis>

<syncfusion:NumericalAxis  Minimum="20" Maximum="50"/>

</syncfusion:LineSeries.YAxis>

</syncfusion:LineSeries>

</syncfusion:SfChart>
{% endhighlight %}
 
{% highlight C# %}

SfChart chart = new Sfchart();

LineSeries lineseries = new LineSeries();

lineseries.ItemsSource = viewmodel.power;

lineseries.XBindingPath = "Year";

lineseries.YBindingPath = "Sports";

lineseries.Label = "LineSeries";

lineseries.Interior = Brushes.Brown;

lineseries.ShowTooltip = true;

lineseries.ShowEmptyPoints = true;

lineseries.EmptyPointInterior = Brushes.Purple;

lineseries.EmptyPointStyle = EmptyPointStyle.Interior;

lineseries.EmptyPointValue = EmptyPointValue.Average;

lineseries.StrokeThickness = 3;

lineseries.EnableAnimation = true;

lineseries.AnimationDuration = new TimeSpan(00, 00, 03);

lineseries.IsSeriesVisible = true;

lineseries.IsSortData = true;

lineseries.IsTransposed = true;

lineseries.SortBy = SortingAxis.X;

lineseries.YAxis = new NumericalAxis() { Minimum = 20, Maximum = 50 };

lineseries.SortDirection = Direction.Ascending;

chart.Series.Add(lineseries);
{% endhighlight %}
{% endtabs %}

The following table illustrates the API comparison for series,

<table>
<tr>
<th>
ChartSeries</th><th>
LineSeries, ColumnSeries, SplineSeries … etc.,</th><th>
Description</th></tr>
<tr>
<td>
Label</td><td>
Label</td><td>
Gets or sets series label name.</td></tr>
<tr>
<td>
ShowTooltip</td><td>
ShowTooltip</td><td>
Gets or sets a value to enable tooltip.</td></tr>
<tr>
<td>
EnableAnimation</td><td>
EnableAnimation</td><td>
Gets or sets a value to enable animation.</td></tr>
<tr>
<td>
AnimationDuration</td><td>
AnimationDuration</td><td>
Gets or sets timespan for animation duration.</td></tr>
<tr>
<td>
AnimateOneByOne</td><td>
-</td><td>
Gets or sets a value whether to animate the series one by one or not.</td></tr>
<tr>
<td>
AnimateOption</td><td>
-</td><td>
Gets or sets enum for animation direction.</td></tr>
<tr>
<td>
ColorEach </td><td>
Palette</td><td>
Gets or sets a value that indicates whether to color each segment differently or not.</td></tr>
<tr>
<td>
BindingPathX</td><td>
XBindingPath</td><td>
Gets or sets x axis binding property.</td></tr>
<tr>
<td>
BindingPathsY</td><td>
YBindingPath,High,Low,Open,Close,Size</td><td>
Gets or sets y axis binding property. In Chart, it is a collection of y value paths whereas in SfChart, each y path is represented by individual properties. For example, Candle, HiLoOpenClose series contains four y values, each value is represented by High, Low, Open and Close properties.HiLo contains two y values represented by High and Low properties.Bubble series contains two y values represented by YBindingPath and Size properties.Other series that contains one y value is represented by YBindingPath property.</td></tr>
<tr>
<td>
DataSource</td><td>
ItemsSource</td><td>
Gets or sets items source for chart series.</td></tr>
<tr>
<td>
Interior</td><td>
Interior</td><td>
Gets or sets interior color for chart series.</td></tr>
<tr>
<td>
ShowEmptyPoints</td><td>
ShowEmptyPoints</td><td>
Gets or sets a value that indicates whether to show empty points in different style or color based on EmptyPointValue and EmptyPointValue.</td></tr>
<tr>
<td>
EmptyPointValue</td><td>
EmptyPointValue</td><td>
Gets or sets a value that indicates whether to represent empty point as average of previous and next value or just zero.</td></tr>
<tr>
<td>
EmptyPointInterior</td><td>
EmptyPointInterior</td><td>
Gets or sets empty point value interior. </td></tr>
<tr>
<td>
IsSortData</td><td>
IsSortData</td><td>
Gets or sets a value to enable sorting in chart series.</td></tr>
<tr>
<td>
SortBy</td><td>
SortBy</td><td>
Sorting the series based on X or Y axis value.</td></tr>
<tr>
<td>
SortDirection</td><td>
SortDirection</td><td>
Sorting the chart series based on direction like ascending or descending.</td></tr>
<tr>
<td>
ShowSmartLabels</td><td>
EnableSmartLabels</td><td>
Gets or sets a value whether to avoid the adornment intersection. In SfChart EnableSmartLabels is used for Pie and Doughnut series.</td></tr>
<tr>
<td>
EnableEffects</td><td>
-</td><td>
Gets or sets effect for Chart series.</td></tr>
<tr>
<td>
Unit</td><td>
-</td><td>
Gets or sets legend unit.</td></tr>
<tr>
<td>
UnitVisibility</td><td>
-</td><td>
Gets or sets legend unit visibility</td></tr>
<tr>
<td>
chart:ChartPieType.ExplodedAll  chart:ChartDoughnutType.ExplodedAll</td><td>
ExplodedAll</td><td>
Gets or sets a value whether to explode all the segments of pie and doughnut chart</td></tr>
<tr>
<td>
chart:ChartPieType.ExplodedIndex  chart:ChartDoughnutType.ExplodedIndex</td><td>
ExplodedIndex</td><td>
Gets or sets the index of the segment to be exploded.</td></tr>
<tr>
<td>
chart:ChartPieType.ExplodeRadius chart: ChartDoughnutType.ExplodeRadius</td><td>
ExplodeRadius</td><td>
Gets or sets explode radius for all the segment of pie, doughnut chart.</td></tr>
<tr>
<td>
ChartPyramidType.GapRatio</td><td>
GapRatio</td><td>
Gets or sets gap ratio for pyramid series.</td></tr>
<tr>
<td>
ChartPyramidType.PyramidMode</td><td>
PyramidMode</td><td>
Gets or sets mode for pyramid series.</td></tr>
</table>

## Adornments

The Adornments are same as Chart and you can define the Adornments inside the Series like Chart.

### Chart

{% tabs %}
{% highlight xaml %}

<syncfusion:ChartSeries>

<syncfusion:ChartSeries.ChartAdornmentInfo >

<syncfusion:ChartAdornmentInfo  SegmentLabelContent="YValue"

SegmentShowLine="True"  Visible="True"

SymbolInterior="Red"

AdornmentsPosition="Top" Symbol="Ellipse"

SegmentLabelRotation="20" 

SymbolStroke="Red" SymbolHeight="15"

SymbolWidth="15" />

<syncfusion:ChartSeries.ChartAdornmentInfo />

</syncfusion:ChartSeries>
{% endhighlight %}


{% highlight C# %}

ChartSeries lineseries = new ChartSeries();

ChartAdornmentInfo adornment = new ChartAdornmentInfo();

adornment.Visible = true;

adornment.Symbol = Symbol.Ellipse;

adornment.SymbolInterior = Brushes.Red;

adornment.SymbolWidth = 15d;

adornment.SymbolHeight = 15d;

adornment.SegmentLabelContent = LabelContent.YValue;

adornment.SegmentShowLine = true;

adornment.SegmentLabelRotation = 30d;

adornment.AdornmentsPosition = AdornmentsPosition.Top;



lineseries.AdornmentsInfo = adornment;

{% endhighlight %}
{% endtabs %}

### SfChart

{% tabs %}
{% highlight xaml %}

<syncfusion:LineSeries >

<syncfusion:LineSeries.ChartAdornmentInfo>

<syncfusion:ChartAdornmentInfo  Symbol="Cross"

UseSeriesPalette="True"

AdornmentsPosition="Top"

ShowConnectorLine="True"

ConnectorHeight="10"

SegmentLabelContent="YValue"   

ShowLabel="True" SymbolStroke="Red"

SymbolHeight="20" SymbolWidth="20"

SymbolInterior="Red"/>

</syncfusion:LineSeries.ChartAdornmentInfo>

</syncfusion:LineSeries >
{% endhighlight %}


{% highlight C# %}

LineSeries lineseries = new LineSeries();

ChartAdornmentInfo adornment = new ChartAdornmentInfo();

adornment.ShowLabel = true;

adornment.Symbol = ChartSymbol.Ellipse;

adornment.SymbolHeight = 20d;

adornment.SymbolWidth = 20d;

adornment.SymbolInterior = Brushes.Red;

adornment.SegmentLabelContent = LabelContent.YValue;

adornment.SymbolStroke = Brushes.Red;

adornment.AdornmentsPosition = AdornmentsPosition.Top;

adornment.ConnectorHeight = 10d;

adornment.UseSeriesPalette = true;

adornment.ShowConnectorLine = true;



lineseries.AdornmentsInfo = adornment;
{% endhighlight %}
{% endtabs %}

The following table illustrates the API comparison for Adornments.

<table>
<tr>
<th>
ChartAdornmentInfo (Chart)</th><th>
ChartAdornmentInfo (SfChart)</th><th>
Description</th></tr>
<tr>
<td>
Visible</td><td>
ShowLabel</td><td>
Gets or sets a value whether to show Adornment label or not.</td></tr>
<tr>
<td>
Symbol</td><td>
Symbol</td><td>
Gets or sets symbol for Adornment.</td></tr>
<tr>
<td>
SymbolInterior</td><td>
SymbolInterior</td><td>
Gets or sets color for Adornment.</td></tr>
<tr>
<td>
SymbolStroke</td><td>
SymbolStroke</td><td>
Gets or sets stroke color for Adornment symbol.</td></tr>
<tr>
<td>
AdornmentsPosition</td><td>
AdornmentsPosition</td><td>
Gets or sets position for Adornment.</td></tr>
<tr>
<td>
LabelTemplate</td><td>
LabelTemplate</td><td>
Gets or sets template for label.</td></tr>
<tr>
<td>
SymbolTemplate</td><td>
SymbolTemplate</td><td>
Gets or sets template for symbol.</td></tr>
<tr>
<td>
SegmentLabelContent</td><td>
SegmentLabelContent</td><td>
Gets or sets Adornment segment label content.</td></tr>
<tr>
<td>
ConnectorTemplate</td><td>
ConnectorHeight,ConnectorLineStyle</td><td>
Customizing the Adornment connector line.</td></tr>
<tr>
<td>
</td><td>
UseSeriesPalette</td><td>
Gets or sets color for each connector line</td></tr>
<tr>
<td>
SegmentShowLine</td><td>
ShowConnectorLine</td><td>
Gets or sets a value to enable connector line.</td></tr>
</table>

## Interactive Cursor

The InteractiveCursor is represented as ChartCrosshairBehavior and ChartTrackballBehavior in SfChart. Following code example illustrates this,

### Chart

{% tabs %}
{% highlight xaml %}

<syncfusion:ChartArea>

<syncfusion:ChartArea.InteractiveCursors>

<syncfusion:InteractiveCursor VerticalLabelVisibility="Visible"HorizontalLabelVisibility="Visible" IsBindWithMouseMove="True"IsBindWithSegment="False" OffsetX="100" OffsetY="100"/>

</syncfusion:ChartArea.InteractiveCursors>

</syncfusion:ChartArea>
{% endhighlight %}


{% highlight C# %}

ChartArea area= new ChartArea();

InteractiveCursor incCursor = new InteractiveCursor();

incCursor.VerticalLabelVisibility = Visibility.Visible;

incCursor.HorizontalLabelVisibility = Visibility.Visible;

incCursor.IsBindWithMouseMove = true;

incCursor.IsBindWithSegment = false;

incCursor.OffsetX = 100d;

incCursor.OffsetY = 100d;

area.InteractiveCursors.Add(incCursor);
{% endhighlight %}
{% endtabs %}

### SfChart

{% tabs %}
{% highlight xaml %}

<syncfusion:SfChart>

<syncfusion:SfChart.Behaviors>

<syncfusion:ChartCrossHairBehavior HorizontalAxisLabelAlignment="Center"VerticalAxisLabelAlignment="Center" />

<syncfusion:SfChart.Behaviors/>

</syncfusion:SfChart>
{% endhighlight %}

{% highlight C# %}

SfChart chart = new SfChart();

ChartCrossHairBehavior crosshair = new ChartCrossHairBehavior();

crosshair.VerticalAxisLabelAlignment = ChartAlignment.Center;

crosshair.HorizontalAxisLabelAlignment = ChartAlignment.Center;

chart.Behaviors.Add(crosshair);
{% endhighlight %}
{% endtabs %}

## Zooming and Panning

The Zooming and Panning are achieved using the ChartZoomPanBehavior in SfChart as in the following code example.

### Chart

{% tabs %}
{% highlight xaml %}

<syncfusion:ChartArea EnableZoomOnScroll="True" ZoomAllAxes="True"chart:ChartZoomingToolkit.ZoomingToolkitVisibility="Visible"EnableMouseDragZooming="True" /> 
{% endhighlight %}


{% highlight C# %}

ChartArea area= new ChartArea();

area.ZoomAllAxes = true;

area.EnableZoomOnScroll = true;

ChartZoomingToolkit.SetZoomingToolkitVisibility(area, Visibility.Visible);

{% endhighlight %}
{% endtabs %}

### SfChart

{% tabs %}
{% highlight xaml %}

<syncfusion:SfChart>

 <syncfusion:SfChart.Behaviors>

<syncfusion:ChartZoomPanBehavior ZoomMode="XY" EnablePinchZooming="False"ZoomRelativeToCursor="False" EnableMouseWheelZooming="True"EnableSelectionZooming="False" EnablePanning="True" />

<syncfusion:SfChart.Behaviors/>

</syncfusion:SfChart>
{% endhighlight %}

{% highlight C# %}

SfChart chart = new SfChart();

ChartZoomPanBehavior zoom = new ChartZoomPanBehavior();

zoom.EnableMouseWheelZooming = true;

zoom.EnablePanning = true;

zoom.EnableSelectionZooming = false;

zoom.ZoomMode = ZoomMode.XY;

zoom.ZoomRelativeToCursor = false;

zoom.EnablePinchZooming = false;

chart.Behaviors.Add(zoom);
{% endhighlight %}
{% endtabs %}

## StripLines

The following code example demonstrates the usage of StripLines in Chart and SfChart.

### Chart

{% tabs %}
{% highlight xaml %}

<syncfusion:ChartAxis.StripLines>

<syncfusion:ChartStripLine x:Name="strip" Start="40" IsSegmented="False"SegmentStartValue="20" SegmentEndValue="40" RepeatEvery="10" RepeatUntil="50"TextRotationAngle="30"  StartFromAxis="False" Width="5" IsPixelWidth="False"Interior="#b4e8f3" >

<syncfusion:ChartAxis.StripLines/>
{% endhighlight %}

{% highlight C# %}

ChartArea area= new ChartArea();

ChartStripLine stripline = new ChartStripLine();

stripline.Offset = 20d;

stripline.Width = 5d;

stripline.StartFromAxis = false;

stripline.IsSegmented = false;

stripline.SegmentStartValue = 20d;

stripline.SegmentEndValue = 40d;

stripline.RepeatEvery = 10d;

stripline.RepeatUntil = 50d;

stripline.TextRotationAngle = 30;

stripline.IsPixelWidth = false;

stripline.Interior = new SolidColorBrush(Colors.Red);

stripline.Text = new FormattedText("StripLine", CultureInfo.CurrentCulture, FlowDirection.LeftToRight, new Typeface("Times New Roman"), 20, Brushes.Black);



area.SecondaryAxis.StripLines.Add(stripline);
{% endhighlight %}
{% endtabs %}

### SfChart

{% tabs %}
{% highlight xaml %}

<syncfusion:NumericalAxis.StripLines>

<syncfusion:ChartStripLine Start="40" LabelAngle="30" LabelHorizontalAlignment="Center"LabelVerticalAlignment="Center" RepeatEvery="10" RepeatUntil="50"IsSegmented="False" SegmentStartValue="20" SegmentEndValue="50" IsPixelWidth="True"   Width="5" Label="StripLine" Background="#b4e8f3" />

<syncfusion:NumericalAxis.StripLines/>

{% endhighlight %}


{% highlight C# %}

SfChart chart = new SfChart();

ChartStripLine stripline = new ChartStripLine();

stripline.Start = 40d;

stripline.LabelAngle = 30d;

stripline.LabelHorizontalAlignment = HorizontalAlignment.Center;

stripline.LabelVerticalAlignment = VerticalAlignment.Center;

stripline.RepeatEvery = 10d;

stripline.RepeatUntil = 50d;

stripline.IsSegmented = false;

stripline.SegmentStartValue = 20d;

stripline.SegmentEndValue = 50d;

stripline.IsPixelWidth = true;

stripline.Background = new SolidColorBrush(Colors.Red);

stripline.Width = 5d;

stripline.Background = Brushes.LightGray;

stripline.Label = "StripLine";

chart.SecondaryAxis.StripLines.Add(stripline);

{% endhighlight %}
{% endtabs %}

The following table illustrates the API comparison between Chart and SfChart.

<table>
<tr>
<th>
ChartStripLine (Chart)</th><th>
ChartStripLine (SfChart)</th><th>
Description</th></tr>
<tr>
<td>
Start</td><td>
Start</td><td>
Gets or sets start value for axis.</td></tr>
<tr>
<td>
Width</td><td>
Width</td><td>
Gets or sets the width. When IsPixelWidth is ‘true’, then it considers unit of width as pixel otherwise it is axis value.</td></tr>
<tr>
<td>
Interior</td><td>
Background</td><td>
Gets or sets color for strip line background.</td></tr>
<tr>
<td>
Text</td><td>
Label</td><td>
Gets or sets text for strip line. In Chart Text as a 'Formatted Text' and in SfChart label as a 'String'.</td></tr>
<tr>
<td>
TextRotationAngle</td><td>
LabelAngle</td><td>
Gets or sets label angle.</td></tr>
<tr>
<td>
TextAlignment</td><td>
LabelHorizontalAlignmentLabelVerticalAlignment</td><td>
Gets or sets alignment for strip line labels.</td></tr>
<tr>
<td>
RepeatEvery</td><td>
RepeatEvery</td><td>
Gets or sets value for strip line occurrence.</td></tr>
<tr>
<td>
RepeatUntil</td><td>
RepeatUntil</td><td>
Gets or sets value where the strip line occurrence ends.</td></tr>
<tr>
<td>
IsSegmented</td><td>
IsSegmented</td><td>
Gets or sets value that indicates whether strip line is segmented.</td></tr>
<tr>
<td>
SegmentStartValue</td><td>
SegmentStartValue</td><td>
Gets or sets segment start value.</td></tr>
<tr>
<td>
SegmentEndValue</td><td>
SegmentEndValue</td><td>
Gets or sets segment end value.</td></tr>
<tr>
<td>
IsPixelWidth</td><td>
IsPixelWidth</td><td>
Gets or sets a value that indicates the unit of the value of Width is pixel.</td></tr>
</table>

## Watermark

Following code example illustrates the WatermarkAPI comparison,

### Chart

{% tabs %}
{% highlight xaml %}

<syncfusion:ChartArea>

<syncfusion:ChartArea.Watermark>

<VisualBrush Stretch="None" Opacity="0.5" AlignmentX="Center" AlignmentY="Center">

<VisualBrush.Visual>

<TextBlock  Text="Chart" FontSize="60"Foreground="Gray">

</TextBlock>

</VisualBrush.Visual>

 </VisualBrush>

  </syncfusion:ChartArea.Watermark>

</syncfusion:ChartArea>

{% endhighlight %}

{% highlight C# %}
ChartArea area = new ChartArea();

area.Watermark = new VisualBrush()

{

Opacity = 0.5,

AlignmentX = AlignmentX.Center,

AlignmentY = AlignmentY.Center,

Stretch = Stretch.None,

Visual = new TextBlock()

{

Text = "Chart", Foreground = Brushes.Gray, FontSize = 60d

}

};

{% endhighlight %}
{% endtabs %}

### SfChart

{% tabs %}
{% highlight xaml %}

<syncfusion:SfChart>

<syncfusion:SfChart.Watermark>

<syncfusion:Watermark Canvas.ZIndex="-1" HorizontalAlignment="Center"VerticalAlignment="Center">

<syncfusion:Watermark.Content>

<TextBlock Text="SfChart" FontSize="60" Foreground="Gray"Opacity="0.5"></TextBlock>

</syncfusion:Watermark.Content>

</syncfusion:Watermark>

</syncfusion:SfChart.Watermark>

</syncfusion:SfChart>
{% endhighlight %}


{% highlight C# %}

SfChart chart = new SfChart();

Watermark waterMark = new Watermark();

waterMark.HorizontalAlignment = HorizontalAlignment.Center;

waterMark.VerticalAlignment = VerticalAlignment.Center;

Canvas.SetZIndex(waterMark, -1);

waterMark.Content = new TextBlock() { Text = "SfChart", Foreground = Brushes.Gray, Opacity = 0.5, FontSize = 60d };


chart.Watermark = waterMark;

{% endhighlight %}
{% endtabs %}

## Annotation

In Chart, you can add Annotations to chart and series. Annotations added to Chart are positioned based on OffsetX and OffsetY whose values are in the unit of pixel. Annotations added to series are positioned relative to axis. Annotation shape is specified in AnnotationShape property.

Following code example illustrates the Annotation types and Annotation API’s for both Charts:

### Chart

Chart having following Annotations

* Chart Annotation

{% tabs %}
{% highlight xaml %}

<syncfusion:Chart.AnnotationLabels>

< syncfusion:ChartAnnotationLabel AnnotationShape="None" Template="{StaticResourcetemplateImage}"  Content="Text Annotation" OffsetX="500" OffsetY="100"IsAnnotationDragDrop="True" />

</syncfusion:Chart.AnnotationLabels>
{% endhighlight %}

{% highlight C# %}

Chart chart = new Chart();

ChartAnnotationLabel chartannotation=new ChartAnnotationLabel();

chartannotation.AnnotationShape = AnnotationShapes.None;

chartannotation.Content = "Text Annotation";

chartannotation.OffsetX = 500d;

chartannotation.OffsetY = 100d;

chartannotation.IsAnnotationDragDrop = true;

chart.AnnotationLabels.Add(chartannotation);

{% endhighlight %}
{% endtabs %}


* Series Annotation

{% tabs %}
{% highlight xaml %}

<syncfusion:ChartSeries.Annotations>

   <syncfusion:AnnotationsCollection >

    <syncfusion:ChartSeriesAnnotation X="40702" Y="468"  AnnotationShape="Diamond"Stroke="Black"   Fill="Orange"/>

   </syncfusion:AnnotationsCollection>

</syncfusion:ChartSeries.Annotations>

{% endhighlight %}

{% highlight C# %}

ChartSeries columnSeries = new ChartSeries();

AnnotationsCollection annoCollection = new AnnotationsCollection();

ChartSeriesAnnotation seriesAnnotation=new ChartSeriesAnnotation();

seriesAnnotation.X = 40702;

seriesAnnotation.Y = 468;

seriesAnnotation.AnnotationShape = AnnotationShapes.Diamond;

seriesAnnotation.Stroke = Brushes.Black;

seriesAnnotation.Fill = Brushes.Orange;

annoCollection.m_annotationsCollection.Add(seriesAnnotation);

columnSeries.Annotations = annoCollection;
{% endhighlight %}
{% endtabs %}

### SfChart

In SfChart, you can position Annotations in pixel unit or axis. Units are specified using CoordinateUnit property. Unlike Chart, shape is represented by class name itself in SfChart.

###SfChart having the following Annotations

* Image Annotation

{% tabs %}
{% highlight xaml %}

<syncfusion:SfChart.Annotations>              

 < syncfusion:ImageAnnotation ImageSource="Annotation.png"VerticalTextAlignment="Center" Foreground="White" CoordinateUnit="Axis" X1="30"X2="75" Y1="520" Y2="560">                  

 </syncfusion:ImageAnnotation>

<syncfusion:SfChart.Annotations/>
{% endhighlight %}

{% highlight C# %}

SfChart chart = new SfChart();

ImageAnnotation imgAnnotation = new ImageAnnotation();

imgAnnotation.ImageSource = new BitmapImage(new Uri(@"/Images/Annotation.png", UriKind.Relative));

imgAnnotation.VerticalTextAlignment = VerticalAlignment.Center;

imgAnnotation.Foreground = new SolidColorBrush(Colors.White);

imgAnnotation.CoordinateUnit = CoordinateUnit.Axis;

imgAnnotation.X1 = 30d;

imgAnnotation.X2 = 75d;

imgAnnotation.Y1 = 520d;

imgAnnotation.Y2 = 560d;



chart.Annotations.Add(imgAnnotation);
{% endhighlight %}
{% endtabs %}

* Line Annotation

{% tabs %}
{% highlight xaml %}

<syncfusion:SfChart.Annotations>              

 < syncfusion:LineAnnotation X1="3" Y1="34" X2="5" Y2="38" CanResize="True"CanDrag="True"></ syncfusion:LineAnnotation>   

<syncfusion:SfChart.Annotations/>
{% endhighlight %}


{% highlight C# %}

SfChart chart = new SfChart();

LineAnnotation lineAnnotation = new LineAnnotation();

lineAnnotation.CoordinateUnit = CoordinateUnit.Axis;

lineAnnotation.CanResize = true;

lineAnnotation.CanDrag = true;

lineAnnotation.X1 = 3d;

lineAnnotation.X2 = 34d;

lineAnnotation.Y1 = 5d;

lineAnnotation.Y2 = 38d;



chart.Annotations.Add(lineAnnotation);

{% endhighlight %}
{% endtabs %}

* Ellipse Annotation 
{% tabs %}
{% highlight xaml %}

<syncfusion:SfChart.Annotations>              

 <syncfusion:EllipseAnnotation X1="1" Y1="36" X2="2" Y2="42" CanResize="True"CanDrag="True"></ syncfusion:EllipseAnnotation>     

<syncfusion:SfChart.Annotations/>
{% endhighlight %}


{% highlight C# %}

SfChart chart = new SfChart();

EllipseAnnotation ellipseAnnotation = new EllipseAnnotation();

ellipseAnnotation.CoordinateUnit = CoordinateUnit.Axis;

ellipseAnnotation.CanResize = true;

ellipseAnnotation.CanDrag = true;

ellipseAnnotation.X1 = 36d;

ellipseAnnotation.X2 = 2d;

ellipseAnnotation.Y1 = 36d;

ellipseAnnotation.Y2 = 42d;

chart.Annotations.Add(ellipseAnnotation);
{% endhighlight %}
{% endtabs %}

* Rectangle Annotation
{% tabs %}
{% highlight xaml %}

<syncfusion:SfChart.Annotations>              

 <syncfusion:RectangleAnnotation X1="4" Y1="40" X2="6" Y2="42" CanResize="True"CanDrag="True"></syncfusion:RectangleAnnotation>           

<syncfusion:SfChart.Annotations/>
{% endhighlight %}

{% highlight C# %}

SfChart chart = new SfChart();

RectangleAnnotation rectAnnotation = new RectangleAnnotation();

rectAnnotation.CoordinateUnit = CoordinateUnit.Axis;

rectAnnotation.CanResize = true;

rectAnnotation.CanDrag = true;

rectAnnotation.X1 = 36d;

rectAnnotation.X2 = 2d;

rectAnnotation.Y1 = 36d;

rectAnnotation.Y2 = 42d;

chart.Annotations.Add(rectAnnotation);

{% endhighlight %}
{% endtabs %}

* Vertical Line Annotation 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfChart.Annotations>              

 <syncfusion:VerticalLineAnnotation CanDrag="True" ShowAxisLabel="True"CanResize="True" CoordinateUnit="Axis" X1="3">               

</syncfusion:VerticalLineAnnotation>                

<syncfusion:SfChart.Annotations/>
{% endhighlight %}


{% highlight C# %}

SfChart chart = new SfChart();

VerticalLineAnnotation verAnnotation = new VerticalLineAnnotation();

verAnnotation.CoordinateUnit = CoordinateUnit.Axis;

verAnnotation.ShowAxisLabel = true;

verAnnotation.CanDrag = true;

verAnnotation.X1 = 3d;

chart.Annotations.Add(verAnnotation);

{% endhighlight %}
{% endtabs %}

* Horizontal Line Annotation  

{% tabs %}
{% highlight xaml %}

<syncfusion:SfChart.Annotations>              

 <syncfusion:HorizontalLineAnnotation CanDrag="True" CanResize="True"CoordinateUnit="Axis" ShowAxisLabel="True"  Y1="40" >                

</syncfusion:HorizontalLineAnnotation>

<syncfusion:SfChart.Annotations/>

{% endhighlight %}



{% highlight C# %}

SfChart chart = new SfChart();

HorizontalLineAnnotation horAnnotation = new HorizontalLineAnnotation();

horAnnotation.CoordinateUnit = CoordinateUnit.Axis;

horAnnotation.ShowAxisLabel = true;

horAnnotation.CanDrag = true;

horAnnotation.Y1 = 40d;

chart.Annotations.Add(horAnnotation);
{% endhighlight %}
{% endtabs %}
* Text Annotation 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfChart.Annotations>              

<syncfusion:TextAnnotation X1="0" Y1="150" Text="Release 1" ContentTemplate="{StaticResource textTemplate}" ToolTipContent="Volume 1 Released!!!"ToolTipTemplate="{StaticResource tooltip}" VerticalAlignment="Top" HorizontalAlignment="Left"  ToolTipPlacement="Top"ShowToolTip="True">                </syncfusion:TextAnnotation>

<syncfusion:SfChart.Annotations/>
{% endhighlight %}


{% highlight C# %}

SfChart chart = new SfChart();

TextAnnotation textAnnotation = new TextAnnotation();

textAnnotation.CoordinateUnit = CoordinateUnit.Axis;

textAnnotation.X1 = 0d;

textAnnotation.Y1 = 150d;

textAnnotation.Text = "Release 1";

textAnnotation.ToolTipContent = "Volume 1 Released!!!";

textAnnotation.HorizontalAlignment = HorizontalAlignment.Left;

textAnnotation.ToolTipPlacement = ToolTipLabelPlacement.Top;

textAnnotation.ShowToolTip = true;

chart.Annotations.Add(textAnnotation);

{% endhighlight %}
{% endtabs %}

### Technical Indicators

The following table illustrates the API comparison for TechnicalIndicators,

<table>
<tr>
<th>
ChartTechnicalIndicator (Chart)</th><th>
AccumulationDistributionIndicator, BollingerBandIndicator… etc.,(SfChart)</th><th>
Description</th></tr>
<tr>
<td>
SignalLineColor</td><td>
SignalLineColor</td><td>
Gets or sets the Brush value that represents the indicator signal line color.</td></tr>
<tr>
<td>
UpperLineColor</td><td>
UpperLineColor</td><td>
Gets or sets the Brush value that represents the color for the Upper Bollinger Band.</td></tr>
<tr>
<td>
ConvergenceLineColor</td><td>
ConvergenceLineColor</td><td>
Gets or sets the Brush value that represents the line color for the convergence.</td></tr>
<tr>
<td>
DivergenceLineColor</td><td>
DivergenceLineColor</td><td>
Gets or sets the Brush value that represents the Divergence Line color.</td></tr>
<tr>
<td>
chart:ChartBollingerBand.BollingerMovingAverage</td><td>
Period</td><td>
Gets or sets the value that represents the indicator moving average period</td></tr>
<tr>
<td>
chart:ChartExponentialAverage.ExponentialAverage</td><td>
Period</td><td>
Gets or sets the value that represents the indicator moving average period</td></tr>
<tr>
<td>
chart:ChartSimpleAverage.MovingAverage</td><td>
Period</td><td>
Gets or sets the value that represents the indicator moving average period</td></tr>
<tr>
<td>
chart:ChartTriangularAverage.TriangularAverage</td><td>
Period</td><td>
Gets or sets the value that represents the indicator moving average period</td></tr>
<tr>
<td>
chart:ChartMomentum.MomentumTimeSpan</td><td>
Period</td><td>
Measures the amount that a security's price has changed over a given time span.</td></tr>
<tr>
<td>
IndicatorType</td><td>
-</td><td>
In Chart, you can set the type of the indicator where as in SfChart, indicator type is indicated by the class name itself.</td></tr>
</table>

### Chart

{% tabs %}
{% highlight xaml %}

<syncfusion:ChartSeries.Indicators>

<syncfusion:IndicatorCollection>

<syncfusion:IndicatorCollection.Items>

<syncfusion:ChartTechnicalIndicator 

IndicatorType="BollingerBands"  

chart:ChartBollingerBand.LowerLineColor ="Blue" chart:ChartBollingerBand.UpperLineColor="Red" chart:ChartBollingerBand.SignalLineColor ="Green" chart:ChartBollingerBand.BollingerMovingAverage="50" >

</syncfusion:ChartTechnicalIndicator>

</syncfusion:IndicatorCollection.Items>

</syncfusion:IndicatorCollection>

</syncfusion:ChartSeries.Indicators>

{% endhighlight %}

{% highlight C# %}

ChartSeries columnSeries = new ChartSeries();

IndicatorCollection indiCollection = new IndicatorCollection();

ChartTechnicalIndicator indicator = new ChartTechnicalIndicator();

indicator.IndicatorType = IndicatorTypes.BollingerBands;

ChartBollingerBand.SetLowerLineColor(chart,Brushes.Blue);

ChartBollingerBand.SetSignalLineColor(chart, Brushes.Red);

ChartBollingerBand.SetSignalLineColor(chart, Brushes.Green);

ChartBollingerBand.SetBollingerMovingAverage(chart,50);

indiCollection.Items.Add(indicator);

columnSeries.Indicators = indiCollection;

{% endhighlight %}
{% endtabs %}

##SfChart

{% tabs %}
{% highlight xaml %}

<syncfusion:SfChart.TechnicalIndicators>

 <syncfusion:BollingerBandIndicator UpperLineColor="Brown"LowerLineColor="DarkBlue" Period="1" XBindingPath="Year" ItemsSource="{BindingCompanyDetails}" High="High" Open="Open" Close="Close" Low="Low"/>

 </syncfusion:SfChart.TechnicalIndicators>
{% endhighlight %}


{% highlight C# %}



SfChart chart = new SfChart();

BollingerBandIndicator indicator = new BollingerBandIndicator();

indicator.UpperLineColor=new SolidColorBrush(Colors.Brown);

indicator.LowerLineColor=new SolidColorBrush(Colors.DarkBlue);

indicator.XBindingPath = "Year";

indicator.High = "High";

indicator.Open = "Open";

indicator.Close = "Close";

indicator.Low = "Low";

indicator.ItemsSource = viewmodel.CompanyDetails;

chart.TechnicalIndicators.Add(indicator);
{% endhighlight %}
{% endtabs %}

## SyncChartAreas

In Chart, you can split chart area into multiple plotting areas that share common axis, crosshair/interactive cursor etc., using SyncChartAreas class.

In SfChart, you can split chart into multiple plotting areas that share common axis, crosshair/interactive cursor and zooming functionalities by defining multiple rows and columns using RowDefinitions and ColumnDefinition properties. It is similar to defining rows and columns in Grid panel.

The following code example illustrates the API’s for both charts,

### Chart

## SyncChartAreas

{% tabs %}
{% highlight xaml %}

  <syncfusion:Chart>

  <syncfusion:SyncChartAreas >

  <syncfusion:SyncChartAreas.PrimaryAxis>

  <syncfusion:ChartAxis  ValueType="DateTime"LabelDateTimeFormat="MM/dd/yy" Header="Date">

  </syncfusion:ChartAxis>

  </syncfusion:SyncChartAreas.PrimaryAxis>

  <syncfusion:SyncChartAreas.Areas>

  <syncfusion:ChartArea x:Name="Area1" >

  <syncfusion:ChartArea.SecondaryAxis >

  <syncfusion:ChartAxis EdgeLabelsDrawingMode="Shift" Interval="50" Header="Prices">

  </syncfusion:ChartAxis>

  </syncfusion:ChartArea.SecondaryAxis>

  <syncfusion:ChartSeries Type="Line" DataSource="{Bindingdatalist}" BindingPathX="Time" BindingPathsY="Low"  >

  </syncfusion:ChartSeries>

  </syncfusion:ChartArea>

  <syncfusion:ChartArea x:Name="Area2" >

  <syncfusion:ChartArea.SecondaryAxis >

  <syncfusion:ChartAxis EdgeLabelsDrawingMode="Shift" Interval="50" Header="Prices">

  </syncfusion:ChartAxis>

  </syncfusion:ChartArea.SecondaryAxis>

  <syncfusion:ChartSeries Type="Line" DataSource="{Bindingdatalist}" BindingPathX="Time" BindingPathsY="High" >

  </syncfusion:ChartSeries>

  </syncfusion:ChartArea>

  </syncfusion:SyncChartAreas.Areas>

  </syncfusion:SyncChartAreas>

  </syncfusion:Chart>


{% endhighlight %}

{% highlight C# %}




SyncChartAreas areas=new SyncChartAreas();

areas.PrimaryAxis = new ChartAxis();

ChartArea area1 = new ChartArea();

area1.SecondaryAxis = new ChartAxis();

ChartSeries lineSeries1 = new ChartSeries();

lineSeries1.BindingPathX = "Time";

lineSeries1.BindingPathsY = new string[] { "Low" };

lineSeries1.DataSource = viewmodel.datalist;

lineSeries1.Type = ChartTypes.Line;

area1.Series.Add(lineSeries1);

ChartArea area2 = new ChartArea();

area2.SecondaryAxis = new ChartAxis();

ChartSeries lineSeries2 = new ChartSeries();

lineSeries2.BindingPathX = "Time";

lineSeries2.BindingPathsY = new string[] { "High" };

lineSeries2.DataSource = viewmodel.datalist;

lineSeries2.Type = ChartTypes.Line;

area2.Series.Add(lineSeries1);

areas.Areas.Add(area1);

areas.Areas.Add(area2);

{% endhighlight %}
{% endtabs %}

### SfChart

##Column Row Definition

{% tabs %}
{% highlight xaml %}
<syncfusion:SfChart>

<syncfusion:SfChart.RowDefinitions>

<syncfusion:ChartRowDefinition/>

<syncfusion:ChartRowDefinition/>

</syncfusion:SfChart.RowDefinitions>

<syncfusion:SfChart.PrimaryAxis>

<syncfusion:CategoryAxis ShowGridLines="False" FontSize="20"Header="Company Name"/>

</syncfusion:SfChart.PrimaryAxis>

<syncfusion:SfChart.SecondaryAxis>

<syncfusion:NumericalAxis syncfusion:ChartBase.Row="0"  Interval="40"FontSize="20" Header="Gross Revenue (cr.)"/>

</syncfusion:SfChart.SecondaryAxis>

<syncfusion:LineSeries  Stroke="Red" StrokeThickness="3"XBindingPath="CompanyName" YBindingPath="CompanyTurnOver1" ItemsSource="{BindingCompanyDetails}"/>

<syncfusion:LineSeries  Stroke="Green" StrokeThickness="3"XBindingPath="CompanyName" YBindingPath="CompanyTurnOver2" ItemsSource="{BindingCompanyDetails}">

<syncfusion:LineSeries.YAxis>

<syncfusion:NumericalAxis syncfusion:ChartBase.Row="1"Header="Additional Axis" PlotOffset="30"/>

</syncfusion:LineSeries.YAxis>

</syncfusion:LineSeries>

</syncfusion:SfChart>
{% endhighlight %}

{% highlight C# %}

SfChart chart = new SfChart();

ChartRowDefinition row1=new ChartRowDefinition();

ChartRowDefinition row2 = new ChartRowDefinition();

chart.RowDefinitions.Add(row1);

chart.RowDefinitions.Add(row2);



chart.PrimaryAxis = new CategoryAxis();

NumericalAxis numAxis1 = new NumericalAxis();

ChartBase.SetRow(numAxis1,0);



LineSeries lineseries1 = new LineSeries();

lineseries1.ItemsSource = viewmodel.CompanyDetails;

lineseries1.XBindingPath = "CompanyName";

lineseries1.YBindingPath = "CompanyTurnOver1";



LineSeries lineseries2 = new LineSeries();

lineseries2.ItemsSource = viewmodel.CompanyDetails;

lineseries2.XBindingPath = "CompanyName";

lineseries2.YBindingPath = "CompanyTurnOver2";



NumericalAxis numAxis2 = new NumericalAxis();

ChartBase.SetRow(numAxis2,1);

lineseries2.YAxis = numAxis2;



chart.Series.Add(lineseries1);

chart.Series.Add(lineseries2);

{% endhighlight %}
{% endtabs %}

## Exporting and Printing

### Export to Image

### Chart

{% highlight C# %}

Chart chart = new Chart();      

SaveFileDialog saveFileDialog = new SaveFileDialog();

            string C_imageFilesFilter = "Bitmap(*.bmp)|*.bmp|JPEG(*.jpg,*.jpeg)|*.jpg;*.jpeg|Gif (*.gif)|*.gif|TIFF(*.tiff)|*.tiff|PNG(*.png)|*.png|WDP(*.wdp)|*.wdp|Xps file (*.xps)|*.xps|All files (*.*)|*.*";

saveFileDialog.Filter = C_imageFilesFilter;



if (saveFileDialog.ShowDialog() == true)

 {

    chart.Save(saveFileDialog.FileName);

 }
{% endhighlight %}

### SfChart

{% highlight C# %}

SfChart sfchart = new SfChart();      

SaveFileDialog sfd = new SaveFileDialog();      

 sfd.Filter = "Bitmap(*.bmp)|*.bmp|JPEG(*.jpg,*.jpeg)|*.jpg;*.jpeg|Gif (*.gif)|*.gif|PNG(*.png)|*.png|All files (*.*)|*.*";          

  if (sfd.ShowDialog() == true)          

  {               

          using (Stream fs = sfd.OpenFile())

          {

              sfchart.Save(fs, new PngBitmapEncoder());

          }           

   }
{% endhighlight %}

##Printing Chart

### Chart

{% highlight xaml %}

<syncfusion:Chart x:Name="chart"/>

<Button Content="Print"  Command="{x:Static ApplicationCommands.Print}"

CommandTarget="{Binding ElementName=chart}"/>

<Button Content="Printing Mode" Command="{x:Staticsyncfusion:ChartCommands.SwitchPrinting}"

CommandTarget="{Binding ElementName=chart}"/>
{% endhighlight %}

### SfChart

{% highlight C# %}

SfChart chart = new SfChart();

chart.Print();


{% endhighlight %}


