---
layout: post
title: Adornments| SfChart | Wpf | Syncfusion
description: Learn how to add markers, data point labels, connector lines, event, formatting label content and configure the custom templates to the SfChart Adornments.
platform: wpf
control: SfChart
documentation: ug
---

# Data Markers in WPF Charts (SfChart)

Chart adornments (Data Markers) are used to display values related to a chart segment element. Values from data point(x, y) or other custom properties from a data source can be displayed. 

Each adornment can be represented by the following:

* Label - Displays the segment label content at the (X, Y) point.
* Marker- Displays the desired symbol at the (X, Y) point.
* ConnectorLine - Line used to connect the (X, Y) point and the label element.

The following code example illustrates how to initialize the adornment.

{% tabs %}

{% highlight xaml %}

        <syncfusion:ColumnSeries Interior="#777777" ItemsSource="{Binding Demands}" XBindingPath="Category" YBindingPath="Value">
                <syncfusion:ColumnSeries.AdornmentsInfo>
                    <syncfusion:ChartAdornmentInfo></syncfusion:ChartAdornmentInfo>
                </syncfusion:ColumnSeries.AdornmentsInfo>
        </syncfusion:ColumnSeries> 

{% endhighlight %}

{% highlight c# %}

        ColumnSeries series = new ColumnSeries()
            {
                ItemsSource = ViewModel().Demands,
                XBindingPath = "Demands",
                YBindingPath = "Value",
                Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))
            };
        ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo();
        series.AdornmentsInfo = adornmentInfo;
        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Data Markers in Adornment](Adornments_images/Label_Overview.PNG) 

