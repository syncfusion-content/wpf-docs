---
layout: post
title: How to AutoHide all docked windows in WPF Docking | Syncfusion®
description: Learn here how to autohide all docked windows in Syncfusion® WPF Docking (DockingManager) control, its elements and more.
platform: wpf
control: DockingManager
documentation: ug
---

# How to AutoHide all docked windows in WPF Docking

You can AutoHide all Docked windows by using the AutoHideAllDockWindow() method. This can be shown below.

{% tabs %}

{% highlight xaml %}

<syncfusion:DockingManager Name="DockingManager">    

	<Grid/>    
	
	<Grid/>    
	
	<Grid/>    
	
	<Grid/>  
	
</syncfusion:DockingManager>

{% endhighlight  %}

{% highlight c# %}

DockingManager.AutoHideAllDockWindow();

{% endhighlight  %}

{% endtabs %}