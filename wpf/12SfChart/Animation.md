---
layout: post
title: Animation
description: animation
platform: wpf
control: SfChart
documentation: ug
---

# Animation

SfChartAnimation allows you to animate the chart series on loading, and whenever the ItemsSource changes. Animation in chart can be enabled by setting the EnableAnimation property as True and defining the corresponding animation speed with AnimationDuration property.

The following types of series support Animation.

* Line
* Column
* Bar
* Area
* Scatter
* Bubble
* Spline
* Spline area
* Stacking column
* Stacking bar
* Stacking area
* Pie



The following APIs are used to customize the Animation.

_Customization API for Animation_

<table>
<tr>
<td>
Property</td><td>
Definition</td></tr>
<tr>
<td>
EnableAnimation</td><td>
Gets or sets the bool value that represents a value to enable the animation for series.</td></tr>
<tr>
<td>
AnimationDuration</td><td>
Gets or sets the TimeSpan value that represents the animation speed for the chart.</td></tr>
</table>


The following example shows the Animation feature for chart series.

[XAML]



&lt;syncfusion:SfChart&gt;

            &lt;syncfusion:ColumnSeries EnableAnimation="True" AnimationDuration="00:00:02" Palette="Metro" XBindingPath="Category" YBindingPath="Count" ItemsSource="{Binding}"/&gt;

        &lt;/syncfusion:SfChart&gt;



