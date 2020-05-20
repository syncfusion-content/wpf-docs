---
layout: post
title: Adornments | SfChart | Wpf | Syncfusion
description: This section explains about adornments behavior and its customization properties in WPF Chart (SfChart3D)
platform: wpf
control: SfChart3D
documentation: ug
---

# Adornments in WPF 3D Charts (SfChart3D)

Adornments are used to provide information about the data points to the user. Values from data point(x, y) or other custom properties from a data source can be displayed.You can add a shape and label to adorn each data point.

Each adornment can be represented by the following:

* Marker- Displays the desired symbol at the (X, Y) point.
* Label - Displays the segment label content at the (X, Y) point.
* ConnectorLine - Line used to connect the (X, Y) point and the label element.

    
The following code example illustrates how to initialize the adornment.

{% tabs %}

{% highlight xaml %}

    <chart:StackingBarSeries3D ItemsSource="{Binding CategoricalDatas}" XBindingPath="Year" YBindingPath="Plastic">
                <!--AdornmentsInfo-->
        <chart:StackingBarSeries3D.AdornmentsInfo>
            <chart:ChartAdornmentInfo3D UseSeriesPalette="True" BorderBrush="White" BorderThickness="1" ShowLabel="True" ></chart:ChartAdornmentInfo3D>
        </chart:StackingBarSeries3D.AdornmentsInfo>
    </chart:StackingBarSeries3D>

{% endhighlight %}

{% highlight C# %}

        StackingBarSeries3D series = new StackingBarSeries3D()
            {
                ItemsSource = new ViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic"                
            };

        ChartAdornmentInfo adornmentInfo = new ChartAdornmentInfo() { ShowLabel = true };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Chart 3D support in WPF](Adornments-Images/Chart-3D-Adornment.png)

## Applying Series Brush

[`UseSeriesPalette`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.ChartAdornmentInfoBase~UseSeriesPalette.html#) property is used to set the interior of the series to the adornment background. 

For Accumulation like Pie, Doughnut, Funnel and Pyramid the segment interior color will be reflected in adornment background.

{% tabs %}

{% highlight xaml %}

        <chart:ColumnSeries3D  ItemsSource="{Binding CategoricalData}" XBindingPath="Year"
            YBindingPath="Plastic">                
                    <chart:ColumnSeries3D.AdornmentsInfo>
                        <chart:ChartAdornmentInfo3D ShowLabel="True" LabelPosition="Outer"
                        UseSeriesPalette="True" ></chart:ChartAdornmentInfo3D>
                    </chart:ColumnSeries3D.AdornmentsInfo>
        </chart:ColumnSeries3D>
{% endhighlight %}

{% highlight c# %}

        ColumnSeries3D series = new ColumnSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic",
            };

        ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
            {

                ShowLabel = true,
                LabelPosition = AdornmentsLabelPosition.Outer,
                UseSeriesPalette=true
            };

        series.AdornmentsInfo = adornmentInfo;

        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Series brush for adornments background support in WPF Chart](Adornments-Images/Label_palette.png)

## Smart Labels

When you have more datapoints in Pie or Doughnut series, the adornment labels might get overlap with each other. SfChart provides built-in support to avoid these overlapping by using [`EnableSmartLabels`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CircularSeriesBase~EnableSmartLabels.html#) property.

The following code example demonstrates the EnableSmartLabels property:

{% tabs %}

{% highlight xaml %}

        <chart:PieSeries3D  ItemsSource="{Binding CategoricalData}" ConnectorType="Bezier" XBindingPath="Year"
            YBindingPath="Plastic" EnableSmartLabels="True" LabelPosition="OutsideExtended" ExplodeAll="True" ExplodeRadius="3">
                <chart:PieSeries3D.AdornmentsInfo>
                    <chart:ChartAdornmentInfo3D ShowLabel="True" HorizontalAlignment="Center" VerticalAlignment="Center" ShowConnectorLine="True"></chart:ChartAdornmentInfo3D>
                </chart:PieSeries3D.AdornmentsInfo>
        </chart:PieSeries3D>

{% endhighlight %}

{% highlight c# %}

        PieSeries3D series = new PieSeries3D()
            {
                ItemsSource = new CategoryDataViewModel().CategoricalData,
                XBindingPath = "Year",
                YBindingPath = "Plastic",
                LabelPosition = CircularSeriesLabelPosition.OutsideExtended,
                ConnectorType = ConnectorMode.StraightLine,                
                EnableSmartLabels = true,
                ExplodeAll=true,
                ExplodeRadius=3
            };

        ChartAdornmentInfo3D adornmentInfo = new ChartAdornmentInfo3D()
            {
                ShowLabel = true,
                ShowConnectorLine = true,
                HorizontalAlignment=HorizontalAlignment.Center,
                VerticalAlignment=VerticalAlignment.Center
            };

        series.AdornmentsInfo = adornmentInfo;
        chart.Series.Add(series);

{% endhighlight %}

{% endtabs %}

![Smart Labels in WPF Chart](Adornments-Images/SmartLabels.png)

N> For circular series, the adornment position can be changed to [`Inside`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CircularSeriesLabelPosition.html), [`Outside`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CircularSeriesLabelPosition.html) or [`OutsideExtended`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CircularSeriesLabelPosition.html) using the [`LabelPosition`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.CircularSeriesBase~LabelPosition.html) property.
