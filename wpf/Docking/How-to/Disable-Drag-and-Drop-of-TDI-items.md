---
layout: post
title: How to disable TDI items drag and drop in Docking in WPF Data Grid
description: Learn How to disable TDI items drag and drop in Docking in WPF Data Grid using Syncfusion controls. It supports data operations, UI customization, and enterprise features.
platform: WPF
control: DockingManager
documentation: ug
---

# How to disable TDI items drag and drop in Docking in WPF Data Grid

IsTDIDragDropEnabled property is used to disable the drag and drop of TDI items in DockingManager. The usage is follows: 

{% tabs %}

{% highlight xaml %}

<syncfusion:DockingManager Name="DockingManager" ContainerMode="TDI"IsTDIDragDropEnabled="False">   

	<Grid Name="grid1" syncfusion:DockingManager.State="Document"/>   
	
	<Grid Name="grid2" syncfusion:DockingManager.State="Document"/>
	
</syncfusion:DockingManager>

{% endhighlight  %}

{% highlight c# %}

DockingManager.IsTDIDragDropEnabled = false;

{% endhighlight  %}

{% endtabs %}
