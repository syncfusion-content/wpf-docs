---
layout: post
title: Axis
description: axis
platform: wpf
control: SfChart
documentation: ug
---

# Axis

ChartAxis is used to locate a data point inside the chart area. Generally, to locate a data point, you require two axes, along each direction, that is, horizontal and vertical, in a chart. The vertical axis, or y-axis, usually represents numerical values .The horizontal axis, or x-axis, represents categorical or numerical or date and time values. ChartAxis supports the following types.

You can choose any ChartAxis derived types, like DateTimeAxis, NumericalAxis, CategoryAxis, LogarithmicAxis or TimeSpanAxis depending on the value type. DateTimeCategoryAxis is a special type, used to plot date and time values for the given datapoints. 

## NumericAxis

NumericalAxis is used to plot numericals to the chart. You can set NumericalAxis for both PrimaryAxis and SecondaryAxis.

The following APIs are used to customize NumericalAxis.

_Properties_

<table>
<tr>
<td>
Property</td><td>
Definition</td></tr>
<tr>
<td>
Interval</td><td>
Gets or sets the double that represents the interval between the labels.</td></tr>
<tr>
<td>
Minimum</td><td>
Gets or sets the double that represents the Minimum value for the Axis.</td></tr>
<tr>
<td>
Maximum</td><td>
Gets or sets the double that represents the Maximum value for the Axis.</td></tr>
<tr>
<td>
RangePadding</td><td>
Gets or sets the NumericalPadding that specifies how to render the segments in chart area.</td></tr>
<tr>
<td>
StartRangeFromZero</td><td>
Gets or sets the bool that represents a value to enable start the range from zero. </td></tr>
</table>
 [XAML]

&lt;syncfusion:SfChart x:Name="Chart"   Margin="5,0,10,0"&gt;

            &lt;syncfusion:SfChart.DataContext&gt;

                &lt;local:ViewModel/&gt;

            &lt;/syncfusion:SfChart.DataContext&gt;

            &lt;syncfusion:SfChart.PrimaryAxis&gt;

                &lt;syncfusion:CategoryAxis   Header="Company Name"/&gt;

            &lt;/syncfusion:SfChart.PrimaryAxis&gt;

            &lt;syncfusion:SfChart.SecondaryAxis&gt;

                &lt;syncfusion:NumericalAxis Interval="100" Minimum="0" Maximum="1000" RangePadding="Round"   Header="Gross Revenue "/&gt;

            &lt;/syncfusion:SfChart.SecondaryAxis&gt;



            &lt;syncfusion:ColumnSeries x:Name="series1" Label="Company Details"   XBindingPath="CompanyName" YBindingPath="CompanyTurnOver"   ItemsSource="{Binding CompanyDetails}"&gt;

            &lt;/syncfusion:ColumnSeries&gt;

        &lt;/syncfusion:SfChart&gt;



{ ![C:/Users/rachel/Desktop/wpf/chart3.png](Axis_images/Axis_img1.png) | markdownify }
{:.image }


## CategoryAxis

CategoryAxis is an index based axis that plots values based on the index of the data point collection. The points are equally spaced here.

The following APIs are used in CategoryAxis.

_CategoryAxis_

<table>
<tr>
<td>
Property</td><td>
Definition</td></tr>
<tr>
<td>
Interval</td><td>
Gets or sets the double value that represents the interval between the labels.</td></tr>
<tr>
<td>
LabelPlacement</td><td>
Gets or sets the LabelPlacement that represents the position of the label in the axis.</td></tr>
</table>


[XAML]



&lt;syncfusion:SfChart x:Name="Chart"   Margin="5,0,10,0"&gt;

                &lt;syncfusion:SfChart.DataContext&gt;

                    &lt;local:ViewModel/&gt;

                &lt;/syncfusion:SfChart.DataContext&gt;



                &lt;syncfusion:SfChart.PrimaryAxis&gt;

                    &lt;syncfusion:CategoryAxis   Header="Company Name"/&gt;

                &lt;/syncfusion:SfChart.PrimaryAxis&gt;



                &lt;syncfusion:SfChart.SecondaryAxis&gt;

                    &lt;syncfusion:NumericalAxis Interval="10" Minimum="200" Maximum="400" RangePadding="Round"   Header="Gross Revenue "/&gt;

                &lt;/syncfusion:SfChart.SecondaryAxis&gt;



                &lt;syncfusion:ColumnSeries x:Name="series1" Label="Company Details"   XBindingPath="CompanyName" YBindingPath="CompanyTurnOver"   ItemsSource="{Binding CompanyDetails}"&gt;

                &lt;/syncfusion:ColumnSeries&gt;



            &lt;/syncfusion:SfChart&gt;



{ ![C:/Users/rachel/Desktop/wpf/chart3.png](Axis_images/Axis_img2.png) | markdownify }
{:.image }


