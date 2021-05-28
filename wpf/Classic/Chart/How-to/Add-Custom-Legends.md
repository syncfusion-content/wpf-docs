---
layout: post
title: Add Custom Legends | wpf | Syncfusion
description: Learn here all about Add-Custom-Legends support in Syncfusion WPF Chart (Classic) control, its elements and more details.
platform: wpf
control: Chart (Classic)
 documentation: ug
---

## Add Custom Legends

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

![Add-Custom-Legends_img1](Add-Custom-Legends_images/Add-Custom-Legends_img1.jpeg)
