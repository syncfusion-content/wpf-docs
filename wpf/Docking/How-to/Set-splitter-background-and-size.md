---
layout: post
title: Set splitter background and size | DockingManager | wpf | Syncfusion
description: set splitter background and size
platform: wpf
control: DockingManager
 documentation: ug
---

## Set splitter background and size

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


![](Set-splitter-background-and-size_images/Set-splitter-background-and-size_img1.jpeg)



