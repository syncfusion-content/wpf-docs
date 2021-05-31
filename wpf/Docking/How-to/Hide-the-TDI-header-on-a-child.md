---
layout: post
title: Hide the TDI header on a child | DockingManager | wpf | Syncfusion
description: hide the tdi header on a child
platform: wpf
control: DockingManager
 documentation: ug
---

# Hide the TDI header on a child

This property is used to hide the header of a TDI document when the DocumentTabControl has a TDI child.

{% highlight xaml %}

<syncfusion:DockingManager Name="DockingManager"HideTDIHeaderOnSingleChild="True" UseDocumentContainer="True">

	<Grid Name="grid1" syncfusion:DockingManager.State="Document">   

		<TextBlock Text="Tab Content"/>

	</Grid>

</syncfusion:DockingManager>

{% endhighlight  %}

{% highlight c# %}

DockingManager.HideTDIHeaderOnSingleChild = true;

{% endhighlight  %}

![](Hide-the-TDI-header-on-a-child_images/Hide-the-TDI-header-on-a-child_img1.jpeg)
