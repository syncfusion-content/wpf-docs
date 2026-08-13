---
layout: post
title: How to set splitter background and size in WPF Docking | Syncfusion®
description: Learn here how to set splitter background and size in Syncfusion® WPF Docking (DockingManager) control, its elements and more.
platform: wpf
control: DockingManager
documentation: ug
---

# How to set splitter background and size in WPF Docking

SplitterBackground is the property used to apply background to splitter between docked Children.

{% tabs %}

{% highlight xaml %}

<syncfusion:DockingManager Name="DockingManager" SplitterBackground="Black">    

	<Grid Name="grid1" syncfusion:DockingManager.Header="Window1"/>    

	<Grid Name="grid2" syncfusion:DockingManager.Header="Window2"/>

</syncfusion:DockingManager>

{% endhighlight  %}

{% highlight c# %}

DockingManager.SplitterBackground = Brushes.Black;

{% endhighlight  %}

{% endtabs %}


![Set-splitter-background-and-size_images1](Set-splitter-background-and-size_images/Set-splitter-background-and-size_img1.jpeg)



