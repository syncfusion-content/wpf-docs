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

## Namespaces

<table>
<tr>
<th>Removed namespaces</th>
<th>Added namespaces</th></tr>
<tr>
<td>Syncfusion.Grid.WPF, Syncfusion.GridCommon.WPF</td>
<td>Syncfusion.SfGrid.WPF, Syncfusion.Data.WPF, Syncfusion.Themes.MaterialLight.WPF</td>
</tr>
</table>

## API breaking

### Class
<table>
<tr>
<th>Class Name</th>
<th>Existing base class</th>
<th>New base class</th>
</tr>

<tr>
<td>{{'[GanttGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.Grid.GanttGrid.html)'| markdownify }}</td>
<td>{{'[GridTreeControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridTreeControl.html)'| markdownify }}</td>
<td>{{'[SfTreeGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html)'| markdownify }} </td>
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
<td>{{'[GanttGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.Grid.GanttGrid.html)'| markdownify }}</td>
<td>ObservableCollection(GridTreeColumn)</td>
<td>{{'[Columns](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridTreeControl.html#Syncfusion_Windows_Controls_Grid_GridTreeControl_Columns)'| markdownify }}</td>
<td>{{'[TreeGridColumns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridColumns.html)'| markdownify }}</td>
<td>{{'[Columns](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_Columns)'| markdownify }}</td>
</tr>

<tr>
<td>{{'[GanttGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.Grid.GanttGrid.html)'| markdownify }}</td>
<td>{{'[GridTreeStartUpExpandState](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridTreeStartUpExpandState.html)'| markdownify }}</td>
<td>{{'[ExpandStateAtStartUp](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridTreeControl.html#Syncfusion_Windows_Controls_Grid_GridTreeControl_ExpandStateAtStartUp)'| markdownify }}</td>
<td>{{'[AutoExpandMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.AutoExpandMode.html)'| markdownify }}</td>
<td>{{'[AutoExpandMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_AutoExpandMode)'| markdownify }}</td>
</tr>

<tr>
<td>{{'[GanttGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.Grid.GanttGrid.html)'| markdownify }}</td>
<td>bool</td>
<td>{{'[ReadOnly](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridTreeControl.html#Syncfusion_Windows_Controls_Grid_GridTreeControl_ReadOnly)'| markdownify }}</td>
<td>bool</td>
<td>{{'[IsReadOnly](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_IsReadOnly)'| markdownify }}</td>
</tr>

<tr>
<td>{{'[GanttGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.Grid.GanttGrid.html)'| markdownify }}</td>
<td>bool</td>
<td>{{'[AllowSort](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridTreeControl.html#Syncfusion_Windows_Controls_Grid_GridTreeControl_AllowSort)'| markdownify }}</td>
<td>bool</td>
<td>{{'[AllowSorting](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_AllowFiltering)'| markdownify }}</td>
</tr>

<tr>
<td>{{'[GanttGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.Grid.GanttGrid.html)'| markdownify }}</td>
<td>{{'[GridSelectedTreeNodes](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridSelectedTreeNodes.html)'| markdownify }}</td>
<td>{{'[SelectedNodes](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridTreeControl.html#Syncfusion_Windows_Controls_Grid_GridTreeControl_SelectedNodes)'| markdownify }}</td>
<td>ObservableCollection(object)</td>
<td>{{'[SelectedItems](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectedItems)'| markdownify }}</td>
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
<td>{{'[GanttGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.Grid.GanttGrid.html)'| markdownify }}</td>
<td>{{'[CollapseAllNodes(GridTreeNode n)](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridTreeControl.html#Syncfusion_Windows_Controls_Grid_GridTreeControl_CollapseNode_Syncfusion_Windows_Controls_Grid_GridTreeNode_)'| markdownify }}</td>
<td>{{'[CollapseAllNodes(TreeNode treeNode)](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_CollapseAllNodes_Syncfusion_UI_Xaml_TreeGrid_TreeNode_)'| markdownify }}</td>
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
<td>{{'[GanttGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.Grid.GanttGrid.html)'| markdownify }}</td>
<td>{{'[GridTreeNodeEventHandler](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridTreeNodeEventHandler.html)'| markdownify }}</td>
<td>{{'[ExpandStateChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridTreeControl.html#Syncfusion_Windows_Controls_Grid_GridTreeControl_ExpandStateChanged)'| markdownify }}</td>
<td>{{'[EventHandler(NodeExpandedEventArgs)](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.NodeExpandedEventArgs.html)'| markdownify }}</td>
<td>{{'[NodeExpanded](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_NodeExpanded)'| markdownify }}</td>
</tr>

