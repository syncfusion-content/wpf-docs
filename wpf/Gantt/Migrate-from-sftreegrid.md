---
layout: post
title: Migrate GridTreeControl to TreeGrid in WPF Gantt Control | Syncfusion
description: Learn about GridTreeControl to SfTreeGrid migration in Syncfusion Essential Studio WPF Gantt control.
platform: wpf
control: Gantt
documentation: ug
---

# Migrating from GridTreeControl to SfTreeGrid
The transition from GridTreeControl to SfTreeGrid is aimed at integrating drag-and-drop, filtering, and sorting capabilities into the Gantt grid. This transition result in the breaking of certain APIs and the introduction of new ones. Please find the difference in the following topics.

## API breaking

### Class
<table>
<tr>
<th>Class Name</th>
<th>Existing base class</th>
<th>New base class</th>
</tr>

<tr>
<td>GanttGrid</td>
<td>GridTreeControl</td>
<td>SfTreeGrid </td>
</tr>
</table>

### Properties
<table>
<tr>
<th>Class name</th>
<th>Existing API type</th>
<th>Existing API name</th>
<th>New API type</th>
<th>New API Name</th>
</tr>

<tr>
<td>GanttControl</td>
<td>Line</td>
<td>CurrentDateLine</td>
<td>CurrentDateIndicator</td>
<td>CurrentDateIndicator</td>
</tr>

<tr>
<td>GanttControl</td>
<td>CurrentDateLinePositions</td>
<td>CurrentDateLinePositions</td>
<td>CurrentDateIndicatorPositions</td>
<td>CurrentDate IndicatorPositions</td>
</tr>

<tr>
<td>GanttGrid</td>
<td>ObservableCollection(GridTreeColumn)</td>
<td>Columns</td>
<td>TreeGridColumns</td>
<td>Columns</td>
</tr>

<tr>
<td>GanttGrid</td>
<td>GridTreeStartUpExpandState</td>
<td>ExpandStateAtStartUp</td>
<td>GanttAutoExpandMode</td>
<td>AutoExpandMode</td>
</tr>

<tr>
<td>GanttGrid</td>
<td>bool</td>
<td>ReadOnly</td>
<td>bool</td>
<td>IsReadOnly</td>
</tr>

<tr>
<td>GanttGrid</td>
<td>bool</td>
<td>AllowSort</td>
<td>bool</td>
<td>AllowSorting</td>
</tr>

<tr>
<td>GanttGrid</td>
<td>GridSelectedTreeNodes</td>
<td>SelectedNodes</td>
<td>ObservableCollection(object)</td>
<td>SelectedItems</td>
</tr>
</table> 

### Methods
<table>
<tr>
<th>Class name</th>
<th>Existing method</th>
<th>New method</th>
</tr>

<tr>
<td>GanttGrid</td>
<td>CollapseAllNodes(GridTreeNode n)</td>
<td>CollapseAllNodes(TreeNode treeNode)</td>
</tr>
</table> 

### Events
<table>
<tr>
<th>Class name</th>
<th>Existing structure</th>
<th>Existing name</th>
<th>New structure</th>
<th>New name</th>
</tr>

<tr>
<td>GanttGrid</td>
<td>GridTreeNodeEventHandler</td>
<td>ExpandStateChanged</td>
<td>EventHandler<NodeExpandedEventArgs></td>
<td>NodeExpanded</td>
</tr>

<tr>
<td>GanttGrid</td>
<td>GridTreeNodeEventHandler</td>
<td>ExpandStateChanged</td>
<td>EventHandler<NodeCollapsedEventArgs></td>
<td>NodeCollapsed</td>
</tr>

<tr>
<td>GanttGrid</td>
<td>GridTreeNodeEventHandler</td>
<td>ItemsSourceChanged </td>
<td>EventHandler<TreeGridItemsSourceChangedEventArgs></td>
<td>ItemsSourceChanged</td>
</tr>
</table> 

### Enums
<table>
<tr>
<th>Existing name</th>
<th>Existing members</th>
<th>New name</th>
<th>New members</th>
</tr>

<tr>
<td>SelectionMode</td>
<td>MouseMove, MouseClick</td>
<td>GanttSelectionMode</td>
<td>None, Single, Multiple</td>
</tr>

