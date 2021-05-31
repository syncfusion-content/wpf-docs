---
layout: post
title: Segment of the WPF Linear ProgressBar control | Syncfusion
description: Learn here about segment support with corner radius in the Syncfusion WPF Linear ProgressBar control and more details.
platform: WPF
control: SfLinearProgressBar
documentation: ug
---
# Segments in Linear ProgressBar
Divides the progressbar into multiple segements using the API.

## Segment
To visualize the progress of multiple sequential tasks, split the progressbar into multiple segments by setting the [SegmentCount](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.ProgressBarBase.html#Syncfusion_UI_Xaml_ProgressBar_ProgressBarBase_SegmentCountProperty).
{% tabs %}
{% highlight XAML %}      
<Syncfusion:SfLinearProgressBar Progress="70"  SegmentCount="4" />     
{% endhighlight %}
{% highlight C# %}
SfLinearProgressBar linear = new SfLinearProgressBar();
 linear.Progress = 70;
linear.SegmentCount = 5;
linear.Width = 500;
linear.Height = 20;
grid.Children.Add(linear);
{% endhighlight %}
{% endtabs %}
![Segment image](Segment_images/Segment.png)

## Segment with corner radius

Corner radius helps to generate rounded edges for the progressbar. This can be achieved through the [IndicatorCornerRadius](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.ProgressBar.ProgressBarBase.html#Syncfusion_UI_Xaml_ProgressBar_ProgressBarBase_IndicatorCornerRadiusProperty) property. 
{% tabs %}
{% highlight XAML %}
 <Syncfusion:SfLinearProgressBar Progress="70"  SegmentCount="4"  IndicatorCornerRadius="10"/>   
{% endhighlight %}
{% highlight C# %}
SfLinearProgressBar linear = new SfLinearProgressBar();
linear.Progress = 70;5
linear.SegmentCount = 5;
linear.IndicatorCornerRadius =10;
linear.Width = 500;
linear.Height = 20;
grid.Children.Add(linear);
{% endhighlight %}
{% endtabs %}
![Segment image](Segment_images/SegmentwithCornerradius.png)