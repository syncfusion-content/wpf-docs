---
layout: post
title: Helpers in WPF TreeGrid control | Syncfusion®
description: Learn here all about Helpers support in Syncfusion® WPF TreeGrid (SfTreeGrid) control, its elements and more.
platform: wpf
control: SfTreeGrid
documentation: ug
---

# Helpers in WPF TreeGrid (SfTreeGrid)

## IndexResolver

SfTreeGrid has [TreeGridIndexResolver](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridIndexResolver.html) static class present in the Syncfusion.UI.Xaml.TreeGrid namespace has some extension methods to resolve from row or column index to node or visible column index and vice-versa.

For example, you can get a node from its row index using the [GetNodeAtRowIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridIndexResolver.html#Syncfusion_UI_Xaml_TreeGrid_TreeGridIndexResolver_GetNodeAtRowIndex_Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_System_Int32_) method.

{% tabs %}
{% highlight c# %}

treeGrid.GetNodeAtRowIndex(3);

{% endhighlight %}
{% endtabs %}

## Prototype table
<table>
<tr>
<td>
{{'**Prototype**'| markdownify }}
</td>
<td>
{{'**Description**'| markdownify }}
</td>
</tr>
<tr>
<td>
ResolveToNodeIndex(int rowindex)

</td>
<td>
Resolves the node index from the row index. When row index does not find any record, it returns -1. The NodeIndex denotes the index of node in SfTreeGrid.View.Nodes.

</td>
</tr>
<tr>
<td>
ResolveToRowIndex(int nodeIndex)

</td>
<td>
Resolves the row index from the node index associated with SfTreeGrid.View.Nodes. When node index is lesser than 0 it returns -1.
</td>
</tr>
<tr>
<td>
ResolveToRowIndex(object data)

</td>
<td>
Resolves the row index from the data associated with SfTreeGrid.View.Nodes. When the given node is not available in the collection, it returns -1.
</td>
</tr>
<tr>
<td>
ResolveToRowIndex(TreeNode node)

</td>
<td>
Resolves the row index from the node associated with SfTreeGrid.View.Nodes. When the given node is not available in the collection, it returns -1.
</td>
</tr>
<tr>
<td>
ResolveToGridVisibleColumnIndex(int columnIndex)

</td>
<td>
Resolves the TreeGridColumn index from the visible column index. It excludes row header and indent column.
</td>
</tr>
<tr>
<td>
ResolveToScrollColumnIndex(int gridColumnIndex)

</td>
<td>
Resolves column index from the grid column index associated with SfTreeGrid.Columns. It also includes the indent column and row header also.
</td>
</tr>
<tr>
<td>
ResolveToStartColumnIndex()

</td>
<td>
Returns the start column index of the VisibleColumn.

</td>
</tr>
<tr>
<td>
GetHeaderIndex()

</td>
<td>
Returns the header row index.
</td>
</tr>
<tr>
<td>
GetNodeAtRowIndex(int rowIndex)

</td>
<td>
Gets the tree node based on the row index.
</td>
</tr>
</table>

## Dispose

This method is associated with relinquishes memory and clears all references associated with treegrid. When you call this method, it releases all references for treegrid. So, the memory occupied using treegrid is reclaimed. You should call the [SfTreeGrid.Dispose](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_Dispose_System_Boolean_) method to release the memory.


N> You can refer to our [WPF TreeGrid](https://www.syncfusion.com/wpf-controls/treegrid) feature tour page for its groundbreaking feature representations. You can also explore our [WPF TreeGrid example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the treegrid.