## DateTimeAxis

DateTimeAxis is used to plot DateTime values. The DateTimeAxis is widely used to make financial charts in places like the Stock Market, where index plotting is done everyday.

The following APIs are used for customizing DateTimeAxis.

_DateTimeAxis_

<table>
<tr>
<td>
Property</td><td>
Definition</td></tr>
<tr>
<td>
Minimum</td><td>
Gets or sets the DateTime value that represents a minimum value of the Axis.</td></tr>
<tr>
<td>
Maximum</td><td>
Gets or sets the DateTime value that represents a maximum value of the Axis.</td></tr>
<tr>
<td>
RangePadding</td><td>
Gets or sets the DateTimeRangePadding value that specifies segment arrangement in the chart area.</td></tr>
<tr>
<td>
Interval</td><td>
Gets or sets the double value as the interval between labels.</td></tr>
<tr>
<td>
IntervalType</td><td>
Gets or sets the DateTimeIntervalType. It represents the type of the interval. This property is used to define the type of interval to be displayed and considered for plotting the series.</td></tr>
<tr>
<td>
EnableBusinessHours</td><td>
Gets or sets the bool value that represents a value to enable business hours.</td></tr>
<tr>
<td>
OpenTime</td><td>
Gets or sets the double value that represents the open working time of a day.</td></tr>
<tr>
<td>
CloseTime</td><td>
Gets or sets the double value that represents the close working time of a day.</td></tr>
<tr>
<td>
WorkingDays</td><td>
Gets or sets the double value that represents the working days of a week.</td></tr>
</table>
DateTimeIntervalType

The DateTime interval corresponds to the type specified in the IntervalType property.

For instance, if the Interval is set as 2 and IntervalType is set as Days, the labels are plotted for every two days. The following are the values for IntervalType property:

* Auto
* Days
* Hours
* Milliseconds
* Minutes 
* Months
* Seconds
* Years



The default IntervalType of a DateTimeAxis is Auto. It calculates the type automatically and the interval, accordingly.

[XAML]

&lt;syncfusion:SfChart.PrimaryAxis&gt;

                <syncfusion:DateTimeAxis Name="Primary" 

                                    IntervalType="Years" Interval="1" />

            &lt;/syncfusion:SfChart.PrimaryAxis&gt;



The following code example and screenshot are for DateTimeAxis.

[XAML]



  &lt;syncfusion:SfChart x:Name="Chart"   Margin="5,0,10,0"&gt;

            &lt;syncfusion:SfChart.DataContext&gt;

                &lt;local:ViewModel/&gt;

            &lt;/syncfusion:SfChart.DataContext&gt;



            &lt;syncfusion:SfChart.PrimaryAxis&gt;

                &lt;syncfusion:DateTimeAxis Interval="1" LabelFormat="yyyy" IntervalType="Years”/&gt;

            &lt;/syncfusion:SfChart.PrimaryAxis&gt;



            &lt;syncfusion:SfChart.SecondaryAxis&gt;

                &lt;syncfusion:NumericalAxis /&gt;

            &lt;/syncfusion:SfChart.SecondaryAxis&gt;



            &lt;syncfusion:LineSeries x:Name="series1" Label="Company Details"   XBindingPath="Year" YBindingPath="CompanyTurnOver"  ItemsSource="{Binding CompanyDetails}"&gt;

            &lt;/syncfusion:LineSeries&gt;

        &lt;/syncfusion:SfChart&gt;



{ ![C:/Users/rachel/Desktop/wpf/sshot-3.png](Axis_images/Axis_img3.png) | markdownify }
{:.image }


## DateTimeCategoryAxis

DateTimeCategoryAxis is a special type of axis used mainly with financial series. All the data points are plotted with equal spaces, similar to CategoryAxis, thereby removing space for missing dates. Intervals and range for the axis are calculated similar to DateTimeAxis. There are no visual gaps between points, even when the difference between two points is more than a year.

_DateTimeCategoryAxis_

<table>
<tr>
<td>
Property</td><td>
Definition</td></tr>
<tr>
<td>
Interval</td><td>
Gets or sets the double value that represents the interval between the labels.</td></tr>
<tr>
<td>
IntervalType</td><td>
Gets or sets the DateTimeIntervalType that represents the type of the interval.</td></tr>
</table>


[XAML]



