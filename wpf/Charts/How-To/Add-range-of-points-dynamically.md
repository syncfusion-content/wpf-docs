---
layout: post
title: How to add range of points dynamically in WPF Chart | Syncfusion®
description: Add range of points dynamically in WPF Chart control, its elements and more.
platform: wpf
control: SfChart
documentation: ug
---

# How to add range of points dynamically in WPF Chart

Whenever you add a data point to ItemsSource dynamically, corresponding data will be updated inside chart series synchronously. This operation will be happening for each and every data point that we add subsequently. You can avoid this by calling SuspendSeriesNotification method of Chart before adding range of data points and then call ResumeSeriesNotification to update all the data points that have been added between these two method calls.

{% highlight c# %}

Chart.SuspendSeriesNotification();

// ...

// Add multiple data points.

// ...

Chart.ResumeSeriesNotification();



{% endhighlight  %}