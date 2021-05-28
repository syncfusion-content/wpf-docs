---
layout: post
title: Add range of points dynamically| SfChart | Wpf | Syncfusion
description: Add range of points dynamically in Syncfusion Essential Studio WPF Chart (SfChart) control, its elements and more.
platform: wpf
control: SfChart
documentation: ug
---

## Add range of points dynamically

Whenever you add a data point to ItemsSource dynamically, corresponding data will be updated inside chart series synchronously. This operation will be happening for each and every data point that we add subsequently. You can avoid this by calling SuspendSeriesNotification method of Chart before adding range of data points and then call ResumeSeriesNotification to update all the data points that have been added between these two method calls.

{% highlight c# %}

Chart.SuspendSeriesNotification();

// ...

// Add multiple data points.

// ...

Chart.ResumeSeriesNotification();



{% endhighlight  %}