&lt;syncfusion:SfChart x:Name="Chart"   Margin="5,0,10,0"&gt;

            &lt;syncfusion:SfChart.DataContext&gt;

                &lt;local:ViewModel/&gt;

            &lt;/syncfusion:SfChart.DataContext&gt;



            &lt;syncfusion:SfChart.PrimaryAxis&gt;

                &lt;syncfusion:DateTimeCategoryAxis Interval="1" LabelFormat="yyyy" IntervalType="Years"  Header="Company Name"/&gt;

            &lt;/syncfusion:SfChart.PrimaryAxis&gt;



            &lt;syncfusion:SfChart.SecondaryAxis&gt;

                &lt;syncfusion:NumericalAxis   Header="Gross Revenue (cr.)"/&gt;

            &lt;/syncfusion:SfChart.SecondaryAxis&gt;



            &lt;syncfusion:LineSeries x:Name="series1" Label="Company Details"   XBindingPath="Year" YBindingPath="CompanyTurnOver"   ItemsSource="{Binding CompanyDetails}"&gt;

            &lt;/syncfusion:LineSeries&gt;



        &lt;/syncfusion:SfChart&gt;



{ ![C:/Users/rachel/Desktop/wpf/sshot-3.png](Axis_images/Axis_img4.png) | markdownify }
{:.image }


## TimeSpanAxis

TimeSpanAxis is used to plot the time span values in the PrimaryAxis. TimeSpanAxis has the advantage of plotting data with milliseconds difference. The limitation of TimeSpanAxis is that it can only accept timespan values (hh:mm:ss) and datetime values are not accepted.

The following APIs are used in TimeSpanAxis.

_TimeSpanAxis_

<table>
<tr>
<td>
Property</td><td>
Definition</td></tr>
<tr>
<td>
Interval</td><td>
Gets or sets the double value that represents the interval between the labels.</td></tr>
<tr>
<td>
Minimum</td><td>
Gets or sets the timespan value that represents the minimum value for the Axis.</td></tr>
<tr>
<td>
Maximum</td><td>
Gets or sets the timespan value that represents the maximum value for the Axis. </td></tr>
</table>


[XAML]

 &lt;syncfusion:SfChart x:Name="Chart"   Margin="5,0,10,0"&gt;

            &lt;syncfusion:SfChart.DataContext&gt;

                &lt;local:ViewModel/&gt;

            &lt;/syncfusion:SfChart.DataContext&gt;



            &lt;syncfusion:SfChart.PrimaryAxis&gt;

                &lt;syncfusion:TimeSpanAxis Interval="00:00:01" Header="Company Name"/&gt;

            &lt;/syncfusion:SfChart.PrimaryAxis&gt;



            &lt;syncfusion:SfChart.SecondaryAxis&gt;

                &lt;syncfusion:NumericalAxis   Header="Gross Revenue (cr.)"/&gt;

            &lt;/syncfusion:SfChart.SecondaryAxis&gt;

            &lt;syncfusion:LineSeries x:Name="series1" Label="Company Details"   XBindingPath="Year" YBindingPath="CompanyTurnOver"  ItemsSource="{Binding CompanyDetails}"&gt;

            &lt;/syncfusion:LineSeries&gt;

        &lt;/syncfusion:SfChart&gt;



{ ![](Axis_images/Axis_img5.png) | markdownify }
{:.image }


## LogarithmicAxis

LogarithmicAxis is used to plot the logarithmic scale for the chart. In order to plot the logarithmic scale, you must specify the base value using LogarithmicBase Property.

The following APIs are used to customize the LogarithmicAxis.

_LogarithmicAxis_

<table>
<tr>
<td>
Property</td><td>
Definition</td></tr>
<tr>
<td>
Interval</td><td>
Gets or sets the double value that represents the interval between the labels</td></tr>
<tr>
<td>
Minimum</td><td>
Gets or sets the double value that represents the minimum value for the Axis.</td></tr>
<tr>
<td>
Maximum</td><td>
Gets or sets the double value that represents the maximum value of the Axis. </td></tr>
<tr>
<td>
LogarithmicBase</td><td>
Gets or sets the double value that represents the logarithmic base value of the Axis.</td></tr>
</table>


[XAML]



&lt;syncfusion:SfChart x:Name="Chart"   Margin="5,0,10,0"&gt;

            &lt;syncfusion:SfChart.DataContext&gt;

                &lt;local:ViewModel/&gt;

            &lt;/syncfusion:SfChart.DataContext&gt;



            &lt;syncfusion:SfChart.PrimaryAxis&gt;

                &lt;syncfusion:CategoryAxis   Header="Company Name"/&gt;

            &lt;/syncfusion:SfChart.PrimaryAxis&gt;



            &lt;syncfusion:SfChart.SecondaryAxis&gt;

                &lt;syncfusion:LogarithmicAxis LogarithmicBase="10"   Header="Gross Revenue (cr.)"/&gt;

            &lt;/syncfusion:SfChart.SecondaryAxis&gt;

            &lt;syncfusion:LineSeries x:Name="series1" Label="Company Details"   XBindingPath="CompanyName" YBindingPath="CompanyTurnOver"   ItemsSource="{Binding CompanyDetails}"&gt;

            &lt;/syncfusion:LineSeries&gt;



        &lt;/syncfusion:SfChart&gt;



