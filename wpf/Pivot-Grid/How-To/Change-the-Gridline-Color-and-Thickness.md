---
layout: post
title: 142-Change-the-Gridline-Color-and-Thickness | Syncfusion
description: Section that helps to know how to change the color and thickness of grid lines in pivot grid control.
platform: wpf
control: PivotGridControl
documentation: ug
---

# How to change the GridLine color and thickness?

GridLine color can be changed by using the `GridLineStroke` property of PivotGrid and it can be mentioned either in *XAML* or in *Code-Behind*. 

If through *XAML*, please refer the below code sample.

{% highlight xaml %}

<syncfusion:PivotGridControl HorizontalAlignment="Left" Name="pivotGrid" VerticalAlignment="Top" GridLineStroke="#2F5BB7" ItemSource="{Binding   Source={StaticResource data}}">
</syncfusion:PivotGridControl>
     
{% endhighlight %}

Else if through *Code-Behind*, please refer the below code sample.

{% highlight C# %}

public MainWindow() {
    InitializeComponent();
    pivotGrid.GridLineStroke = new SolidColorBrush(Colors.Black);
}
		
{% endhighlight %}


