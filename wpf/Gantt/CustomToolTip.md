---
layout: post
title: CustomToolTip| Gantt | Wpf | Syncfusion
description: customtooltip
platform: wpf
control: Gantt
documentation: ug
---

# CustomToolTip

Essential Gantt provides tooltip support for the TaskBar. Tooltip is a small pop-up box, which is usually displayed on mouse hover. This is used to display additional information about the elements without increasing the window size. Essential Gantt provides support to add customizable tooltip. You can add text or image to your tooltip as needed. 

## Properties


<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th></tr>
<tr>
<td>
ToolTipTemplate</td><td>
Gets or set the TaskBarCollection Property of GanttControl</td><td>
Dependency Property</td><td>
DataTemplate</td></tr>
</table>


## Adding CustomToolTip to Gantt 

The following code illustrates how to add a custom tooltip to the Gantt control.

{% highlight xaml %}



<Sync:GanttControl x:Name="Gantt" ToolTipTemplate="{StaticResource ToolTipTemp}"/>


{% endhighlight  %}


The following image shows Custom ToolTip:



![](CustomToolTip_images/CustomToolTip_img1.png)



Custom ToolTip Demo
{:.caption}

## Samples Link

To view samples: 

1. Go to the Syncfusion Essential Studio installed location. 
    Location: Installed Location\Syncfusion\Essential Studio\{{ site.releaseversion }}\Infrastructure\Launcher\Syncfusion Control Panel 
2. Open the Syncfusion Control Panel in the above location (or) Double click on the Syncfusion Control Panel desktop shortcut menu.
2. Click Run Samples for WPF under User Interface Edition panel .
3. Select Gantt.
4. Expand the Interactive Features item in the Sample Browser.
5. Choose the CustomToolTip samples to launch.



