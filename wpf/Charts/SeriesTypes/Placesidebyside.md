---
layout: post
title: Side By Side Placement in WPF Charts control | Syncfusion
description: Learn here all about Side By Side Placement support in Syncfusion® WPF Charts (SfChart) control and more.
platform: wpf
control: SfChart
documentation: ug
---

# Side By Side Placement in WPF Charts (SfChart)

Side by side placement defines how bar-type series (such as Column, Bar, RangeColumn, etc.) are arranged in the chart.

The [`SideBySideSeriesPlacement`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_SideBySideSeriesPlacement) is a Boolean property with a default value of `true`, which places segments adjacent to each other (clustered).

![Column Placed Side by Side in WPF Chart](Series_images/wpf-chart-placed-side-by-side.jpeg)

## Overlapping Series

When you set [`SideBySideSeriesPlacement`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_SideBySideSeriesPlacement) to `false`, the series will be placed one over another (overlapped) as shown in the following example:

{% tabs %}

{% highlight xaml %}
<chart:SfChart x:Name="columnChart" 
               AreaBorderBrush="DarkGray" 
               Header="Usage of Metals"  
               SideBySideSeriesPlacement="False"
               AreaBorderThickness="1,1,1,1">
    
    <chart:SfChart.PrimaryAxis>
        <chart:CategoryAxis Header="Metals"/>
    </chart:SfChart.PrimaryAxis>
    
    <chart:SfChart.SecondaryAxis>
        <chart:NumericalAxis Header="Usage" />                            
    </chart:SfChart.SecondaryAxis>
    
    <chart:SfChart.Legend>
        <chart:ChartLegend Visibility="Visible" />
    </chart:SfChart.Legend>
    
    <chart:ColumnSeries Interior="#bcbcbc"
                        ItemsSource="{Binding SneakersDetail}" 
                        Label="2015"  
                        XBindingPath="Brand" 
                        YBindingPath="ItemsCount" />
    
    <chart:ColumnSeries ItemsSource="{Binding SneakersDetail}"  
                        SegmentSpacing="0.5"
                        Interior="#4a4a4a"  
                        XBindingPath="Brand" 
                        Label="2014" 
                        YBindingPath="postion"/>            
</chart:SfChart>
{% endhighlight %}

{% highlight C# %}
SfChart chart = new SfChart();
chart.Header = "Usage of Metals";
chart.AreaBorderBrush = new SolidColorBrush(Colors.DarkGray);
chart.SideBySideSeriesPlacement = false;
chart.AreaBorderThickness = new Thickness(1);

chart.PrimaryAxis = new CategoryAxis()
{
    Header = "Metals"
};

chart.SecondaryAxis = new NumericalAxis()
{
    Header = "Usage"
};

chart.Legend = new ChartLegend()
{
    Visibility = Visibility.Visible
};

ColumnSeries columnSeries1 = new ColumnSeries()
{
    ItemsSource = new ViewModel().SneakersDetail,
    XBindingPath = "Brand",
    YBindingPath = "ItemsCount",
    Label = "2015",
    Interior = new SolidColorBrush(Color.FromRgb(0xbc, 0xbc, 0xbc)),
};

ColumnSeries columnSeries2 = new ColumnSeries()
{
    ItemsSource = new ViewModel().SneakersDetail,
    XBindingPath = "Brand",
    YBindingPath = "Position",
    Label = "2014",
    SegmentSpacing = 0.5,
    Interior = new SolidColorBrush(Color.FromRgb(0x4a, 0x4a, 0x4a)),
};

chart.Series.Add(columnSeries1);
chart.Series.Add(columnSeries2);
{% endhighlight %}

{% endtabs %}

![Column Placed One over Another in WPF Chart](Series_images/wpf-chart-column-placed-one-over-another.jpeg)

N> When series are placed one over another (overlapped), you can use the `SegmentSpacing` property to differentiate between them.