<tr>
<td>{{'[GanttGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.Grid.GanttGrid.html)'| markdownify }}</td>
<td>{{'[GridTreeNodeEventHandler](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridTreeNodeEventHandler.html)'| markdownify }}</td>
<td>{{'[ExpandStateChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridTreeControl.html#Syncfusion_Windows_Controls_Grid_GridTreeControl_ExpandStateChanged)'| markdownify }}</td>
<td>{{'[EventHandler(NodeCollapsedEventArgs)](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.NodeCollapsedEventArgs.html)'| markdownify }}</td>
<td>{{'[NodeCollapsed](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_NodeCollapsed)'| markdownify }}</td>
</tr>

<tr>
<td>{{'[GanttGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.Grid.GanttGrid.html)'| markdownify }}</td>
<td>{{'[GridRoutedEventHandler](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.ComponentModel.GridRoutedEventHandler.html)'| markdownify }}</td>
<td>{{'[ItemsSourceChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridTreeControl.html#Syncfusion_Windows_Controls_Grid_GridTreeControl_ItemsSourceChanged)'| markdownify }} </td>
<td>{{'[EventHandler(TreeGridItemsSourceChangedEventArgs)](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridItemsSourceChangedEventArgs.html)'| markdownify }}</td>
<td>{{'[ItemsSourceChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ItemsSourceChanged)'| markdownify }}</td>
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
<td>{{'[GridSelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GridSelectionMode.html)'| markdownify }}</td>
<td>MouseMove, MouseClick</td>
<td>{{'[SelectionMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Grid.SfGridBase.html#Syncfusion_UI_Xaml_Grid_SfGridBase_SelectionMode)'| markdownify }}</td>
<td>None, Single, Multiple</td>
</tr>

<tr>
<td>{{'[GridTreeNodeActions](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridTreeNodeActions.html)'| markdownify }}</td>
<td>Expanding, Expanded, Collapsing, Collapsed, Selecting, Unselecting</td>
<td>{{'[AutoExpandMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_AutoExpandMode)'| markdownify }}</td>
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
<td>{{'[SfTreeGrid](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html)'| markdownify }}</td>
<td>{{'[TreeGridTextColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridTextColumn.html#%22%22)'| markdownify }}, {{'[TreeGridComboBoxColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridComboBoxColumn.html#%22%22)'| markdownify }}, {{'[TreeGridCurrencyColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridCurrencyColumn.html#%22%22)'| markdownify }}, {{'[TreeGridDateTimeColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridDateTimeColumn.html#%22%22)'| markdownify }}, {{'[TreeGridHyperlinkColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridHyperlinkColumn.html#%22%22)'| markdownify }}, {{'[TreeGridMaskColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridMaskColumn.html#%22%22)'| markdownify }}, {{'[TreeGridNumericColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridNumericColumn.html#%22%22)'| markdownify }}, {{'[TreeGridPercentColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridPercentColumn.html#%22%22)'| markdownify }}, {{'[TreeGridCheckBoxColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridCheckBoxColumn.html#%22%22)'| markdownify }}, {{'[TreeGridTemplateColumn](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridTemplateColumn.html#%22%22)'| markdownify }}</td>
</tr>
</table>

### Removed public classes
<table>
<tr>
<th>Class name</th>
<th>Base class</th>
</tr>

<tr>
<td>{{'[PredecessorCellRenderer](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.Grid.PredecessorCellRenderer.html)'| markdownify }}</td>
<td>{{'[GridCellTextBoxRenderer](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridCellTextBoxRenderer.html)'| markdownify }}</td>
</tr>

<tr>
<td>{{'[PredecessorCellModel](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.Grid.PredecessorCellModel.html)'| markdownify }}</td>
<td>{{'[GridCellModel(PredecessorCellRenderer)](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridCellModel-1.html)'| markdownify }}</td>
</tr>

<tr>
<td>{{'[ResourceCellRenderer](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.Grid.ResourceCellRenderer.html)'| markdownify }}</td>
<td>{{'[GridCellTextBoxRenderer](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridCellTextBoxRenderer.html)'| markdownify }}</td>
</tr>

<tr>
<td>{{'[ResourceCellModel](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.Grid.ResourceCellModel.html)'| markdownify }}</td>
<td>{{'[GridCellModel(ResourceCellRenderer)](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Grid.GridCellModel-1.html)'| markdownify }}</td>
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
<th>Property type</th>
<th>Property name</th>
</tr>

<tr>
<td>{{'[GanttControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttControl.html)'| markdownify }}</td>
<td>{{'[VisualStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.VisualStyle.html)'| markdownify }}</td>
<td>{{'[VisualStyle](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Gantt.GanttControl.html#Syncfusion_Windows_Controls_Gantt_GanttControl_VisualStyle)'| markdownify }}</td>
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