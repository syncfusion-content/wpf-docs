---
layout: post
title: Segment support in the WPF Circular ProgressBar control | Syncfusion
description: Learn here about segment support in the Syncfusion WPF Circular ProgressBar control and more details.
platform: WPF
control: SfCircularProgressBar
documentation: ug
---
# Segments in Circular ProgressBar
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