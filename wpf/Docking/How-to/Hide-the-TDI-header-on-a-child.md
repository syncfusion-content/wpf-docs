---
layout: post
title: How to hide TDI header on a child in Docking in WPF Data Grid
description: Learn How to hide TDI header on a child in Docking in WPF Data Grid using Syncfusion controls. It supports data operations, UI customization, and enterprise features.
platform: WPF
control: DockingManager
documentation: ug
---

# How to hide TDI header on a child in Docking in WPF Data Grid

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
