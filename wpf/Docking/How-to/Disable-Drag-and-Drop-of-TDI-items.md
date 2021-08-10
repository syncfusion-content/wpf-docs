---
layout: post
title: Disable Drag and Drop of TDI items | DockingManager | wpf | Syncfusion
description: Disable drag and drop of tdi items in Syncfusion Essential Studio WPF DockingManager control, its elements and more.
platform: wpf
control: DockingManager
documentation: ug
---

# Disable Drag and Drop of TDI items  

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
