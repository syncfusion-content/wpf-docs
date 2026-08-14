---
layout: post
title: Segment Customization in WPF Sparkline | Syncfusion®
description: Segment customization in the WPF Sparkline to apply different colors to data segments and improve visual distinction of trends.
platform: wpf
control: SfSparkline
documentation: ug
---

# Segment Customization in WPF Sparkline

You can customize the first, last, negative, high, and low point brushes, similar to markers, in area and line sparklines.

{% tabs %}

{% highlight xaml %}

 <Syncfusion:SfColumnSparkline
     ItemsSource="{Binding UsersList}"
     YBindingPath="NoOfUsers">
     
     <Syncfusion:SfColumnSparkline.SegmentTemplateSelector>
         <Syncfusion:SegmentTemplateSelector
             FirstPointBrush="Yellow"
             LastPointBrush="Yellow"
             HighPointBrush="Red"/>
     </Syncfusion:SfColumnSparkline.SegmentTemplateSelector>

 </Syncfusion:SfColumnSparkline>
		
{% endhighlight  %}

{% highlight c# %}

SfColumnSparkline sparkline = new SfColumnSparkline()
{
    ItemsSource = new UsersViewModel().UsersList,
    YBindingPath = "NoOfUsers"
};

SegmentTemplateSelector selector = new SegmentTemplateSelector()
{
    FirstPointBrush = new SolidColorBrush(Colors.Yellow),
    LastPointBrush = new SolidColorBrush(Colors.Yellow),
    HighPointBrush = new SolidColorBrush(Colors.Red)
};

sparkline.SegmentTemplateSelector = selector;

{% endhighlight %}

{% endtabs %}

The following is a snapshot of the customized segment.

![Customize-segment-brush_img1](Customize-segment-brush_images/Customize-segment-brush_img1.png)
