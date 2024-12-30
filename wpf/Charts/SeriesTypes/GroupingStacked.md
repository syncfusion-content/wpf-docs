---
layout: post
title: Grouping Stacked Chart in WPF Charts control | Syncfusion®
description: Learn here all about Grouping Stacked Chart support in Syncfusion® WPF Charts (SfChart) control and more.
platform: wpf
control: SfChart
documentation: ug
---

# Grouping Stacked in WPF Charts (SfChart)

You can group the stacked similar series using [`GroupingLabel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StackingSeriesBase.html#Syncfusion_UI_Xaml_Charts_StackingSeriesBase_GroupingLabel) property of stacked series. The stacked series which contains the same [`GroupingLabel`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.StackingSeriesBase.html#Syncfusion_UI_Xaml_Charts_StackingSeriesBase_GroupingLabel) will be stacked in a single group.

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

![WPF Grouping Stacked Chart](Series_images/wpf-grouping-stacked-chart.png)

## See also

[`How to render the stacked step line series in WPF Chart`](https://www.syncfusion.com/kb/10155/how-to-render-the-stacked-step-line-series-in-wpf-chart)

[`How to create separate columns StackedGroup in stacking series`](https://www.syncfusion.com/kb/4730/how-to-create-separate-columns-stackedgroup-in-stacking-series)
