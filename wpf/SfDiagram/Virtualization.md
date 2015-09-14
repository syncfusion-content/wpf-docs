---
layout: post
title: Virtualization
description: virtualization
platform: wpf
control: Control Name undefined
documentation: ug
---

### Virtualization

Virtualization is the process of loading the diagramming objects available in the visible area of the Diagram control, that is, only the diagramming objects that lie within the ViewPort of the ScrollViewer are loaded (remaining objects are loaded only when they come into view).



This feature gives optimized performance while loading and dragging items to the SfDiagram that consists of many Nodes and Line Connectors.

The following code example illustrates how to enable Virtualization in SfDiagram:



[C#]


sfdiagram.Constraints = sfdiagram.Constraints | GraphConstraints.Virtualize;



![](Virtualization_images/Virtualization_img1.jpeg)
{:.image }
_Note: For more information about virtualization, see_Appendix_._



