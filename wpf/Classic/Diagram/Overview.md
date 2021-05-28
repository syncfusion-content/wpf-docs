---
layout: post
title: About WPF Diagram Control | Syncfusion
description: Learn here all about introduction of Syncfusion WPF Diagram (classic) control, its elements and more details.
platform: wpf
control: Diagram
 documentation: ug
---

# WPF Diagram (classic) Overview

Essential Diagram WPF is an extensible and high-performance diagramming Framework for WPF applications. It can be used by the developers who want to develop Microsoft Visio-like interactive graphics and diagramming applications. It stores graphical objects in a node graph and renders those objects on the screen.  

N> A node graph is a structure consisting of nodes connected to each other by lines referred to as edges.

Essential Diagram supports both vector and raster graphics on the drawing surface. 

N> A raster (bitmap) image uses a grid of individual pixels where each pixel can be a different color or shade. Bitmaps are composed of pixels.

Vector graphics use mathematical relationships between points and the paths connecting them to describe an image. Vector graphics are composed of paths.

Essential Diagram WPF allows you to create interactive diagrams easily.  


## Real World Scenarios

Essential Diagram WPF finds its application in various fields; some of them are listed below.

* Essential Diagram WPF can be effectively used to create process flow diagrams and flow charts. The connectors with a label depict the process flow from one level to another.



![Overview_img1](Overview_images/Overview_img1.jpeg)





* Essential Diagram WPF can be used to create electrical diagrams. The electrical shapes can be loaded to the SymbolPalette and can be dragged to the drawing surface. Connections can then be made as desired and the circuit diagrams can be created.



![Overview_img2](Overview_images/Overview_img2.jpeg)





* Essential Diagram WPF employs automatic layout algorithms to layout the nodes automatically in a tree structure. This kind of setting is typically useful in creating Organizational Layout and for data binding purposes.



![Overview_img3](Overview_images/Overview_img3.jpeg)





* Essential Diagram WPF allows you to create Swim lane diagrams, which groups a set of sub processes in a visual manner, by arranging them in lanes. Nodes can be manually placed to create swim lanes. The process in each lane may then be described using the nodes and the flow can be depicted using the connections as illustrated in the following diagram.



![Overview_img4](Overview_images/Overview_img4.jpeg)



_Swim Lane Diagram_



* Essential Diagram WPF allows you to create a Data Flow Diagram, A data-flow diagram (DFD) is a graphical representation of the "flow" of data through an information system. DFD's can also be used for the visualization of data processing.



![Overview_img5](Overview_images/Overview_img5.png)





* Essential Diagram WPF allows you to create a Floor Plan,



![Overview_img6](Overview_images/Overview_img6.png)





## Key Features



The following are the key features of Essential Diagram WPF:



* Nodes - Nodes are graphical objects that can be drawn on the page by selecting them from the SymbolPalette and dropping them on the page. 
* Transformations - The following transformations are provided:
1. Translate: Ability to move the nodes.
2. Rotate: Ability to rotate the nodes.
3. Scale: Ability to resize the nodes. 
* Groups and Ungroup - Essential Diagram WPF provides support to group and ungroup nodes. Grouping feature comes in handy when you want to apply the same edits to a number of objects and yet retain their individuality. All the operations performed on the group also affects the individual items in the group. However any item in the group can also be edited individually. On ungrouping, the items in the group again act as individual entities.
* Layers - Essential Diagram for WPF supports layer display. Numerous nodes and line connectors can be added to a layer and the visible property of its contents can be hidden by changing the visible property of the layer. A node or line connector can be added to any number of layers, and the node is visible only if the all layers to which this node or line connector belongs to are visible.
* Connectors - Connectors are the objects that are used to create a link between two nodes. Three types of connectors provided are as follows:
1. Orthogonal
2. Bezier
3. Straight 
* LineBridging - Line Bridging creates a bridge for lines to smartly cross over other line at points of intersection.

When two line connectors meets each other, line with higher z-order will draw an arc over the line with lower z-order. 

Only Straight and Orthogonal Connector type supports line bridging.

