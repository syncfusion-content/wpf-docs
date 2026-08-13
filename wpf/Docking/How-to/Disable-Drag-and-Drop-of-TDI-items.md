---
layout: post
title: Disable TDI drag and drop in WPF DocumentContainer | Syncfusion®
description: Learn how to disable drag and drop of TDI items in Syncfusion WPF DocumentContainer by setting the IsTDIDragDropEnabled property of DockingManager.
platform: wpf
control: DockingManager
documentation: ug
---

# Disable TDI drag and drop in WPF DocumentContainer  

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
