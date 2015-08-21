---
layout: post
title: Set-splitter-background-and-size
description: set splitter background and size
platform: wpf
control: DockingManager
documentation: ug
---

## Set splitter background and size

SplitterBackground is the property used to apply background to splitter between docked Children.


{% highlight html %}

<syncfusion:DockingManager Name="DockingManager" SplitterBackground="Black">    <Grid Name="grid1" syncfusion:DockingManager.Header="Window1"/>    <Grid Name="grid2" syncfusion:DockingManager.Header="Window2"/></syncfusion:DockingManager>

DockingManager.SplitterBackground = Brushes.Black;

{% endhighlight  %}

![C:/Users/Hemanth/Desktop/Documentation/Images/SplitterBackground.jpg](Set-splitter-background-and-size_images/Set-splitter-background-and-size_img1.jpeg)



