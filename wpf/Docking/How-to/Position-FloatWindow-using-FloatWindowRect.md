---
layout: post
title: Position FloatWindow using FloatWindowRect | DockingManager | wpf | Syncfusion
description: position floatwindow using floatwindowrect
platform: wpf
control: DockingManager
 documentation: ug
---

# Position FloatWindow using FloatWindowRect

FloatWindowRect is used to specify the Rect bounds for the float child that is displayed in FloatWindow.

{% tabs %}

{% highlight xaml %}

<syncfusion:DockingManager Name="DockingManager">

	<Grid Name="grid1" syncfusion:DockingManager.State="Float" syncfusion:DockingManager.FloatingWindowRect="0,0,200,200"/>

</syncfusion:DockingManager>

{% endhighlight  %}

{% highlight c# %}

DockingManager.SetFloatingWindowRect(grid1, new Rect(0, 0, 200, 200));

{% endhighlight  %}

{% endtabs %}