> _Note: Logarithmic Axis does not support zero or negative values._

The following screenshot illustrates the SfChart with LogarithmicAxis.

{ ![C:/Users/rachel/Desktop/wpf/sshot-5.png](Axis_images/Axis_img6.png) | markdownify }
{:.image }


## Multiple Axes

SfChart provides a way to arrange multiple series inside the same chart area, giving the chart more space than x-axis and y-axis.These axes can be arranged in a stack or in a side by side pattern. 

By default, all the series are plotted based on Primary and Secondary Axis. You can add more axes by adding additional axis to the series. There are two properties XAxis and YAxis in all the series, except Accumulation Series.

 [XAML]



 <syncfusion:ColumnSeries Label="2010" 

     ItemsSource="{Binding Demands}"

     XBindingPath="Demand"

     YBindingPath="Year2010"

     Interior="Green"

     >

            &lt;syncfusion:ColumnSeries.XAxis&gt;

                &lt;syncfusion:NumericalAxis Header="Additional X Axis"/&gt;

            &lt;/syncfusion:ColumnSeries.XAxis&gt;



            &lt;syncfusion:ColumnSeries.YAxis&gt;

                &lt;syncfusion:NumericalAxis Header="Additional Y Axis"/&gt;

            &lt;/syncfusion:ColumnSeries.YAxis&gt;



        &lt;/syncfusion:ColumnSeries&gt;



        <syncfusion:LineSeries Label="2011" 

    ItemsSource="{Binding Demands}"

    XBindingPath="Demand"

    YBindingPath="Year2011"

    Interior="Black"

    StrokeThickness="2"

    />





The following screenshot illustrates SfChart with multiple axes.

{ ![C:/Users/rachel/Desktop/snaps/6.png](Axis_images/Axis_img7.png) | markdownify }
{:.image }


> _Note: The first series is plotting based on additional X & Y axis and second series (or remaining series) is plotting against the Primary and Secondary axis._

Axis Positioning

By default, the x-axis is arranged horizontally at the bottom of the chart and the y-axis is arranged vertically on the left-side of the chart. You can change the alignment of the axes by setting OpposedPosition to True. It arranges the x-axis at the top and the y-axis on the right-side of the chart. 

The following is the code example for setting the OpposedPosition property.

[XAML]



&lt;syncfusion:ColumnSeries.XAxis&gt;

            &lt;syncfusion:NumericalAxis Header="Additional X Axis" OpposedPosition="True"/&gt;

        &lt;/syncfusion:ColumnSeries.XAxis&gt;



        &lt;syncfusion:ColumnSeries.YAxis&gt;

            &lt;syncfusion:NumericalAxis Header="Additional Y Axis" OpposedPosition="True"/&gt;

        &lt;/syncfusion:ColumnSeries.YAxis&gt;

The following is a screenshot demonstrating y-axis of a chart arranged in OpposedPosition.

{ ![C:/Users/rachel/Desktop/snaps/7.png](Axis_images/Axis_img8.png) | markdownify }
{:.image }


## Inversed Axis

This feature is used to reverse chart plotting inverse the axis scaling.

[XAML]

&lt;syncfusion:SfChart.PrimaryAxis&gt;

                &lt;syncfusion:CategoryAxis   FontSize="16" IsInversed="True" OpposedPosition="True" /&gt;

            &lt;/ syncfusion:SfChart.PrimaryAxis&gt;



            &lt;syncfusion:SfChart.SecondaryAxis&gt;

                &lt;syncfusion:NumericalAxis FontSize="16" Minimum="0" Maximum="2000" Interval=”200” IsInversed="True" OpposedPosition="True" /&gt;

            &lt;/syncfusion:SfChart.SecondaryAxis&gt;



{ ![C:/Users/rachel/Desktop/snaps/8.png](Axis_images/Axis_img9.png) | markdownify }
{:.image }


## Axis range and Interval

ChartAxis calculates the range and intervals automatically based on the values of series data points. You can also explicitly specify the range and interval using the Minimum, Maximum and Interval properties. 

> _Tip: You cannot specify range for CategoryAxis instead you can use ZoomFactor and ZoomPosition._



> _Note: You can force the NumericalAxis to start range from zero by enabling StartRangeFromZero. The following is the code example for setting the ChartAxis properties._

 The following is the code sample for setting the ChartAxis properties:

[XAML]

&lt;syncfusion:SfChart.PrimaryAxis&gt;

                &lt;syncfusion:CategoryAxis FontSize="14"/&gt;

            &lt;/syncfusion:SfChart.PrimaryAxis&gt;



            &lt;syncfusion:SfChart.SecondaryAxis&gt;

                &lt;syncfusion:NumericalAxis FontSize="14"/&gt;

            &lt;/syncfusion:SfChart.SecondaryAxis&gt;

