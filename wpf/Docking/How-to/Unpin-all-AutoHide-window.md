---
layout: post
title: How to unpin all AutoHide window in WPF DockingManager | Syncfusion®
description: Learn here how to unpin all autohide window in Syncfusion® WPF Docking (DockingManager) control, its elements and more.
platform: wpf
control: DockingManager
documentation: ug
---

# How to unpin all AutoHide window in WPF DockingManager

You can Unpin all AutoHidden windows by using the method UnPinAutoHide().This can be shown below:

{% tabs %}

{% highlight xaml %}

<syncfusion:DockingManager Name="DockingManager">            

	<Grid syncfusion:DockingManager.State="AutoHidden"/>            
	
	<Grid syncfusion:DockingManager.State="AutoHidden"/>           

	<Grid syncfusion:DockingManager.State="AutoHidden"/>            
	
	<Grid syncfusion:DockingManager.State="AutoHidden"/>  
	
</syncfusion:DockingManager>

{% endhighlight  %}

{% highlight c# %}

DockingManager.UnPinAllAutoHide();  

{% endhighlight  %}

{% endtabs %}


