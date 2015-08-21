---
layout: post
title: Customize-segment-brush
description: customize segment brush
platform: wpf
control: Sparkline
documentation: ug
---

# Customize segment brush

We can able to customize the first, last, negative, high and low point brushes as like markers in area and line sparkline.
{% highlight html %}

<Syncfusion:SfColumnSparkline ItemsSource="{Binding UsersList}" YBindingPath="NoOfUsers" >

            <Syncfusion:SfColumnSparkline.SegmentTemplateSelector>

                <Syncfusion:SegmentTemplateSelector FirstPointBrush="Yellow" LastPointBrush="Yellow" HighPointBrush="Red"/>

            </Syncfusion:SfColumnSparkline.SegmentTemplateSelector>

        </Syncfusion:SfColumnSparkline>
{% endhighlight  %}

Following is the snapshot for customize segment,

![C:/Users/ApoorvahR/Desktop/10.png](Customize-segment-brush_images/Customize-segment-brush_img1.png)



