---
layout: post
title: Unpin all AutoHide window | DockingManager | wpf | Syncfusion
description: Unpin all autohide window in Syncfusion Essential Studio WPF DockingManager control, its elements and more.
platform: wpf
control: DockingManager
documentation: ug
---

## Unpin all AutoHide window

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


