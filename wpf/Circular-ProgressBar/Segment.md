---
layout: post
title: Segments in WPF SfCircularProgressBar | Syncfusion®
description: Learn how segments customization in WPF SfCircularProgressBar helps visualize progress using multiple segments, spacing, and styling options.
platform: wpf
control: SfCircularProgressBar
documentation: ug
---
# Segments in WPF SfCircularProgressBar
Segmentation helps to divide the progressbar into multiple potions. To visualize the progress of multiple sequential tasks, split the progressbar into multiple segments by setting the [SegmentCount](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.ProgressBarBase.html#Syncfusion_UI_Xaml_ProgressBar_ProgressBarBase_SegmentCountProperty) property.

{% tabs %}
{% highlight XAML %}      
<Syncfusion:SfCircularProgressBar Progress="70"  SegmentCount="4" />     
{% endhighlight %}
{% highlight C# %}
SfCircularProgressBar Circular = new SfCircularProgressBar();
 Circular.Progress = 70;
Circular.SegmentCount = 4;
grid.Children.Add(Circular);
{% endhighlight %}
{% endtabs %}
![Segment image](Segment_images/Segment.png)
