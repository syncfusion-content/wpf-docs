---
layout: post
title: AutoHide all docked windows | DockingManager | wpf | Syncfusion
description: autohide all docked windows
platform: wpf
control: DockingManager
 documentation: ug
---

# AutoHide all docked windows

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