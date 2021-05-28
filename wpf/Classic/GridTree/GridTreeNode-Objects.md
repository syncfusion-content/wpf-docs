---
layout: post
title: GridTreeNode Objects in WPF Wizard Control control | Syncfusion
description: Learn here all about GridTreeNode Objects support in Syncfusion WPF GridTreeControl (Classic) control and more.
platform: wpf
control: GridTree 
 documentation: ug
---

# GridTreeNode Objects in WPF GridTreeControl (Classic)

The GridTreeControl.InternalGrid.Nodes collection holds the GridTreeNodes that represents the visible nodes in the GridTree control. The GridTreeNode object has the following properties:



<table>
<tr>
<th>
GridTreeNode Property</th><th>
Description</th><th>
Type of Property</th><th>
Value It Accepts</th><th>
Property Syntax</th></tr>
<tr>
<td>
ChildNodes</td><td>
A collection of GridTreeNodes that represent the child nodes for this node.</td><td>
Normal</td><td>
List<GridTreeNode></td><td>
treeGrid.ParentNode.ChildNodes</td></tr>
<tr>
<td>
Expanded </td><td>
Controls the expand state for the node. Set this property to true, to expand this node, or set it to false, and to collapse this node.</td><td>
Normal</td><td>
bool</td><td>
gridTreeNode.Expanded</td></tr>
<tr>
<td>
HasChildNodes</td><td>
Determines whether this node has child nodes or not.</td><td>
Normal</td><td>
bool</td><td>
gridTreeNode.HasChildNodes</td></tr>
<tr>
<td>
IsSelected</td><td>
Controls whether this node is selected.</td><td>
Normal</td><td>
bool</td><td>
gridTreeNode.IsSelected</td></tr>
<tr>
<td>
Item</td><td>
The data item (an object from the underlying bound data) associated with this node.</td><td>
Normal</td><td>
Object</td><td>
gridTreeNode.Item</td></tr>
<tr>
<td>
Level</td><td>
Indicates tree level for this node.</td><td>
Normal</td><td>
int </td><td>
gridTreeNode.Level</td></tr>
<tr>
<td>
NodeHeight</td><td>
The height of the grid row associated with this node.</td><td>
Normal</td><td>
Double</td><td>
gridTreeNode.NodeHeight</td></tr>
<tr>
<td>
ParentItem</td><td>
The data item (an object from the underlying bound data) associated with the parent node of this node.</td><td>
Normal</td><td>
Object</td><td>
gridTreeNode.ParentItem</td></tr>
<tr>
<td>
ParentNode</td><td>
The GridTreeNode that is the parent node of this node.</td><td>
Normal</td><td>
GridTreeNode</td><td>
gridTreeNode.ParentNode</td></tr>
<tr>
<td>
SelectedColumns</td><td>
Holds the column names that are selected for this node. This property is only valid when GridTreeControl.EnableNodeSelections is {{ '_false_' | markdownify }} and GridTreeControl.EnableSelections is {{ '_true_' | markdownify }}.</td><td>
Normal</td><td>
List<string></td><td>
gridTreeNoe.SelectedColumns</td></tr>
</table>