<tr>
<td>GridTreeNodeActions</td>
<td>Expanding, Expanded, Collapsing, Collapsed, Selecting, Unselecting</td>
<td>GanttAutoExpandMode</td>
<td>None, RootNodesExpanded, AllNodesExpanded</td>
</tr>
</table>

### Column types
<table>
<tr>
<th>GridTreeControl</th>
<th>GridTreeColumn</th>
</tr>

<tr>
<td>SfTreeGrid</td>
<td>TreeGridTextColumn, TreeGridComboBoxColumn, TreeGridCurrencyColumn, TreeGridDateTimeColumn, TreeGridHyperlinkColumn, TreeGridMaskColumn, TreeGridNumericColumn, TreeGridPercentColumn</td>
</tr>
</table>

### Removed public classes
<table>
<tr>
<th>Class name</th>
<th>Base class</th>
</tr>

<tr>
<td>PredecessorCellRenderer</td>
<td>GridCellTextBoxRenderer</td>
</tr>

<tr>
<td>PredecessorCellModel</td>
<td>GridCellModel(PredecessorCellRenderer)</td>
</tr>

<tr>
<td>ResourceCellRenderer</td>
<td>GridCellTextBoxRenderer</td>
</tr>

<tr>
<td>ResourceCellModel</td>
<td>GridCellModel(ResourceCellRenderer)</td>
</tr>
</table>

### Removed XAML files

* Blend
* Metro
* Office2010Black
* Office2010Silver
* VS2010

### Removed API
<table>
<tr>
<th>Class name</th>
<th>Property name</th>
<th>Property type</th>
</tr>

<tr>
<td>GanttControl</td>
<td>VisualStyle</td>
<td>VisualStyle</td>
</tr>
</table>

### Access type changed classes
<table>
<tr>
<th>Class name</th>
<th>Base class</th>
<th>Existing access type</th>
<th>Changed access type</th>
</tr>

<tr>
<td>CollectionToStringConverter</td>
<td>IValueConverter</td>
<td>internal</td>
<td>public</td>
</tr>

<tr>
<td>BoolToVisibilityConverter</td>
<td>IValueConverter</td>
<td>internal</td>
<td>public</td>
</tr>
</table>

## Newly added API's in GanttControl

### Properties
<table>
<tr>
<th>Name</th>
<th>Type</th>
<th>Default value</th>
<th>Summary</th>
</tr>

<tr>
<td>AllowDragDrop </td>
<td>bool</td>
<td>true</td>
<td>Gets or sets a value indicating whether to allow the nodes reordering in Gantt.</td>
</tr>

<tr>
<td>AutoExpandMode</td>
<td>GanttAutoExpandMode</td>
<td>AllNodesExpanded</td>
<td>Gets or sets the value which indicates how the nodes to be expanded while loading.</td>
</tr>

<tr>
<td>AllowSorting</td>
<td>bool</td>
<td>false</td>
<td>Gets or sets a value indicating whether to allow sorting of records in Gantt.</td>
</tr>

<tr>
<td>AllowFiltering</td>
<td>bool</td>
<td>false</td>
<td>Gets or sets a value indicating whether to allow filtering of records in Gantt.</td>
</tr>
</table>

### Events
<table>
<tr>
<th>Event name</th>
<th>EventArg name</th>
<th>Summary</th>
</tr>

<tr>
<td>TreeGridNodeDragStarting</td>
<td>TreeGridNodeDragStartingEventArgs</td>
<td>Provides data for the TreeGridNodeDragStarting  event, which occurs when an item is to be dragged.</td>
</tr>

<tr>
<td>TreeGridNodeDragging</td>
<td>TreeGridNodeDraggingEventArgs</td>
<td>Provides data for the TreeGridNodeDragging event, which occurs when an item is being dragged over the Gantt control.</td>
</tr>

<tr>
<td>TreeGridNodeDrop</td>
<td>TreeGridNodeDropEventArgs</td>
<td>Provides data for the TreeGridNodeDrop event, which occurs when an item to be dropped within Gantt control.</td>
</tr>

<tr>
<td>SelectionChanging</td>
<td>SelectionChangingEventArgs</td>
<td>Occurs when the selection is being changed in the Gantt.</td>
</tr>

<tr>
<td>SelectionChanged</td>
<td>SelectionChangedEventArgs</td>
<td>Occurs when the selection is changed in the Gantt.</td>
</tr>
</table>