---
layout: post
title: Creating-Different-Views-in-the-ContextViewManager
description: creating different views in the contextviewmanager
platform: wpf
control: Diagram
documentation: ug
---

# Creating Different Views in the ContextViewManager

ContextViewManager can be used to choose any one of the three different views. The nodes and connection will be created based on the view chosen.

1. Predecessors View: The predecessors view is used to display all hierarchical parent nodes of the selected node in a layout manner. 
2. Successors View: The successor view displays all the hierarchical child nodes of the selected node.
3. Neighborhood View: This view will be used to show immediate child and parent nodes of the selected node.

The following code example explains how to choose the predecessors view
{% highlight vbnet %}




‘Create ContextViewManager to attach source and target diagrams.

Dim ContextView As New ContextViewManager(source, target)

'Set ContextViewMode as Predecessors.

ContextView.ContextViewMode =ContextViewMode.Predecessors

{% endhighlight  %}

![C:/Users/jeganr/AppData/Local/Syncfusion/EssentialStudio/10.3.0.25/WPF/Diagram.WPF/Samples/3.5/WindowsSamples/Getting Started/Context View Demo/Images/ContextViewDemo.png](Diagram-View_images/Diagram-View_img53.png)



_Context View_

> Note: By default, the context view manager will show the neighborhood view.

