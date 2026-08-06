---
layout: post
title: Highlight Segment in WPF Sparkline | Syncfusion®
description: Highlight segment in the WPF Sparkline emphasizes specific data points or ranges with distinct styling for improved data visibility.
platform: wpf
control: SfSparkline
documentation: ug
---

# Highlight Segment in WPF Sparkline 

This feature enables highlighting the column segments on mouse move. It is applicable for column and WinLoss sparklines.

{% tabs %}

{% highlight xaml %}

<Syncfusion:SfColumnSparkline
    HighlightSegment="True"
    ItemsSource="{Binding UsersList}"
    YBindingPath="NoOfUsers">
</Syncfusion:SfColumnSparkline>
		
{% endhighlight %}  

{% highlight c# %}

SfColumnSparkline sparkline = new SfColumnSparkline()
{
    ItemsSource = new UsersViewModel().UsersList,
    YBindingPath = "NoOfUsers",
    HighlightSegment = true
};

{% endhighlight %}

{% endtabs %}

The following is a snapshot of the highlight segment.

![Highlight-Segment_img1](Highlight-Segment_images/Highlight-Segment_img1.png)
