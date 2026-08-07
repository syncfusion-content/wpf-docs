---
layout: post
title: How to AutoHide all docked windows in Docking in WPF Data Grid
description: Learn How to AutoHide all docked windows in Docking in WPF Data Grid using Syncfusion controls. It supports data operations, UI customization, and enterprise features.
platform: WPF
control: DockingManager
documentation: ug
---

# How to AutoHide all docked windows in Docking in WPF Data Grid

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