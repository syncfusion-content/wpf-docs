---
layout: post
title: Creating Different Views in WPF Diagram | Syncfusion
description: Learn here all about Creating Different Views in the ContextViewManager support in Syncfusion WPF Diagram (classic) control and more.
platform: wpf
control: Diagram
 documentation: ug
---

# Creating Different Views in the ContextViewManager in WPF Diagram

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

![Diagram-View_img53](Diagram-View_images/Diagram-View_img53.png)



Context View
{:.caption}

N> By default, the context view manager will show the neighborhood view.

