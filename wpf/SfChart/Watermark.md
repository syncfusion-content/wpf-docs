---
layout: post
title: Watermark
description: watermark
platform: wpf
control: SfChart
documentation: ug
---

# Watermark

SfChart provides Watermark support, used to add text or images to the chart area. The major application of Watermark is to define the copyright information of the user it belongs to. 

This section is to help you understand how to use the Watermark feature in your chart.

## Add Text as Watermark

You can add the text to chart background using this feature. This can be done by creating the instance for the Watermark and you must set the required text for the Content property of that instance. 

The following APIs are used to add Watermark to chart.



<table>
<tr>
<th>
Property</th><th>
Definition</th></tr>
<tr>
<td>
HorizontalAlignment</td><td>
Gets or sets the HorizontalAlignment value that represents the horizontal alignment for the Watermark.</td></tr>
<tr>
<td>
VerticalAlignment</td><td>
Gets or sets the VerticalAlignment value that represents the vertical alignment for the Watermark.</td></tr>
<tr>
<td>
Content</td><td>
Gets or sets the object value that represents the content for the Watermark</td></tr>
</table>


The following code example explains how to set your custom text as Watermark.

{% highlight xml %}


<syncfusion:SfChart.Watermark>



<syncfusion:Watermark Canvas.ZIndex="-1"  HorizontalAlignment="Center" VerticalAlignment="Center">



<syncfusion:Watermark.Content>

<TextBlock Text="Demand Report" FontSize="60" Foreground="Gray" Opacity="0.5"></TextBlock>

</syncfusion:Watermark.Content>



</syncfusion:Watermark>

</syncfusion:SfChart.Watermark>

{% endhighlight %}

The following screenshot illustrates the Watermark with custom text.

![C:/Users/rachel/Desktop/snaps/21.png](Watermark_images/Watermark_img1.png)



## Add Image as Watermark

You can set images as Watermark for SfChart, using the Content property, since it can hold any kind of object. The following code example illustrates image Watermark.

{% highlight xml %}



<syncfusion:SfChart.Watermark>

<syncfusion:Watermark   HorizontalAlignment="Right" VerticalAlignment="Top">

<syncfusion:Watermark.Content>

<Image Source="ms-appx:///Assets/syncfusion.png" Height="50" Width="50"/>

</syncfusion:Watermark.Content>

</syncfusion:Watermark>

</syncfusion:SfChart.Watermark>

The following screenshot illustrates the image Watermark, center aligned.
{% endhighlight %}

![C:/Users/rachel/Desktop/snaps/22.png](Watermark_images/Watermark_img2.png)



