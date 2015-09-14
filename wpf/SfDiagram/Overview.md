---
layout: post
title: Overview
description: overview
platform: wpf
control: Control Name undefined
documentation: ug
---

### Overview

Overview control is used to display a preview (overall view) of the entire content of a Diagram. This helps you to look overall picture of large Diagram and also to navigate (pan or zoom) to a particular position of the page.

When you work on a very large Diagram, you may not know the part where you are actually working or navigation from one part to another might be difficult. To navigation, you can zoom out entire Diagram and find where you are. This solution is not suitable when you need some frequent navigation.

Overview control solves this problem by displaying a preview (overall view) of the entire Diagram. A rectangle indicates viewport of the Diagram. Navigation becomes easy by dragging this rectangle.

Supported platform: WinRT 8.1, Universal

Use Case Scenarios

You can view the entire content of a Diagram in a preview window. This helps you to navigate to a particular position of the page.

<table>
<tr>
<td>
Property</td><td>
Description</td><td>
Type</td><td>
Data Type</td></tr>
<tr>
<td>
Constraint</td><td>
Gets or sets the OverviewConstraints type.</td><td>
Dependency Property</td><td>
enum<br>OverviewContraints.None<br>OverviewContraints.Pan<br>OverviewContraints.TapFocus<br>OverviewContraints.DrawFocus<br>OverviewContraints.Zoom</td></tr>
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


 Adding Overview Control to an Application 

The following code example explains how to add Overview to an Application



[XAMl]

&lt;!--Overview--&gt;

&lt;overview:Overview Source="{Binding ElementName=diagramControl}"   Height="300" Margin="0,25,0,0"&gt;&lt;/overview:Overview&gt;

![D:/OverView.png](Overview_images/Overview_img1.png)
{:.image }




Refer to the Overview Sample from the following link.

Sample Link:

Navigation->WPF->Diagram->Overview

