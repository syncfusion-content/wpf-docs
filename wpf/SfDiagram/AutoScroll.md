---
layout: post
title: AutoScroll | SfDiagram | wpf | Syncfusion
description: autoscroll
platform: wpf
control: SfDiagram
documentation: ug
---

# AutoScroll

AutoScroll feature enables you to perform drag operationS from one end to other end of a large Diagram. For example, when you want to drag a node towards the borders of Diagram, Diagram is automatically scrolled to place the node that does not lie in visible area. AutoScroll takes place for the following interation Node / Connector dragging, Resizing the Node, Multiple Selection (Rubber band selection). 

## Enable and Disable the AutoScroll 

Autoscroll is enabled by default. The following code example describes you how to disable the AutoSroll.



{% highlight c# %} 

// Removes AutoScroll from GraphConstraints 

sfDiagram.Constraints = sfDiagram.Constraints &~ GraphConstraints.AutoScroll;

{% endhighlight %}

N> GraphConstraints property is manipulated by using bitwise operations. For more information about bitwise operations, see [Bitwise Operations](http://help.syncfusion.com/UG/winrt/documents/appendix.htm).