* Custom Ports - Essential Diagram WPF provides the ability to define custom ports for making connections. The ConnectionPort class can be used for defining custom ports on the nodes. Any number of ports can be defined on a node. The user can define a port on any part of the node and make connection to that port. The port's visibility can also be controlled. Several customizable properties have been provided for the port.
* Decorator Shapes - Decorator shapes can be added to the head and tail of the connectors. Three types of decorator shapes provided are as follows:
1. Arrow
2. Diamond
3. Circle
* Export - Essential Diagram for WPF offers capabilities to export a diagram representation into various formats. The formats include JPEG, BMP, PNG, TIFF, GIF, WDP and XAML.
* Command Architecture - Essential Diagram for WPF provides several commands as follows. 
* Zoom Commands 
* Alignment Commands
* Spacing and Sizing Commands
* Group and Ungroup Commands 
* Undo and Redo Commands
* Z-order Commands
* Nudge Commands
* Clipboard Commands
* Delete Command
* Zooming, Scrolling and Panning - Zooming, scrolling, and panning are supported and can be achieved using sufficient interactive diagram tools. 
* Grid Lines - The drawing area of the Diagram control can be rendered with horizontal and vertical Grid lines.
* Rulers - Horizontal and vertical rulers are provided to indicate the coordinates of the mouse position with respect to the view.
* Measurement Units - As different fields require different units of measure, several measurement units are provided such that the end-users can choose the unit that is most comfortable and suitable for their use.
* SymbolPalette - The SymbolPalette control displays the node shapes and allows a user to drag the symbols onto the diagram. It supports grouping and filtering of symbols, and it is implemented based on the Syncfusion's Gallery control. Also, custom shapes can be added to the SymbolPalette.
* Label Editor - A label editor is provided for each node and connector; it enables the user to edit labels at run time if IsLabelEditable property is set to true for the corresponding object.
* Customizable - The control is highly customizable and extensible. Customization is easy, and custom UI tools can be easily created and registered.
* Automatic Layout Management - Essential Diagram WPF provides the ability to set automatic layout for the nodes. Several layout types have been provided. They are:
* DirectedTree Layout - The DirectedTree layout arranges nodes in a tree-like structure. This layout can be applied to any diagram that is composed of a directed tree graph with unique root and child nodes.
* HierarchicalTree Layout - The HierarchicalTree layout also arranges nodes in a tree-like structure; however, unlike the directed tree layout, the nodes in hierarchical layout may have multiple parents hence avoiding the need to specify the root.
* RadialTree Layout - The Radial-TreeLayout is a specialization of the Directed Tree Layout Manager that employs a circular layout algorithm for locating the diagram nodes. The RadialTreeLayoutManager arranges nodes in a circular layout, positioning the root node at the center of the graph and the child nodes in a circular fashion around the root. Sub-trees formed by the branching of child nodes are located radially around the child nodes. This arrangement results in an ever-expanding concentric arrangement with radial proximity to the root node indicating the node level in the hierarchy.
* Table Layout - The Table layout arranges the nodes in a tabular structure based on specified intervals between them. The layout depends upon the number of nodes in each row and column specified. The nodes are assigned rows and columns based on the order in which they are added to the model and based on the maximum nodes allowed in that row and column. 
* Serialization - The Diagram Page can be saved in XAML format for future use. The user can then load the saved page into the current view and start editing the page.
* Event Mechanisms - Several events have been provided for nodes and connections.
* Print and Print Preview - This feature enables the user to set a printer to be used, and it allows the user to define the pages and the number of copies that should be printed. It also provides an overview of the document, showing how the document will appear when printed.




## User Guide Organization

The product comes with numerous samples as well as an extensive documentation to guide you. This User Guide provides detailed information on the features and functionalities of the Essential Diagram for WPF. It is organized into the following sections:

* Overview-This section gives a brief introduction to the product and its key features.
* Getting Started-This section guides you on getting started with WPF application, controls etc.
* Concepts and Features-The features of individual controls are illustrated with use case scenarios, code examples and screen shots under this section.

## Document Conventions 

The conventions below will help you to quickly identify the important sections of information, while using the content:



<table>
<tr>
<th>
Convention</th><th>
Description of the Icon</th></tr>
<tr>
<td>
Note</td><td>
Represents important information.</td></tr>
<tr>
<td>
Example</td><td>
Represents an example.</td></tr>
<tr>
<td>
Tip</td><td>
Represents useful hints, that will help you in using the controls and features.</td></tr>
<tr>
<td>
Additional information</td><td>
Represents additional information on the corresponding topic.</td></tr>
</table>


