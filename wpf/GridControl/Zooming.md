---
layout: post
title: Zooming in WPF Excel-like Grid | Syncfusion®
description: Adjust the zoom level in Excel-like Grid to magnify content, view more cells, and improve readability without affecting the grid's actual size.
platform: wpf
control: Excel-like Grid
documentation: ug
---

# Zooming in WPF Excel-like Grid

This feature enables the user to change the zoom level of the Excel-like Grid that brings either more or fewer cells into the view. By zooming in you can get a magnified view of the grid cells, and by zooming out you can bring more cells in to the view. This does not change the underlying size of Excel-like Grid, and the printout of the Excel-like Grid remains constant, regardless of the selected zoom scale.

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
Used to change the zoom level of the Excel-like Grid</td><td>
Dependency Property </td><td>
Double</td></tr>
</table>


N> Download demo application from [GitHub](https://github.com/syncfusion/wpf-demos/tree/master/gridcontrol/Zooming)

## Change Zoom Scale of the Excel-like Grid

You can change the zoom level of the Excel-like Grid by using the ZoomScale property defined in the Excel-like Grid.

The following code illustrates how to change the ZoomScale__of the Excel-like Grid:

{% tabs %}
{% highlight c# %}
gridControl.ZoomScale = 1.5;
{% endhighlight  %}
{% endtabs %}

![Increased Zoom Scale](Zoom-In-and-Zoom-Out_images/Zoom-In-and-Zoom-Out_img1.png)


![Decreased Zoom Scale](Zoom-In-and-Zoom-Out_images/Zoom-In-and-Zoom-Out_img2.png)

