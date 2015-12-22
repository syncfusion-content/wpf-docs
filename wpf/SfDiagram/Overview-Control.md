---
layout: post
title: Overview Control | SfDiagram | wpf | Syncfusion
description: overview control
platform: wpf
control: SfDiagram
documentation: ug
---

# Overview Control

Overview control is used to display a preview (overall view) of the entire content of a Diagram. This helps you to look overall picture of large Diagram and also to navigate (pan or zoom) to a particular position of the page.

When you work on a very large Diagram, You may not know the part where you are actually working or navigation from one part to another might be a difficult. To navigation, you can zoom out entire Diagram and find where you are. This solution is not suitable when you need some frequent navigation.

Overview control solved this problem by displaying a preview (overall view) of the entire Diagram. A rectangle indicated viewport of the Diagram. Navigation becomes easy by dragging this rectangle.

Note : 

Supported platform: WPF, WinRT 8.1, Universal, UWP

Use Case Scenarios

You can view the entire content of a Diagram in a preview window. This helps you to navigate to a particular position of the page.

<table>
<tr>
<td>
<b>Property</b></td><td>
<b>Description</b></td><td>
<b>Type</b></td><td>
<b>Data Type</b></td></tr>
<tr>
<td>
Constraint</td><td>
Gets or Sets the OverviewConstraints type.</td><td>
Dependency property</td><td>
enumOverviewConstraints.NoneOverviewConstraints.PanOverviewConstraints.TapFocusOverviewConstraints.DrawFocusOverviewConstraints.Zoom</td></tr>
<tr>
<td>
FocusBrush</td><td>
Specifies the color of the viewport area in the preview.</td><td>
Dependency Property</td><td>
Brush</td></tr>
<tr>
<td>
UnFocusBrush</td><td>
Specifies the background of the extended area in the preview.</td><td>
Dependency Property</td><td>
Brush</td></tr>
</table>


Adding Overview control to an Application

The following code example explains how to add Overview to an Application

![](Overview-Control_images\Overview-Control_img1.png)

Refer to the Overview Sample from the following link.

Sample Link:

Navigation->WinRT->Diagram->Overview

