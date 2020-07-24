---
layout: post
title: Grouping Stacked charts | SfChart | Wpf | Syncfusion
description: This section explains Grouping Stacked charts and its properties for customization in WPF Charts (SfChart)
platform: wpf
control: SfChart
documentation: ug
---

# Grouping Stacked Series in WPF Chart (SfChart)

You can group the stacked similar series using [`GroupingLabel`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.StackingSeriesBase~GroupingLabel.html#) property of stacked series. The stacked series which contains the same [`GroupingLabel`](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfChart.WPF~Syncfusion.UI.Xaml.Charts.StackingSeriesBase~GroupingLabel.html#) will be stacked in a single group.

The following code example shows how to group the stacking series.

{% tabs %}

{% highlight xaml %}

        <chart:StackingColumnSeries Interior="#4A4A4A" GroupingLabel="Group1" XBindingPath="Year" 
         YBindingPath="Quarter1" ItemsSource="{Binding AnnualDetails}"/>

        <chart:StackingColumnSeries Interior="#BCBCBC" GroupingLabel="Group1" XBindingPath="Year" 
          YBindingPath="Quarter2" ItemsSource="{Binding AnnualDetails}"/>

        <chart:StackingColumnSeries Interior="#7F7F7F" GroupingLabel="Group2" XBindingPath="Year"
          YBindingPath="Quarter3" ItemsSource="{Binding AnnualDetails}"/>

        <chart:StackingColumnSeries Interior="#343434" GroupingLabel="Group2" XBindingPath="Year"
          YBindingPath="Quarter4" ItemsSource="{Binding AnnualDetails}"/>

{% endhighlight %}

{% highlight c# %}

            SfChart chart = new SfChart();

            StackingColumnSeries series1 = new StackingColumnSeries()
            {
                ItemsSource = new ViewModel().AnnualDetails,
                XBindingPath = "Year",
                YBindingPath = "Quarter1",
                GroupingLabel = "Group1",
                Interior = new SolidColorBrush(Color.FromRgb(0x4A, 0x4A, 0x4A))
            };

            StackingColumnSeries series2 = new StackingColumnSeries()
            {
                ItemsSource = new ViewModel().AnnualDetails,
                XBindingPath = "Year",
                YBindingPath = "Quarter2",
                GroupingLabel = "Group1",
                Interior = new SolidColorBrush(Color.FromRgb(0xBC, 0xBC, 0xBC))
            };

            StackingColumnSeries series3 = new StackingColumnSeries()
            {
                ItemsSource = new ViewModel().AnnualDetails,
                XBindingPath = "Year",
                YBindingPath = "Quarter3",
                GroupingLabel = "Group2",
                Interior = new SolidColorBrush(Color.FromRgb(0x7F, 0x7F, 0x7F))
            };

            StackingColumnSeries series4 = new StackingColumnSeries()
            {
                ItemsSource = new ViewModel().AnnualDetails,
                XBindingPath = "Year",
                YBindingPath = "Quarter4",
                GroupingLabel = "Group2",
                Interior = new SolidColorBrush(Color.FromRgb(0x34, 0x34, 0x34))
            };

            chart.Series.Add(series1);
            chart.Series.Add(series2);
            chart.Series.Add(series3);
            chart.Series.Add(series4);
{% endhighlight %}

{% endtabs %}

![Grouping of stacking series in WPF Chart](Series_images/groupingstacking.png)
