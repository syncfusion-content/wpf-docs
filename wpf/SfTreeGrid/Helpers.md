---
layout: post
title: Helpers | SfTreeGrid | WPF | Syncfusion
description: This section describes about the index resolver class for getting the row/column/node indexes and Dispose method of TreeGrid.
platform: wpf
control: SfTreeGrid
documentation: ug
---

# Helpers

## IndexResolver

SfTreeGrid has [TreeGridIndexResolver](https://help.syncfusion.com/cr/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridIndexResolver.html) static class present in Syncfusion.UI.Xaml.TreeGrid namespace that has some extension methods used to resolve from row or column index to node or visible column index and vice versa.

For example, You can get a node from its row index using [GetNodeAtRowIndex](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.TreeGridIndexResolver~GetNodeAtRowIndex.html) method.

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
Resolves node index from the row index. When row index does not find any records, it returns -1. NodeIndex denotes the index of node in SfTreeGrid.View.Nodes.

</td>
</tr>
<tr>
<td>
ResolveToRowIndex(int nodeIndex)

</td>
<td>
Resolves row index from the node index associated with SfTreeGrid.View.Nodes. When node index is lesser than 0 it returns the -1.
</td>
</tr>
<tr>
<td>
ResolveToRowIndex(object data)

</td>
<td>
Resolves row index from the data associated with SfTreeGrid.View.Nodes. When the given node is not available in the collection it returns -1.
</td>
</tr>
<tr>
<td>
ResolveToRowIndex(TreeNode node)

</td>
<td>
Resolves row index from the node associated with SfTreeGrid.View.Nodes. When the given node is not available in the collection it returns -1.
</td>
</tr>
<tr>
<td>
ResolveToGridVisibleColumnIndex(int columnIndex)

</td>
<td>
Resolves the TreeGridColumn index from the visible column index. It excludes the RowHeader and IndentColumn.
</td>
</tr>
<tr>
<td>
ResolveToScrollColumnIndex(int gridColumnIndex)

</td>
<td>
Resolves column index from the Grid column index associated with SfTreeGrid.Columns. It includes the IndentColumn and RowHeader also.
</td>
</tr>
<tr>
<td>
ResolveToStartColumnIndex()

</td>
<td>
Returns start column index of the VisibleColumn.

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
Gets the tree node based on the row index
</td>
</tr>
</table>

## Dispose

This method is associated with relinquishes memory and clears all references associated with the treegrid. When you call this method, it releases all the reference for the treegrid. So, the memory it is occupying using the treegrid is reclaimed. You have to call [SfTreeGrid.Dispose](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid~Dispose.html) method to release the memory.
