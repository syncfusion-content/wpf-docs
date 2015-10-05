---
layout: post
title: Customize segment brush | SfSparkline | wpf | Syncfusion
description: customize segment brush
platform: wpf
control: SfSparkline
documentation: ug
---

# Customize segment brush

We can able to customize the first, last, negative, high and low point brushes as like markers in area and line sparkline.

{% highlight xaml %}

<Syncfusion:SfColumnSparkline ItemsSource="{Binding UsersList}" YBindingPath="NoOfUsers" >

            <Syncfusion:SfColumnSparkline.SegmentTemplateSelector>

                <Syncfusion:SegmentTemplateSelector FirstPointBrush="Yellow" LastPointBrush="Yellow" HighPointBrush="Red"/>

            </Syncfusion:SfColumnSparkline.SegmentTemplateSelector>

        </Syncfusion:SfColumnSparkline>
		
{% endhighlight  %}

Following is the snapshot for customize segment,

![](Customize-segment-brush_images/Customize-segment-brush_img1.png)