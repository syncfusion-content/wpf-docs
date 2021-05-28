---
layout: post
title: GridTree Control Properties in WPF Wizard Control control | Syncfusion
description: Learn here all about GridTree Control Properties support in Syncfusion WPF GridTreeControl (Classic) control and more.
platform: wpf
control: GridTree 
 documentation: ug
---

# GridTree Control Properties in WPF GridTreeControl (Classic)

The GridTree control has the following properties that allow you to control much of the behavior available within the control. Here is a list of these properties along with some discussion of each. 



<table>
<tr>
<th>
GridTree control Property</th><th>
Description</th><th>
Type of Property</th><th>
Value It Accepts</th><th>
Property Syntax</th></tr>
<tr>
<td>
AllowAutoSizingNodeColumn</td><td>
Controls whether the width of the ExpandCell is automatically adjusted as more levels are exposed. This property setting is ignored if PercentageSizing is enabled and you have the ExpandCell column marked to participate in the percentage sizing calculations.</td><td>
DependencyProperty</td><td>
bool</td><td>
treeGrid.AllowAutoSizingNodeColumn</td></tr>
<tr>
<td>
AllowDragColumns</td><td>
Controls whether your user can rearrange the columns by moving the mouse down on the header cell and drag it to another location in the control.</td><td>
Dependency property</td><td>
bool</td><td>
treeGrid.AllowDragColumns</td></tr>
<tr>
<td>
AllowSort</td><td>
Controls whether your user can sort columns by clicking the column header. When enabled, holding down the Ctrl key and clicking the columns will allow sorting on multiple columns. All sorting is done within the child lists.</td><td>
Dependency property</td><td>
bool</td><td>
treeGrid.AllowSort</td></tr>
<tr>
<td>
ColumnHeaderStyle</td><td>
A GridStyleInfo object that controls the appearance of the column headers.</td><td>
Dependency property</td><td>
GridStyleInfo</td><td>
treeGrid.ColumnHeaderStyle = new GridStyleInfo() { };</td></tr>
<tr>
<td>
DefaultColumnWidth</td><td>
Provides the default settings for the column width used in the GridTree control.</td><td>
Dependency property</td><td>
Double</td><td>
treeGrid.DefaultColumnWidth</td></tr>
<tr>
<td>
EnableHotRowMarker</td><td>
Controls whether the row under the mouse is overdrawn with a special background brush so that the user can easily see the row under the mouse. The brush can be specified using the GridTreeControl.InternalGrid.markRowBrush property.</td><td>
Dependency property</td><td>
bool</td><td>
treeGrid. EnableHotRowMarker</td></tr>
<tr>
<td>
EnableSelections</td><td>
Controls whether selections are supported. The GridTree control support two types of selections, node selections and cell selections. Use the EnableNodeSelection property to determine which selection type is active.</td><td>
Dependency property</td><td>
bool</td><td>
treeGrid.EnableSelections</td></tr>
<tr>
<td>
EnableNodeSelection</td><td>
Controls whether all the rows will be selected when a single row is clicked. When enabled, you can select multiple rows by holding the Shift key and dragging the mouse. When not enabled, the cell ranges will be selected.</td><td>
Dependency property</td><td>
bool</td><td>
treeGrid.EnableNodeSelection</td></tr>
<tr>
<td>
HideEmptyChildGlyphs</td><td>
Controls whether you can possibly see the expand glyph on a node with no children. The default value is true that indicates glyphs on empty nodes will be hidden when initially displayed. In order to support this behavior, the GridTree control must request the child nodes at the time the parent node is expanded (instead of at the time the child node is clicked to be expanded).</td><td>
Dependency property</td><td>
bool</td><td>
treeGrid.HideEmptyChildGlyphs</td></tr>
<tr>
<td>
InternalGrid</td><td>
Gets a reference to the GridControlImpl object associated with this GridTree control. This property will be null until the ModelLoaded event is raised by the GridTree control. ModeLoaded event is triggered once the grid model is loaded.</td><td>
Normal</td><td>
GridTreeControl</td><td>
treeGrid.InternalGrid</td></tr>
<tr>
<td>
LevelStyles</td><td>
A List<GridStyleInfo> object that holds GridStyleInfo objects that will control the look of cells for a given tree level. The 0th GridStyleInfo will be applied to all root node rows, the 1st GridStyleInfo will be applied to level 1 rows, etc. </td><td>
Dependency property</td><td>
List<GridStyleInfo></td><td>
treeGrid.LevelStyles</td></tr>
<tr>
<td>
Model</td><td>
Gives access to the GridTreeModel object associated with this GridTree control. The Model.Options property gives access to the properties that control the behavior of the InternalGrid object associated with this GridTree control. </td><td>
Normal</td><td>
GridTreeModel</td><td>
treeGrid.Model</td></tr>
<tr>
<td>
ReadOnly</td><td>
Determines whether the cells in the GridTree control can be edited. This is a GridTree control-wide setting. You can use the LevelStyles[].StyleInfo.ReadOnly to edit the particular levels. Additionally, you can use Columns[].StyleInfo.ReadOnly to control the edit operation, column-by-column. Finally, you can use the Model.QueryCellInfo event to set ReadOnly properties cell-by-cell in an on-demand manner.</td><td>
Dependency property</td><td>
bool</td><td>
treeGrid.ReadOnly</td></tr>
<tr>
<td>
RowHeaderWidth</td><td>
Specifies the width of the row header column if it is visible. To control the visibility, use the ShowRowHeader property.</td><td>
Dependency property</td><td>
Double</td><td>
treeGrid.RowHeaderWidth</td></tr>
<tr>
<td>
SelectedNodes</td><td>
A collection of nodes selected in the GridTree control. The items in the collection are GridTreeNode objects.</td><td>
Normal</td><td>
GridSelectedTreeNodes</td><td>
treeGrid.SelectedNodes</td></tr>
<tr>
<td>
ShowColumnHeaders</td><td>
Determines whether the column header row is visible.</td><td>
Dependency property</td><td>
bool</td><td>
treeGrid.ShowColumnHeaders</td></tr>
<tr>
<td>
ShowExpandColumnBorders</td><td>
Determines whether the GridTree control display cell borders for the Expand column.</td><td>
Dependency property</td><td>
bool</td><td>
treeGrid.ShowExpandColumnBorders</td></tr>
<tr>
<td>
ShowRowHeader</td><td>
Determines whether the row header column is visible.</td><td>
Dependency property</td><td>
bool</td><td>
treeGrid.ShowRowHeader</td></tr>
<tr>
<td>
SupportRowSizing</td><td>
Determines whether the user can change the row heights using the mouse.</td><td>
Dependency property</td><td>
bool</td><td>
treeGrid.SupportRowSizing</td></tr>
<tr>
<td>
SupportsVisualStyles</td><td>
Determines whether the GridTree control will use the VisualStyle property to control the appearance of the GridTree control. If this property is {{ '_true_' | markdownify }}, you can directly set the VisualStyle property for the grid. You also have the option of applying the changes through the SkinManager found in the Syncfusion.Shared.WPF library. The GridTree control is bound to the SkinManager values through its Template.</td><td>
Dependency property</td><td>
bool</td><td>
treeGrid.SupportsVisualStyle</td></tr>
<tr>
<td>
VisualStyle</td><td>
Determines the VisualStyle that is applied to the GridTree control when SupportsVisualStyles property is set to {{ '_true_' | markdownify }}.</td><td>
Dependency property</td><td>
VisualStyle</td><td>
treeGrid.VisualStyle</td></tr>
</table>


