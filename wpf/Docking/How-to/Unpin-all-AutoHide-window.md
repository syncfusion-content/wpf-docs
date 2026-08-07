---
layout: post
title: How to unpin all AutoHide window in DockingManager in WPF Data Grid
description: Learn How to unpin all AutoHide window in DockingManager in WPF Data Grid using Syncfusion controls. It supports data operations, UI customization, and enterprise features.
platform: WPF
control: DockingManager
documentation: ug
---

# How to unpin all AutoHide window in DockingManager in WPF Data Grid

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