Range Padding

The NumericalAxis and DateTimeAxis have a RangePadding property that can be used to add padding to the range of a chart's axes.

NumericalAxis RangePadding

The following types are available for NumericalAxis: 

* Additional
* None
* Normal
* Round

By default, the default RangePadding value for PrimaryAxis is Auto and for SecondaryAxis, the default value is Round.

{ ![C:/Users/rachel/Desktop/wpf/sshot-109.png](Axis_images/Axis_img10.png) | markdownify }
{:.image }


The following screenshot demonstrates RangePadding as None, where no padding is applied for the axis.

{ ![](Axis_images/Axis_img11.png) | markdownify }
{:.image }


Normal RangePadding for a NumericalAxis is used mostly for the y-axis to have padding based on the Range calculation.

The following screenshot illustrates a chart’s y-axis with RangePadding set to Normal.

{ ![C:/Users/rachel/Desktop/wpf/sshot-11.png](Axis_images/Axis_img12.png) | markdownify }
{:.image }


Round RangePadding for a NumericalAxis rounds the range of the chart axis to the nearest possible value.

The following screenshot demonstrates a chart’s x-axis with RangePadding set to Round.

{ ![](Axis_images/Axis_img13.png) | markdownify }
{:.image }


If RangePadding for NumericalAxis is set to Additional, the interval of the axis is added as padding.

The following screenshot demonstrates a chart’s x-axis with RangePadding set to Additional.

{ ![](Axis_images/Axis_img14.png) | markdownify }
{:.image }


DateTimeAxis RangePadding

The RangePadding types available in the DateTimeAxis are: 

* Additional
* None
* Round

By default, the RangePadding for a DateTimeAxis is None.

The following screenshot demonstrates a chart’s x-axis with RangePadding set to None. 

{ ![C:/Users/rachel/Desktop/wpf/sshot-9.png](Axis_images/Axis_img15.png) | markdownify }
{:.image }


When RangePadding for DateTimeAxis is set to Additional, the DateTime interval of the axis is added as padding, as shown in the following screenshot.

{ ![C:/Users/rachel/Desktop/wpf/sshot-10.png](Axis_images/Axis_img16.png) | markdownify }
{:.image }


When RangePadding for DateTimeAxis is set to Round, the range of the chart axis is rounded off to the nearest possible DateTime value, as shown in the following screenshot.

{ ![C:/Users/rachel/Desktop/wpf/sshot-9.png](Axis_images/Axis_img17.png) | markdownify }
{:.image }


## Positioning axis labels

Label Placement

The CategoryAxis includes the LabelPlacement property, used to set the labels of the axis between the tick lines or on the tick lines of the category axis. By default the LabelPlacement value for the CategoryAxis is OnTicks.

There are two types of LabelPlacement:

* BetweenTicks
* OnTicks

The following code example and screenshot shows LabelPlacement set to OnTicks.

[XAML]

  &lt;syncfusion:SfChart.PrimaryAxis&gt;

     <syncfusion:CategoryAxis LabelPlacement="OnTicks" 

         FontSize="16"  />

 &lt;/syncfusion:SfChart.PrimaryAxis&gt;



{ ![C:/Users/rachel/Desktop/wpf/sshot-15.png](Axis_images/Axis_img18.png) | markdownify }
{:.image }


The following code example and screenshot shows LabelPlacement set to BetweenTicks.

[XAML]



  &lt;syncfusion:SfChart.PrimaryAxis&gt;

    <syncfusion:CategoryAxis LabelPlacement="BetweenTicks" 

           FontSize="16"  />

    &lt;/syncfusion:SfChart.PrimaryAxis&gt;





{ ![C:/Users/rachel/Desktop/wpf/sshot-16.png](Axis_images/Axis_img19.png) | markdownify }
{:.image }


Label Position 

The LabelsPosition property is used to position the axis label either inside or outside the chart plotting area.

The following code example and screenshot illustrate the use of LabelsPosition.

[XAML]

  &lt;syncfusion:SfChart.PrimaryAxis&gt;

    <syncfusion:CategoryAxis  LabelsPosition="Inside" 

           FontSize="16"  />

    &lt;/syncfusion:SfChart.PrimaryAxis&gt;



{ ![C:/Users/rachel/Desktop/wpf/sshot-17.png](Axis_images/Axis_img20.png) | markdownify }
{:.image }


[XAML]

  &lt;syncfusion:SfChart.PrimaryAxis&gt;

    <syncfusion:CategoryAxis  LabelsPosition="Outside" 

           FontSize="16"  />

    &lt;/syncfusion:SfChart.PrimaryAxis&gt;



