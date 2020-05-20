---
layout: post
title: Adornments| SfChart | Wpf | Syncfusion
description: Learn how to add markers, data point labels, connector lines, event, formatting label content and configure the custom templates to the SfChart Adornments.
platform: wpf
control: SfChart
documentation: ug
---

# Adornments in WPF Charts (SfChart)

Chart adornments are used to display values related to a chart segment element. Values from data point(x, y) or other custom properties from a data source can be displayed. 

Each adornment can be represented by the following:

* Label - Displays the segment label content at the (X, Y) point.
* Marker- Displays the desired symbol at the (X, Y) point.
* ConnectorLine - Line used to connect the (X, Y) point and the label element.

## Smart Labels

When you have more datapoints in Pie or Doughnut series, the adornment labels might get overlap with each other. SfChart provides built-in support to avoid these overlapping by using [`EnableSmartLabels`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CircularSeriesBase~EnableSmartLabels.html#) property.

The following code example demonstrates the EnableSmartLabels property:

{% tabs %}

{% highlight xaml %}

            <chart:PieSeries Interior="#777777" ItemsSource="{Binding CategoricalData}" ConnectorType="Bezier" XBindingPath="Year"
            YBindingPath="Plastic" EnableSmartLabels="True" LabelPosition="OutsideExtended" ExplodeAll="True" ExplodeRadius="3">
                <chart:PieSeries.AdornmentsInfo>
                    <chart:ChartAdornmentInfo ShowLabel="True" HorizontalAlignment="Center" VerticalAlignment="Center" ShowConnectorLine="True"></chart:ChartAdornmentInfo>
                </chart:PieSeries.AdornmentsInfo>
            </chart:PieSeries>

{% endhighlight %}

{% highlight c# %}

            PieSeries series = new PieSeries()
            {
                ItemsSource = new ViewModel().Tax,
                XBindingPath = "Year",
                YBindingPath = "Plastic",
                EnableSmartLabels = true,
                ExplodeAll = true,
                ExplodeRadius = 3,
                Palette = ChartColorPalette.Custom,
                LabelPosition=CircularSeriesLabelPosition.OutsideExtended,
                Interior = new SolidColorBrush(Color.FromRgb(0x77, 0x77, 0x77))
            };

            ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
            {
                ShowLabel = true,
                ShowConnectorLine = true,
                UseSeriesPalette = true,
                HorizontalAlignment = HorizontalAlignment.Center,
                VerticalAlignment = VerticalAlignment.Center
            };
            series.AdornmentsInfo = adornmentInfo;

{% endhighlight %}

{% endtabs %}

![Smart labels for adornments in WPF Chart](/Adornments_images/smartlabel.png)

N> For circular series, the adornment position can be changed to [`Inside`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CircularSeriesLabelPosition.html), [`Outside`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CircularSeriesLabelPosition.html) or [`OutsideExtended`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CircularSeriesLabelPosition.html) using the [`LabelPosition`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CircularSeriesBase~LabelPosition.html) property.

## Applying Series Brush

[`UseSeriesPalette`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~UseSeriesPalette.html#) property is used to set the interior of the series to the adornment background. 

>N For Accumulation like Pie, Doughnut, Funnel and Pyramid the segment interior color will be reflected in adornment background.

{% tabs %}

{% highlight xaml %}

        <syncfusion:ChartAdornmentInfo ShowLabel="True" UseSeriesPalette="True">

        </syncfusion:ChartAdornmentInfo>

{% endhighlight %}

{% highlight c# %}

        ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo()
        {
            ShowLabel = true,
            UseSeriesPalette = true
        };

{% endhighlight %}

{% endtabs %}



