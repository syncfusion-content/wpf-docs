---
layout: post
title: Zooming in WPF GridControl | Syncfusion
description: Learn about Zooming support in Syncfusion Essential Studio WPF GridControl, its elements and more details.
platform: wpf
control: GridControl
documentation: ug
---

# Zooming in WPF GridControl

This feature enables the user to change the zoom level of the Grid control that brings either more or fewer cells into the view. By zooming in you can get a magnified view of the grid cells, and by zooming out you can bring more cells in to the view. This does not change the underlying size of Grid control, and the printout of the Grid control remains constant, regardless of the selected zoom scale.

## Use Case Scenarios

When a larger number of cells are updated in the Grid, the user can view the grid cells clearly by increasing the zoom scale. By decreasing the zoom scale, the user can display more cells in the view.

### Properties



<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th></tr>
<tr>
<td>
ZoomScale</td><td>
Used to change the zoom level of the Grid control</td><td>
Dependency Property </td><td>
Double</td></tr>
</table>


N> Download demo application from [GitHub](https://github.com/syncfusion/wpf-demos/tree/master/gridcontrol/Zooming)

## Change Zoom Scale of the Grid Control

You can change the zoom level of the Grid control by using the ZoomScale property defined in the Grid control.

The following code illustrates how to change the ZoomScale__of the Grid control:

{% tabs %}
{% highlight c# %}
gridControl.ZoomScale = 1.5;
{% endhighlight  %}
{% endtabs %}

![Increased Zoom Scale in WPF GridControl](Zoom-In-and-Zoom-Out_images/Zoom-In-and-Zoom-Out_img1.png)


![Decreased Zoom Scale in WPF GridControl](Zoom-In-and-Zoom-Out_images/Zoom-In-and-Zoom-Out_img2.png)

