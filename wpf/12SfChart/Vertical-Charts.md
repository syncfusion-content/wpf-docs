---
layout: post
title: Vertical-Charts
description: vertical charts
platform: wpf
control: SfChart
documentation: ug
---

# Vertical Charts

SfChart provide support for Vertical Charts. You can use this to change the position of x-axis and y-axis to the CartesianSeries.

The following APIs are used to change axis positions.

_Vertical Charts_

<table>
<tr>
<td>
Property</td><td>
Definition</td></tr>
<tr>
<td>
IsTransposed</td><td>
Gets or sets the bool value that represents the position change of a CartesianSeries.</td></tr>
<tr>
<td>
OpposedPosition</td><td>
Gets or sets the bool value that represents the value to draw axis at the opposite position of chart.</td></tr>
</table>


The following code example illustrates the Vertical Chart feature.



[XAML]

&lt;syncfusion:SfChart   Height="500" Width="650"&gt;

        &lt;syncfusion:SfChart.Resources&gt;

                &lt;DataTemplate x:Key="suffix"&gt;

                    &lt;TextBlock Text="K"  FontSize="14"/&gt;

                &lt;/DataTemplate&gt;

        &lt;/syncfusion:SfChart.Resources&gt;

            &lt;syncfusion:SfChart.ColumnDefinitions&gt;

                &lt;syncfusion:ChartColumnDefinition /&gt;

                &lt;syncfusion:ChartColumnDefinition /&gt;

            &lt;/syncfusion:SfChart.ColumnDefinitions&gt;

            &lt;syncfusion:SfChart.PrimaryAxis&gt;

                &lt;syncfusion:CategoryAxis FontSize="14" /&gt;

            &lt;/syncfusion:SfChart.PrimaryAxis&gt;

            &lt;syncfusion:SfChart.SecondaryAxis&gt;

                &lt;syncfusion:NumericalAxis FontSize="14" PostfixLabelTemplate="{StaticResource suffix}" OpposedPosition="True"/&gt;

            &lt;/syncfusion:SfChart.SecondaryAxis&gt;



            <syncfusion:LineSeries IsTransposed="True" XBindingPath="CompanyName" 

                 YBindingPath="CompanyTurnOver" ItemsSource="{Binding }"/>



            &lt;syncfusion:LineSeries IsTransposed="True" XBindingPath="CompanyName" YBindingPath="CompanyTurnOver" ItemsSource="{Binding }"&gt;

                &lt;syncfusion:LineSeries.YAxis&gt;

                    &lt;syncfusion:NumericalAxis FontSize="14" PlotOffset="30" PostfixLabelTemplate="{StaticResource suffix}" OpposedPosition="True" syncfusion:SfChart.Column="1"/&gt;

                &lt;/syncfusion:LineSeries.YAxis&gt;

            &lt;/syncfusion:LineSeries&gt;



        &lt;/syncfusion:SfChart&gt;



The following screenshot illustrates Vertical Chart.

{ ![C:/Users/rachel/Desktop/wpf/sshot-82.png](Vertical-Charts_images/Vertical-Charts_img1.png) | markdownify }
{:.image }


