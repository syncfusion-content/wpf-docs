---
layout: post
title: Path support | Carousel | wpf | Syncfusion
description: path support
platform: wpf
control: Carousel
documentation: ug
---

# Path support

Carousel panel arrange its children on a path. You can specify any path and it can be created easily using expression blend. You can arrange the items in any path.

## Adding Path support to an Application 

You can set custom path using Path property of Carousel control as shown in the below example.



{% highlight xaml %}



<syncfusion:Carousel x:Name="carousel" Height="400" Width="450">
    <syncfusion:Carousel.Path>
        <Path Data="M0,300 L600,300" Stroke="Blue" StrokeThickness="2" HorizontalAlignment="Stretch" VerticalAlignment="Stretch"/>
    </syncfusion:Carousel.Path>
</syncfusion:Carousel>

{% endhighlight %}



![](Path-support_images/Path-support_img1.png)





## Properties




<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th><th>
Reference links </th></tr>
<tr>
<td>
Path</td><td>
Sets the CustomPath for the Carousel control.</td><td>
DependencyProperty</td><td>
CustomEditorCollection</td><td>
</td></tr>
</table>


