---
layout: post
title: How to set splitter background and size in Docking in WPF Data Grid
description: Learn How to set splitter background and size in Docking in WPF Data Grid using Syncfusion controls. It supports data operations, UI customization, and enterprise features.
platform: WPF
control: DockingManager
documentation: ug
---

# How to set splitter background and size in Docking in WPF Data Grid

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



