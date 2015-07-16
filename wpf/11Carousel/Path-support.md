---
layout: post
title: Path-support
description: path support
platform: wpf
control: Carousel
documentation: ug
---

# Path support

Carousel panel arrange its children on a path. You can specify any path and it can be created easily using expression blend. You can arrange the items in any path.

Adding Path support to an Application 

You can set custom path using Path property of Carousel control as shown in the below example.



[XAML]



&lt;syncfusion:Carousel x:Name="carousel" Height="400" Width="450"&gt;
    &lt;syncfusion:Carousel.Path&gt;
        &lt;Path Data="M0,300 L600,300" Stroke="Blue" StrokeThickness="2" HorizontalAlignment="Stretch" VerticalAlignment="Stretch"/&gt;
    &lt;/syncfusion:Carousel.Path&gt;
&lt;/syncfusion:Carousel&gt;





{ ![](Path-support_images/Path-support_img1.png) | markdownify }
{:.image }




Properties



_CustomEditor Table_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Type </td><td>
Data Type </td><td>
Reference links </td></tr>
<tr>
<td>
Path</td><td>
Sets the CustomPath for the Carousel control.</td><td>
DependencyProperty</td><td>
CustomEditorCollection</td><td>
</td></tr>
</table>


