---
layout: post
title: Change the position of the Chart Legend | wpf | Syncfusion
description: Learn here all about Change the position of the Chart Legend support in Syncfusion WPF Chart (Classic) control and more.
platform: wpf
control: Chart (Classic)
documentation: ug
---

## Change the position of the Chart Legend

Chart Legend can be docked by using the Dock property of DockPanel class. The Legend can be docked to the top, left, bottom or right of either the Chart or Chart Area; also it can be placed anywhere inside or outside the Chart Area (floating).

<table>
<tr>
<th>
Property</th><th>
Description</th></tr>
<tr>
<td>
ChartDockPanel.Dock</td><td>
Docks the Chart Legend in the Chart or Chart Area. The values provided are as follows:Top: Docks the Chart Legend to the top.Bottom: Docks the Chart Legend to the bottom.Right: Docks the Chart Legend to the right.Left: Docks the Chart Legend to the left.Floating: Chart Legend can be dragged anywhere inside or outside the Chart Area.</td></tr>
</table>
The following code example illustrates how to dock the Chart Legend in the Chart Area.

{% tabs %}

{% highlight xaml %}

<chart:Chart.Legends>

<chart:ChartLegend chart:Chart.Dock="Left">

</chart:ChartLegend>

</chart:Chart.Legends>



<syncfusion:ChartArea.Legend>

<syncfusion:ChartLegend Name="Legend1" syncfusion:ChartDockPanel.Dock="Left"/>

</syncfusion:ChartArea.Legend>
{% endhighlight  %}

{% highlight c# %}

ChartDockPanel.SetDock(Legend1, ChartDock.Left);
{% endhighlight  %}
{% endtabs %}

![Change-the-position-of-the-Chart-Legend_img1](Change-the-position-of-the-Chart-Legend_images/Change-the-position-of-the-Chart-Legend_img1.png)

![Change-the-position-of-the-Chart-Legend_img2](Change-the-position-of-the-Chart-Legend_images/Change-the-position-of-the-Chart-Legend_img2.png)





