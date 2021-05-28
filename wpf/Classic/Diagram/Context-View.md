---
layout: post
title: Context View in WPF Diagram Control | Syncfusion
description: Learn here all about Context View support in Syncfusion WPF Diagram (classic) control, its elements and more details.
platform: wpf
control: Diagram
 documentation: ug
---

# Context View in WPF Diagram (classic)

A context view is a small view of an entire diagram with a new arrangement, where the small view and the arrangement are based on a particular view of the selected node. It provides three views:

* Successors view—shows all child nodes of the selected node.
* Predecessors view—displays all parent nodes of the selected node.
* Neighborhood view—displays the immediate child and parent nodes of the selected node.

## Tables for Properties and Methods

### Properties



<table>
<tr>
<th>
Property </th><th>
Description </th><th>
Type </th><th>
Data Type </th></tr>
<tr>
<td>
ContextViewMode</td><td>
This property is used to get or set the context view mode of the context view manager.</td><td>
Dependency property</td><td>
ContextViewMode </td></tr>
<tr>
<td>
Layout </td><td>
This property is used to manage layout information of the context view manager.</td><td>
CLR property</td><td>
ILayout</td></tr>
<tr>
<td>
SourceControl</td><td>
This property is used to get a Diagram control to be a source of the context view manager.</td><td>
CLR property</td><td>
DiagramControl</td></tr>
<tr>
<td>
TargetControl</td><td>
This property is used to get a Diagram control to be a target of the context view manager.</td><td>
CLR property</td><td>
DiagramControl</td></tr>
</table>


### Methods



<table>
<tr>
<th>
Method </th><th>
Description </th><th>
Parameters </th><th>
Type </th></tr>
<tr>
<td>
public ContextViewManager(DiagramControl source, DiagramControl target)</td><td>
Constructor of the context view manager.</td><td>
source—a Diagram control in which selection changes will be monitored.target—a Diagram control to which a new diagram will be created based on the selected node and the context view chosen.</td><td>
In WPF </td></tr>
<tr>
<td>
RefreshLayout</td><td>
This method is used to update the layout. It will be called automatically and can also be forced to be updated.</td><td>
NA</td><td>
In WPF</td></tr>
</table>

## Adding ContextViewManager to an Application

ContextViewManager is a class that helps to communicate between a source diagram and a target diagram.

* Source—it is a Diagram control in which selection changes will be monitored.
* Target—it is a Diagram control to which a new diagram will be created based on the selected node and the context view chosen.  

### Steps to create ContextViewManager

1. Create a Diagram control to be used as a target to show the context view of another Diagram control.

   {%highlight html%}


			<syncfusion:DiagramControl  Height="235" Width="250"  Name="targetDiagramControl">

			<syncfusion:DiagramControl.Model>

			<syncfusion:DiagramModel x:Name="targetDiagramModel"/>

			</syncfusion:DiagramControl.Model>

			<syncfusion:DiagramControl.View>

			<syncfusion:DiagramView EnableFitToPage="True" Name="targetDiagramView"/>

			</syncfusion:DiagramControl.View>

			</syncfusion:DiagramControl>
			
		{%endhighlight%}





2. Create another Diagram control to be used as a source.

3. Create a ContextViewManager instance to synchronize the source and target diagrams.

    {%highlight c#%}


			// Create ContextViewManager to attach the source and target diagrams.

			ContextViewManager ContextView = new ContextViewManager(source, target);

			//Set ContextViewMode as Predecessors.

				   ContextView.ContextViewMode =ContextViewMode.Predecessors;

			// Create a layout for ContextView.

			DirectedTreeLayout layout = new DirectedTreeLayout(diagramModel,diagramView);

			diagramModel.HorizontalSpacing = 10;

			diagramModel.VerticalSpacing = 80;

			diagramModel.SpaceBetweenSubTrees = 10;

			// Set the layout of the ContextView.

			ContextView.Layout = layout;

        {%endhighlight%}

        
		{%highlight vbnet%}



			' Create ContextViewManager to attach source and target diagrams.

			Dim ContextView As New ContextViewManager(source, target)

			'Set ContextViewMode as Predecessors.

			ContextView.ContextViewMode =ContextViewMode.Predecessors

			' Create a layout for ContextView.

			Dim layout As New DirectedTreeLayout(diagramModel,diagramView)

			diagramModel.HorizontalSpacing = 10

			diagramModel.VerticalSpacing = 80

			diagramModel.SpaceBetweenSubTrees = 10

			' Set the layout of the ContextView.

			ContextView.Layout = layout

         {%endhighlight%}
   
