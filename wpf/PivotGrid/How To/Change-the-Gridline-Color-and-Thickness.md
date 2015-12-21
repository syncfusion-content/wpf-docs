---
layout: post
title: 142-Change-the-Gridline-Color-and-Thickness
description:change the gridline color and thickness?
platform: wpf
control: PivotGridControl
documentation: ug
---

# Change the Grid-line Colour and Thickness?

GridLine colour can be changed by using the **GridLineStroke** property of PivotGrid and it can be mentioned either in *XAML* or in *Code-Behind*. 

If through **XAML**, please refer the below code snippet.

{% highlight xaml %}

<syncfusion:PivotGridControl HorizontalAlignment="Left" Name="pivotGrid" VerticalAlignment="Top" GridLineStroke="#2F5BB7" ItemSource="{Binding   Source={StaticResource data}}">
</syncfusion:PivotGridControl>
     
{% endhighlight %}

Else of through **Code-behind**, please refer the below code snippet.

{% highlight C# %}

public MainWindow() {
    InitializeComponent();
    pivotGrid.GridLineStroke = new SolidColorBrush(Colors.Black);
}
		
{% endhighlight %}


