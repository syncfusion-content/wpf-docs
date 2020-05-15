---
layout: post
title: Performance| SfChart | Wpf | Syncfusion
description: How to boost the performance of Essential WPF Chart (SfChart) when there is a need to plot high volume data.
platform: wpf
control: SfChart
documentation: ug
---

# Performance in WPF Charts (SfChart)

* When your underlying data object implements INotifyPropertyChanged, you need to enable the ListenPropertyChange property of the series, to make the chart listen to the property changes of your data object. However enabling this property registers PropertyChanged event of every object in the data source. Due to this, chart’s loading time is affected when there are a large number of points. By default, ListenPropertyChange is set to false in order to avoid the event registration unnecessarily.
* In case of a Line Series, when you have large number of points to plot, you can make use of fast series types like FastLineSeries, FastLineBitmapSeries and FastLineDirectXSeries.
* In case of a Column Series, when you have large number of points to plot, you can make use of FastColumnBitmapSeries.
* You also have Fast Series types for financial charts like HiLo and HiLoOpenClose and they are named as FastHiLoBitmapSeries and FastHiLoOpenCloseBitmapSeries respectively.



