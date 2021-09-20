---
layout: post
title: ColorBar in WPF Surface Chart control | Syncfusion
description: Learn here all about ColorBar support in Syncfusion WPF Surface Chart (SfSurfaceChart) control and more.
platform: wpf
control: SfSurfaceChart
documentation: ug
---

# ColorBar in WPF Surface Chart (SfSurfaceChart)

[`ColorBar`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfSurfaceChart.html#Syncfusion_UI_Xaml_Charts_SfSurfaceChart_ColorBar) is used to represent the value range in surface via colors. You can define ColorBar for surface chart as shown in the following code example. 

Color bar position can be customized using the [`DockPosition`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartColorBar.html#Syncfusion_UI_Xaml_Charts_ChartColorBar_DockPosition) property. 
Color bar can either show or hide the labels and this can be done using the [`ShowLabel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartColorBar.html#Syncfusion_UI_Xaml_Charts_ChartColorBar_ShowLabel) property.

{% tabs %}

{% highlight xaml %}

    <chart:SfSurfaceChart ItemsSource="{Binding DataValues}"  XBindingPath="X"  
                              YBindingPath="Y" ZBindingPath="Z" RowSize="{Binding RowSize}"
                              ColumnSize="{Binding ColumnSize}">
            
            <chart:SfSurfaceChart.ColorBar>
                <chart:ChartColorBar ShowLabel="True" DockPosition="Right"></chart:ChartColorBar>
            </chart:SfSurfaceChart.ColorBar>

        </chart:SfSurfaceChart>
	
{% endhighlight %}

{% highlight c# %}

            SfSurfaceChart chart = new SfSurfaceChart();
            chart.SetBinding(SfSurfaceChart.ItemsSourceProperty, "DataValues");
            chart.SetBinding(SfSurfaceChart.RowSizeProperty, "RowSize");
            chart.SetBinding(SfSurfaceChart.ColumnSizeProperty, "ColumnSize");
            chart.XBindingPath = "X";
            chart.YBindingPath = "Y";
            chart.ZBindingPath = "Z";
            ChartColorBar colorBar = new ChartColorBar();
            colorBar.DockPosition = ChartDock.Right;
            colorBar.ShowLabel = true;
            chart.ColorBar = colorBar;
            grid.Children.Add(chart);
	
{% endhighlight %}

{% endtabs %}

The following image represents the color bar at the right side of the surface chart.

![Color bar position](surface_chart_images/ColorBar_img1.png)
