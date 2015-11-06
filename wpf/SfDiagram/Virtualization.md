---
layout: post
title: Virtualization | SfDiagram | wpf | Syncfusion
description: virtualization
platform: wpf
control: SfDiagram
documentation: ug
---

# Virtualization

Virtualization is the process of loading the diagramming objects available in the visible area of the Diagram control, that is, only the diagramming objects that lie within the ViewPort of the ScrollViewer are loaded (remaining objects are loaded only when they come into view).

This feature gives optimized performance while loading and dragging items to the SfDiagram that consists of many Nodes and Line Connectors.

The following code example illustrates how to enable Virtualization in SfDiagram:

{% highlight c# %}

sfdiagram.Constraints = sfdiagram.Constraints | GraphConstraints.Virtualize;

{% endhighlight %}

N> For more information about virtualization, see_Appendix_.