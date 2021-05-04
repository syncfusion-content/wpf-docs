---
layout: post
title: Data Markers in WPF Charts control | Syncfusion
description: Learn here all about Data Markers support in Syncfusion WPF Charts (SfChart) control, its elements and more details.
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

## See also

[`How to show different data marker based on the value in the WPF Chart`](https://www.syncfusion.com/kb/11001/how-to-show-different-data-marker-based-on-the-value-in-the-wpf-chart)

[`How to show custom data marker in the WPF Chart`](https://www.syncfusion.com/kb/11000/how-to-show-custom-data-marker-in-the-wpf-chart)

[`How to rotate text in adornment`](https://www.syncfusion.com/kb/2908/how-to-rotate-text-in-adornment)

[`How to display the labels inside segments`](https://www.syncfusion.com/kb/2580/how-to-display-the-labels-inside-segments)

[`How to bind the underlying DataTable model to the DataMarker Template in WPF Charts`](https://www.syncfusion.com/kb/11603/how-to-bind-the-underlying-datatable-model-to-the-datamarker-template-in-wpf-charts)


