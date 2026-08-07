---
layout: post
title: How to hide TDI header on a child in WPF Docking | Syncfusion®
description: Learn here how to hide the tdi header on a child in Syncfusion® WPF Docking (DockingManager) control, its elements and more.
platform: WPF
control: DockingManager
documentation: ug
---

# How to hide TDI header on a child in WPF Docking

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

![Hide-the-TDI-header-on-a-child_images1](Hide-the-TDI-header-on-a-child_images/Hide-the-TDI-header-on-a-child_img1.jpeg)
