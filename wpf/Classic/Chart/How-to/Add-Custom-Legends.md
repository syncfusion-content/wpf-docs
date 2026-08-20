---
layout: post
title: How to add custom legends in WPF Classic Chart | Syncfusion®
description: Add custom legends in Syncfusion® WPF Classic Chart to display tailored legend items, customize legend content, and improve chart readability.
platform: wpf
control: Chart (Classic)
documentation: ug
---

# How to add custom legends in WPF Classic Chart

It's easy to replace existing, default, legend items with custom items in Chart or Chart Area legends.

Remember to clear the existing default entries, before adding new custom items. Otherwise, this results in exceptions. The following lines of code can be used to add items to chart legend.
{% highlight c# %}

ChartLegend legend = new ChartLegend();

legend.Items.Clear();

legend.Items.Add("Legend 1");

legend.Items.Add("Legend 2");

legend.Items.Add("Legend 3");

Chart1.Legends.Add(legend);

{% endhighlight %}

![Add-Custom-Legends](add-custom-legends_images/wpf-chart-add-custom-legends.jpeg)
