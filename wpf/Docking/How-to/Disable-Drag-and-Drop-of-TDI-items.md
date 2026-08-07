---
layout: post
title: How to disable TDI items drag and drop in WPF Docking | Syncfusion®
description: Learn here how to disable drag and drop of tdi items in Syncfusion® WPF Docking (DockingManager) control, its elements and more.
platform: wpf
control: DockingManager
documentation: ug
---

# How to disable TDI items drag and drop in WPF Docking  

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