{ ![C:/Users/rachel/Desktop/wpf/sshot-18.png](Axis_images/Axis_img21.png) | markdownify }
{:.image }


Positioning Edge Labels

SfChart provides support to customize the edge labels of the axis to adjust its position using the EdgeLabelDrawingMode property. 

The following are the customizing options in EdgeLabelDrawingMode.

* Center- Positions the label with tickline as center.
* Fit- Position the gridline inside based on the edge label size.
* Hide- Hides the edge labels.
* Shift- Shifts the edge labels inside to label width.



The following code example and screenshot show EdgeLabelsDrawingMode set to Center.

[XAML]

  &lt;syncfusion:SfChart.PrimaryAxis&gt;

  &lt;syncfusion:DateTimeAxis    LabelFormat="MM/yy" EdgeLabelsDrawingMode="Center" FontSize="16"  /&gt;

    &lt;/syncfusion:SfChart.PrimaryAxis&gt;



{ ![C:/Users/rachel/Desktop/wpf/sshot-19.png](Axis_images/Axis_img22.png) | markdownify }
{:.image }


The following code example and screenshot shows EdgeLabelsDrawingMode set to Fit.

[XAML]

  &lt;syncfusion:SfChart.PrimaryAxis&gt;

  &lt;syncfusion:DateTimeAxis    LabelFormat="MM/yy" EdgeLabelsDrawingMode="Fit" FontSize="16"  /&gt;

    &lt;/syncfusion:SfChart.PrimaryAxis&gt;



{ ![C:/Users/rachel/Desktop/wpf/sshot-20.png](Axis_images/Axis_img23.png) | markdownify }
{:.image }


The following code example and screenshot shows EdgeLabelDrawingMode set to Hide.

[XAML]

  &lt;syncfusion:SfChart.PrimaryAxis&gt;

  &lt;syncfusion:DateTimeAxis    LabelFormat="MM/yy" EdgeLabelsDrawingMode="Hide" FontSize="16"  /&gt;

    &lt;/syncfusion:SfChart.PrimaryAxis&gt;



{ ![C:/Users/rachel/Desktop/wpf/sshot-21.png](Axis_images/Axis_img24.png) | markdownify }
{:.image }


The following code example and screenshot shows EdgeLabelsDrawingMode set to Shift.

[XAML]

  &lt;syncfusion:SfChart.PrimaryAxis&gt;

  &lt;syncfusion:DateTimeAxis    LabelFormat="MM/yy" EdgeLabelsDrawingMode="Shift" FontSize="16"  /&gt;

    &lt;/syncfusion:SfChart.PrimaryAxis&gt;



{ ![C:/Users/rachel/Desktop/wpf/sshot-22.png](Axis_images/Axis_img25.png) | markdownify }
{:.image }


## Smart Labels

When a number of axis labels exist, they may overlap with each other. SfChart provides features to handle the overlapping labels using the LabelsIntersectAction property.

The following are the options for intersecting action.

* None
* Hide
* MultipleRows



The following code example and screenshot shows LabelsIntersectAction set to None.

[XAML]

  &lt;syncfusion:SfChart.PrimaryAxis&gt;

    <syncfusion:DateTimeAxis   LabelsIntersectAction="None"  

           FontSize="16"  />

    &lt;/syncfusion:SfChart.PrimaryAxis&gt;



{ ![C:/Users/rachel/Desktop/wpf/sshot-23.png](Axis_images/Axis_img26.png) | markdownify }
{:.image }


The following code example and screenshot shows LabelsIntersectAction set to Hide.

[XAML]

  &lt;syncfusion:SfChart.PrimaryAxis&gt;

    <syncfusion:DateTimeAxis   LabelsIntersectAction="Hide"  

           FontSize="16"  />

    &lt;/syncfusion:SfChart.PrimaryAxis&gt;



{ ![C:/Users/rachel/Desktop/wpf/sshot-24.png](Axis_images/Axis_img27.png) | markdownify }
{:.image }


The following code example and screenshot show LabelsIntersectAction set to MultipleRows.

[XAML]



  &lt;syncfusion:SfChart.PrimaryAxis&gt;

    <syncfusion:DateTimeAxis   LabelsIntersectAction="MultipleRows"  

           FontSize="16"  />

    &lt;/syncfusion:SfChart.PrimaryAxis&gt;





{ ![C:/Users/rachel/Desktop/wpf/sshot-25.png](Axis_images/Axis_img28.png) | markdownify }
{:.image }


## Add units to labels

You can customize the axis label to display its measuring units by adding a prefix or a suffix. This feature can be achieved using the PrefixLabelTemplate and PostfixLabelTemplate properties.

The following code example and screenshot demonstrate the usage of PrefixLabelTemplate.

