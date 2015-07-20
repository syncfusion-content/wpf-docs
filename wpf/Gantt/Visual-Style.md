---
layout: post
title: Visual-Style
description: visual style
platform: wpf
control: Gantt
documentation: ug
---

# Visual Style

Essential Gantt enables you to customize the appearance of the control. This supports the following themes:

* Office2010Blue
* Office2010Black
* Office2010Silver
* Metro

Properties

_Property_

<table>
<tr>
<td>
Property</td><td>
Description</td><td>
Type</td><td>
Data Type</td><td>
Reference links</td></tr>
<tr>
<td>
VisualStyle</td><td>
Gets or set the VisualStyle Property of Gantt control.</td><td>
Dependency Property</td><td>
Enum.VisualStyle.Office2010BlueVisualStyle.Office2010BlackVisualStyle.Office2010SilverVisualStyle.Metro</td><td>
NA</td></tr>
</table>


Adding VisualStyle to Gantt Control 

You can customize the theme using the VisualStyle property.

The following code illustrates how to set the VisualStyle of Gantt control:



[XAML]

&lt;Sync:GanttControl x:Name="Gantt" VisualStyle="Office2010Blue"/&gt;




[C#]

Gantt.VisualStyle = VisualStyle.Office2010Blue;





The following shows Office 2010 Blue:



{ ![](Visual-Style_images/Visual-Style_img1.png) | markdownify }
{:.image }


_Office 2010 Blue_

The following image shows Office 2010 silver:



{ ![](Visual-Style_images/Visual-Style_img2.png) | markdownify }
{:.image }


_Office 2010Silver_

The following image shows Office 2010Silver:



{ ![](Visual-Style_images/Visual-Style_img3.png) | markdownify }
{:.image }


_Office2010Black_

The following image shows Office 2010Metro:



{ ![](Visual-Style_images/Visual-Style_img4.png) | markdownify }
{:.image }


_Metro_

Samples Link

To view samples: 

1. Select Start -> Programs -> Syncfusion -> Essential Studio x.x.xx -> Dashboard.
1. Click Run Samples for WPF under User Interface Edition panel.
2. Select Gantt.
3. Expand the Styles item in the Sample Browser.
4. Choose the Gantt Visual Style sample to launch. 



