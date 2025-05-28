---
layout: post
title: Performance in WPF Charts control | Syncfusion
description: Learn here all about Performance support in Syncfusion® WPF Charts (SfChart) control, its elements and more details.
platform: wpf
control: SfChart
documentation: ug
---

# Performance in WPF Charts (SfChart)

## Performance Optimization Tips

* When your underlying data object implements INotifyPropertyChanged, you need to enable the ListenPropertyChange property of the series to make the chart listen to the property changes of your data object. However, enabling this property registers the PropertyChanged event for every object in the data source. This can affect the chart's loading time when there are a large number of data points. By default, ListenPropertyChange is set to false to avoid unnecessary event registration.

* For Line Series with a large number of data points, use fast series types like FastLineSeries and FastLineBitmapSeries for better performance.

* For Column Series with a large number of data points, use FastColumnBitmapSeries for improved rendering speed.

* For financial charts like HiLo and HiLoOpenClose with large datasets, use FastHiLoBitmapSeries and FastHiLoOpenCloseBitmapSeries respectively.

N> Support for DirectX series has been discontinued. Instead, use FastLineBitmapSeries to render a large amount of data with optimal performance.

## Deferred Real-Time Updates

You can hold and resume the series updates in dynamic update scenarios using the following methods:

[`SuspendSeriesNotification`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_SuspendSeriesNotification)

[`ResumeSeriesNotification`](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_ResumeSeriesNotification)

N> You can refer to our [WPF Charts](https://www.syncfusion.com/wpf-controls/charts) feature tour page for its groundbreaking feature representations. You can also explore our [WPF Charts example](https://github.com/syncfusion/wpf-demos) to know various chart types and how to easily configure them with built-in support for creating stunning visual effects.

## See also

[`How to create a real time Chart using MVVM in WPF`](https://support.syncfusion.com/kb/article/10039/how-to-create-a-real-time-chart-sfchart-using-mvvm-in-wpf)