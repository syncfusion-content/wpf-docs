---
layout: post
title: Print the SfChart | SfChart | WPF | Syncfusion
description: Learn how to print the Syncfusion Essential Studio WPF Chart (SfChart) control in your applications.
platform: wpf
control: SfChart
documentation: ug
---

# Print the SfChart in WPF

The SfChart control provides a simple way to print the chart using the built-in Print method.

The following code example demonstrates how to print the SfChart:

{% highlight c# %}
// Print the chart
chart.Print();
{% endhighlight %}

This method will send the current state of the chart to the default printer. You can use the standard Windows print dialog to select printer options before printing.