[XAML]

  &lt;DataTemplate x:Key="yPrefix"&gt;

     &lt;TextBlock FontSize="15" VerticalAlignment="Center" Text="$"/&gt;

  &lt;/DataTemplate&gt;

&lt;syncfusion:SfChart.SecondaryAxis&gt;

       &lt;syncfusion:NumericalAxis FontSize="16" Minimum="0" Maximum="1000" PrefixLabelTemplate="{StaticResource yPrefix}" /&gt;

&lt;/syncfusion:SfChart.SecondaryAxis&gt;



{ ![C:/Users/rachel/Desktop/wpf/sshot-26.png](Axis_images/Axis_img29.png) | markdownify }
{:.image }


The following code example and screenshot demonstrate the usage of PostfixLabelTemplate.

[XAML]

  &lt;DataTemplate x:Key="yPostfix"&gt;

       &lt;TextBlock FontSize="8" VerticalAlignment="Top" Text="0"/&gt;

 &lt;/DataTemplate&gt;

&lt;chart:SfChart.SecondaryAxis&gt;

       &lt;chart:NumericalAxis FontSize="16" Minimum="0" Maximum="100" PostfixLabelTemplate="{StaticResource yPostfix}" /&gt;

&lt;/chart:SfChart.SecondaryAxis&gt;



{ ![C:/Users/rachel/Desktop/wpf/sshot-27.png](Axis_images/Axis_img30.png) | markdownify }
{:.image }


## Formatting axis labels

SfChart provides the LabelFormat property for defining the custom formatting for the axis labels. This property supports all standard formatting type of numerical and date time values.

