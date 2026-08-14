---
layout: post
title: How to enable TabItemContextMenu in WPF Docking | Syncfusion®
description: Learn here how to enable/disable tabitemcontextmenu and tablistcontextmenu in Syncfusion® WPF Docking (DockingManager) control, its elements and more.
platform: wpf
control: DockingManager
documentation: ug
---

# How to enable TabItemContextMenu in WPF Docking

ShowTabItemContextMenu is the property that is used to disable the showing of Context Menu when right-clicked on the document tab. Similarly, ShowTabListContextMenu is used to disable the showing of Context Menu list when clicked on the TabControl menu toggle button. The usages are given below:

{% tabs %}

{% highlight xaml %}

<syncfusion:DockingManager Name="DockingManager" ShowTabItemContextMenu="False" ShowTabListContextMenu="False" UseDocumentContainer="True" ContainerMode="TDI">       
	
	<Grid Name="grid1" syncfusion:DockingManager.State="Document"/>  
	
	<Grid Name="grid2" syncfusion:DockingManager.State="Document"/>
	
</syncfusion:DockingManager>

{% endhighlight  %}

{% highlight c# %}

//Disables the TabItem context menu.

DockingManager.ShowTabItemContextMenu = false;

//Disables the TabList context menu.

DockingManager.ShowTabListContextMenu = false;

{% endhighlight  %}

{% endtabs %}

