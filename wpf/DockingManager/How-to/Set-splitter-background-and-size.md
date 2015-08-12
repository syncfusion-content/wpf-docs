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



{% highlight xml %}
<syncfusion:DockingManager Name="DockingManager" SplitterBackground="Black"> 
   <Grid Name="grid1" syncfusion:DockingManager.Header="Window1"/>  
   <Grid Name="grid2" syncfusion:DockingManager.Header="Window2"/>
   </syncfusion:DockingManager>
 {% endhighlight %}
{% highlight c# %}
	DockingManager.SplitterBackground = Brushes.Black;
{% endhighlight %}


![](Set-splitter-background-and-size_images/Set-splitter-background-and-size_img1.jpeg)