[XAML#]

 &lt;syncfusion:SfChart.PrimaryAxis&gt;

      &lt;syncfusion:DateTimeAxis LabelFormat="hh:mm tt" IntervalType="Hours" Interval="1" Header="Computer sales" /&gt;

&lt;/syncfusion:SfChart.PrimaryAxis&gt;



&lt;syncfusion:SfChart.SecondaryAxis&gt;

      &lt;syncfusion:NumericalAxis Header="Quantity Sold" LabelFormat="##.00"/&gt;

&lt;/syncfusion:SfChart.SecondaryAxis&gt;



{ ![](Axis_images/Axis_img31.png) | markdownify }
{:.image }


## Styling Header and Labels

SfChart provides support to customize the axis header and label. The following APIs are used to customize the header and label.

_HeaderStyle and LabelStyle_

<table>
<tr>
<td>
Property</td><td>
Definition</td></tr>
<tr>
<td>
HeaderStyle</td><td>
Gets or sets the style for the axis header. The header’s Foreground, FontSize and FontFamily are customized using this property.</td></tr>
<tr>
<td>
LabelStyle</td><td>
Gets or sets the style for the axis labels. The label’s Foreground, FontSize and FontFamily are customized using this property.</td></tr>
</table>


[XAML]

&lt;syncfusion:SfChart Height="250" Width="500"&gt;

            &lt; syncfusion:SfChart.PrimaryAxis&gt;

                &lt; syncfusion:CategoryAxis  Header="City"&gt;

                    &lt; syncfusion:CategoryAxis.LabelStyle&gt;

                        &lt; syncfusion:LabelStyle FontSize="10" FontFamily="Arial" Foreground="Green" &gt;&lt;/syncfusion:LabelStyle&gt;

                    &lt;/syncfusion:CategoryAxis.LabelStyle&gt;

                &lt;/syncfusion:CategoryAxis&gt;

            &lt;/syncfusion:SfChart.PrimaryAxis&gt;

            &lt;syncfusion:SfChart.SecondaryAxis&gt;

                &lt;syncfusion:NumericalAxis x:Name="axis" Header="Year" &gt;

                    &lt;syncfusion:NumericalAxis.LabelStyle &gt;

                        &lt;syncfusion:LabelStyle FontSize="10" Foreground="Green" FontFamily="Arial" &gt;&lt;/syncfusion:LabelStyle&gt;

                    &lt;/syncfusion:NumericalAxis.LabelStyle&gt;

                &lt;/syncfusion:NumericalAxis&gt;

            &lt;/syncfusion:SfChart.SecondaryAxis&gt;

            &lt;syncfusion:LineSeries XBindingPath="City" YBindingPath="Year1950" ItemsSource="{Binding PopulationPercent}"&gt;&lt;/syncfusion:LineSeries&gt;

        &lt;/syncfusion:SfChart&gt;

## GridLines and TickLines 

GridLines

By default, gridlines are automatically added to the ChartAxis in its defined intervals. SfChart supports customization of gridline. You can control the visibility of the gridlines using the ShowGridLines property. 

The following code example and screenshot show ShowGridLines set to False.

[XAML]

  &lt;syncfusion:SfChart.PrimaryAxis&gt;

    <syncfusion:CategoryAxis ShowGridLines="False" 

           FontSize="16"  />

    &lt;/syncfusion:SfChart.PrimaryAxis&gt;



{ ![C:/Users/rachel/Desktop/wpf/sshot-112.png](Axis_images/Axis_img32.png) | markdownify }
{:.image }


Ticklines

Ticklines are small markers extending from the gridlines, used to indicate the axis scaling. Tickline can be positioned either inside or outside of the axis line.

The following code example and screenshot illustrate major and small ticklines set to Inside.

[XAML]

   &lt;syncfusion:SfChart.PrimaryAxis&gt;

&lt;syncfusion:NumericalAxis LabelsPosition="Inside" TickLineSize="10" SmallTickLineSize="5" TickLinesPosition="Inside" SmallTickLinesPosition="Inside" SmallTicksPerInterval="2"  FontSize="16"  /&gt;

            &lt;/syncfusion:SfChart.PrimaryAxis&gt;



{ ![C:/Users/rachel/Desktop/wpf/sshot-28.png](Axis_images/Axis_img33.png) | markdownify }
{:.image }


You can customize the appearance of major gridline, minor gridlines and ticklines using the MajorTickLineStyle, MinorTickLineStyle, MajorGridLineStyle and MinorGridLineStyle properties. Also axis lines can be customized using AxisLineStyle as follows.

[XAML]

&lt;syncfusion:SfChart&gt;

   &lt;syncfusion:SfChart.Resources&gt;

                &lt;Style x:Key="majorTickLineStyle" TargetType="Line"&gt;

                    &lt;Setter Property="Stroke" Value="Red"/&gt;

                    &lt;Setter Property="StrokeThickness" Value="1"/&gt;

                &lt;/Style&gt;

                &lt;Style x:Key="minorTickLineStyle" TargetType="Line"&gt;

                    &lt;Setter Property="Stroke" Value="Green"/&gt;

                    &lt;Setter Property="StrokeThickness" Value="1"/&gt;

                &lt;/Style&gt;

                &lt;Style x:Key="axisLineStyle" TargetType="Line"&gt;

                    &lt;Setter Property="Stroke" Value="OrangeRed"/&gt;

                    &lt;Setter Property="StrokeThickness" Value="1"/&gt;

                &lt;/Style&gt;

                &lt;Style x:Key="majorGridLineStyle" TargetType="Line"&gt;

                &lt;Setter Property="Stroke" Value="Gray"/&gt;

                &lt;Setter Property="StrokeThickness" Value="1"/&gt;

                    &lt;Setter Property="StrokeDashArray" Value="4,2"/&gt;

                 &lt;/Style&gt;

                &lt;Style x:Key="minorGridLineStyle" TargetType="Line"&gt;

                    &lt;Setter Property="Stroke" Value="Gray"/&gt;

                    &lt;Setter Property="StrokeThickness" Value="1"/&gt;

                    &lt;Setter Property="StrokeDashArray" Value="1,2"/&gt;

                &lt;/Style&gt;

  &lt;/syncfusion:SfChart.Resources&gt;



  &lt;syncfusion:SfChart.PrimaryAxis&gt;

                <syncfusion:DateTimeAxis  MajorGridLineStyle="{StaticResource majorGridLineStyle }"

                    MinorGridLineStyle="{StaticResource minorGridLineStyle}"

                    MajorTickLineStyle="{StaticResource majorTickLineStyle}"

                    MinorTickLineStyle="{StaticResource minorTickLineStyle}"

                    AxisLineStyle="{StaticResource axisLineStyle}"       

                    SmallTicksPerInterval="1" TickLineSize="10"

                    SmallTickLineSize="6" LabelFormat="yyyy"

                   />

            &lt;/syncfusion:SfChart.PrimaryAxis&gt;

            &lt;syncfusion:SfChart.SecondaryAxis&gt;

                <syncfusion:NumericalAxis MajorTickLineStyle="{StaticResource majorTickLineStyle}"

                      MajorGridLineStyle="{StaticResource majorGridLineStyle }"

                      MinorGridLineStyle="{StaticResource minorGridLineStyle}"

                      MinorTickLineStyle="{StaticResource minorTickLineStyle}"

                      AxisLineStyle="{StaticResource axisLineStyle}"       

                      SmallTicksPerInterval="1" TickLineSize="10"

                      SmallTickLineSize="5" HorizontalAlignment="Right"  

            &lt;/syncfusion:SfChart.SecondaryAxis&gt;



            &lt;syncfusion:FastLineBitmapSeries   XBindingPath="Date" YBindingPath="Value" &gt;

            &lt;/syncfusion:FastLineBitmapSeries&gt;

        &lt;/syncfusion:SfChart&gt;



{ ![C:/Users/rachel/Desktop/wpf/sshot-29.png](Axis_images/Axis_img34.png) | markdownify }
{:.image }


