---
layout: post
title: Create a preview of the entire content of the Diagram.
description: How to see the preview of the large Diagrams and to ease navigations within that Diagram?
platform: wpf
control: SfDiagram
documentation: ug
---

Overview Control

Overview control is used to display a preview (overall view) of the entire content of a Diagram. This helps you to look overall picture of large Diagram and also to navigate (pan or zoom) to a particular position of the page.

When you work on a very large Diagram, You may not know the part where you are actually working or navigation from one part to another might be a difficult. To navigation, you can zoom out entire Diagram and find where you are. This solution is not suitable when you need some frequent navigation.

Overview control solved this problem by displaying a preview (overall view) of the entire Diagram. A rectangle indicated viewport of the Diagram. Navigation becomes easy by dragging this rectangle.

N> Supported platform: WPF, WinRT 8.1, Universal, UWP


## Create Overview

The following code example explains how to add Overview to an Application.

{% highlight xml %}

<overview:Overview Source="{Binding ElementName=diagramControl}" Height="300" Margin="0,25,0,0"/>
	
{% endhighlight %}	

![](Overview-Control_images/Overview-Control_img1.jpeg)

Refer to the Overview Sample from the following link.

Sample Link:

Navigation->WPF->Diagram->Overview

## Zoom Pan
In overview, the view port of the Diagram is highlighted with a red colored rectangle. Diagram can be zoomed/panned by interacting with that. You can interact with overview as follows.

| Property | Description | Type | DataType |
|---|---|---|---|
| Constraint | Gets or Sets the OverviewConstraints. | Dependency property | Enum OverviewConstraints  OverviewConstraints.None OverviewConstraints.Pan OverviewConstraints.TapFocus OverviewConstraints.DrawFocus OverviewConstraints.Zoom |
| FocusBrush | Specifies the color of the viewport area in the preview. | Dependency Property | Brush |
| UnFocusBrush | Specifies the background of the extended area in the preview. | Dependency Property | Brush |
