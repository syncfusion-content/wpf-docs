---
layout: post
title: Add Range of Points Dynamically | SfChart | WPF | Syncfusion
description: Learn how to add a range of points dynamically in Syncfusion® WPF Chart (SfChart) control, its elements and more.
platform: wpf
control: SfChart
documentation: ug
---

# Add Range of Points Dynamically

When you add data points to the ItemsSource dynamically, the chart series updates synchronously for each individual point added. This can impact performance when adding multiple points in succession. To optimize this process, you can use the `SuspendSeriesNotification` and `ResumeSeriesNotification` methods of the Chart control and update the chart only after all points have been added:

{% highlight c# %}

// Suspend notifications before adding multiple points.
Chart.SuspendSeriesNotification();

//. . .
// Add multiple data points here.
//. . .

// Resume notifications to update the chart with all added points.
Chart.ResumeSeriesNotification();

{% endhighlight %}

By using this pattern, you can significantly improve performance when adding large datasets to your chart.