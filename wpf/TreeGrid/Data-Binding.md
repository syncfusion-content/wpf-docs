---
layout: post
title: Data Binding in WPF TreeGrid control | Syncfusion
description: Learn here all about Data Binding support in Syncfusion WPF TreeGrid (SfTreeGrid) control, its elements and more.
platform: wpf
control: SfTreeGrid
documentation: ug
---

# Data Binding in WPF TreeGrid (SfTreeGrid)

SfTreeGrid is designed to display the self-relational and hierarchical data in tree structure with columns. The data binding can be achieved by assigning the data source to [SfTreeGrid.ItemsSource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ItemsSource) property directly through self-relational binding or nested collection or retrieving the parent and child nodes items dynamically using [RequestTreeItems](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) or [LoadOnDemandCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_LoadOnDemandCommand).
If the data source implements [INotifyCollectionChanged](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.inotifycollectionchanged?redirectedfrom=MSDN&view=net-5.0) interface, then SfTreeGrid control will automatically refresh the UI when item is added, removed or while list cleared. When you add, remove item in[ObservableCollection](https://docs.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.observablecollection-1?redirectedfrom=MSDN&view=net-5.0)`, SfTreeGrid automatically refresh the UI as `ObservableCollection’ implements `INotifyCollectionChanged`. But when you do the same in [List](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1?redirectedfrom=MSDN&view=net-5.0), SfTreeGrid will not refresh the UI automatically.

Below are the ways to bind the data source to SfTreeGrid.

* [Populate data using self-relational binding](https://help.syncfusion.com/wpf/treegrid/getting-started#binding-self-relational-data-in-sftreegrid)
* [Populate data using nested collection](https://help.syncfusion.com/wpf/treegrid/getting-started#binding-nested-collection-with-sftreegrid)
* [Populate data with `RequestTreeItems` event](https://help.syncfusion.com/wpf/treegrid/load-on-demand#using-requesttreeitems-event)
* [Populate data with `LoadOnDemandCommand`](https://help.syncfusion.com/wpf/treegrid/load-on-demand#using-loadondemandcommand)

## Binding with IEnumerable

SfTreeGrid control supports to bind any collection that implements the [IEnumerable](https://docs.microsoft.com/en-us/dotnet/api/system.collections.ienumerable?redirectedfrom=MSDN&view=net-5.0) interface. Data operations such as sorting is supported when you are binding collection derived from `IEnumerable`.

## Binding with dynamic data object

SfTreeGrid control supports to bind [dynamic data object](https://docs.microsoft.com/en-us/dotnet/api/system.dynamic?redirectedfrom=MSDN&view=net-5.0). Below are the limitations when you are binding dynamic data object,

1. In UWP, UI won’t get refreshed when you are changing the property value. This is limitation in UWP platform.
2. SfTreeGrid doesn’t support [LiveNodeUpdateMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_LiveNodeUpdateMode) - `AllowDataShaping`.

## Binding Complex properties

SfTreeGrid control provides support to bind complex property to its columns. To bind the complex property to `TreeGridColumn`, set the complex property path to `MappingName`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid x:Name="treeGrid"
                       ChildPropertyName="Children"
                       ItemsSource="{Binding PersonDetails}"
                       ShowRowHeader="True">
            <syncfusion:SfTreeGrid.Columns>
                <syncfusion:TreeGridColumns>
                    <syncfusion:TreeGridTextColumn MappingName="FirstName" />
                    <syncfusion:TreeGridTextColumn MappingName="Address.City" />
                    <syncfusion:TreeGridTextColumn MappingName="Address.Country" />
                </syncfusion:TreeGridColumns>
            </syncfusion:SfTreeGrid.Columns>
 </syncfusion:SfTreeGrid>
{% endhighlight %}
{% endtabs %}

**Limitations when binding complex property:**

SfTreeGrid doesn’t support [LiveNodeUpdateMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_LiveNodeUpdateMode)  - `AllowDataShaping`.

## Binding Indexer properties

SfTreeGrid control provides support to bind an indexer property to its columns. To bind an indexer property to `TreeGridColumn`, set the indexer property path to `MappingName`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid x:Name="treeGrid"
                       AutoGenerateColumns="False"
                       ItemsSource="{Binding Students}">
            <syncfusion:SfTreeGrid.Columns>
                <syncfusion:TreeGridTextColumn MappingName="RollNo" />
                <syncfusion:TreeGridTextColumn MappingName="Name" />
                <syncfusion:TreeGridTextColumn MappingName="Marks[0]" />
            </syncfusion:SfTreeGrid.Columns>
</syncfusion:SfTreeGrid>
{% endhighlight %}
{% highlight c# %}
this.treeGrid.Columns.Add(new TreeGridTextColumn() {MappingName="Marks[0]"}); 
{% endhighlight %}
{% endtabs %}

**Limitations when binding complex property:**

SfTreeGrid doesn’t support  [LiveNodeUpdateMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_LiveNodeUpdateMode) - `AllowDataShaping`.

## AutoExpandMode

By setting [SfTreeGrid.AutoExpandMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_AutoExpandMode) property, you can let the SfTreeGrid to expand the nodes while loading.

<table>
<tr>
<td>
{{'**Mode**'| markdownify }}
</td>
<td>
{{'**Description**'| markdownify }}
</td>
</tr>
<tr>
<td>
AllNodesExpanded
</td>
<td>
All the nodes will be expanded while at the time of loading.
</td>
</tr>
<tr>
<td>
None
</td>
<td>
None defines the node is not expanded when loading. By default, root nodes only will be displayed.
</td>
</tr>
<tr>
<td>
RootNodeExpanded
</td>
<td>
Root nodes only will be expanded at the time of loading.
</td>
</tr>
</table>

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                       AutoExpandMode="AllNodesExpanded"
                       AutoGenerateColumns="False"
                       ChildPropertyName="ReportsTo"
                       ItemsSource="{Binding Employees}"
                       ParentPropertyName="ID"/>
{% endhighlight %}
{% highlight c# %}
treeGrid.AutoExpandMode = AutoExpandMode.AllNodesExpanded;
{% endhighlight %}
{% endtabs %}

## Expanding a tree node

You can expand a node based on its level or row index. Here is a list of ways to expand a node,

<table>
<tr>
<td>
{{'**Method**'| markdownify }}
</td>
<td>
{{'**Description**'| markdownify }}
</td>
</tr>
<tr>
<td>
{{'[ExpandAllNodes()](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ExpandAllNodes)'| markdownify }}
</td>
<td>
Expands all the nodes including its inner leaf nodes
</td>
</tr>
<tr>
<td>
{{'[ExpandAllNodes(int level)](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ExpandAllNodes_System_Int32_)'| markdownify }}
</td>
<td>
Expand all the nodes up to the specified level 
</td>
</tr>
<tr>
<td>
{{'[ExpandAllNodes(TreeNode treeNode)](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ExpandAllNodes_Syncfusion_UI_Xaml_TreeGrid_TreeNode_)'| markdownify }}
</td>
<td>
Expand the specific node and its child nodes
</td>
</tr>
<tr>
<td>
{{'[ExpandNode(int rowIndex)](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ExpandNode_System_Int32_)'| markdownify }}
</td>
<td>
Expand a node at the specific row Index
</td>
</tr>
<tr>
<td>
{{'[ExpandNode(TreeNode treeNode)](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ExpandNode_Syncfusion_UI_Xaml_TreeGrid_TreeNode_)'| markdownify }}
</td>
<td>
Expands the specific node.
</td>
</tr>
</table>

### Expand all the nodes

You can expand all the nodes programmatically at runtime by using [SfTreeGrid.ExpandAllNodes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ExpandAllNodes) method.

{% tabs %}
{% highlight c# %}
treeGrid.ExpandAllNodes();
{% endhighlight %}
{% endtabs %}

### Expand the nodes based on its level

You can expand the nodes based on the level by using [SfTreeGrid.ExpandAllNodes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ExpandAllNodes_System_Int32_) method by passing level as argument.

{% tabs %}
{% highlight c# %}
treeGrid.ExpandAllNodes(1);
{% endhighlight %}
{% endtabs %}

### Expand the specific node

You can expand the specific node by using [SfTreeGrid.ExpandNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ExpandNode_Syncfusion_UI_Xaml_TreeGrid_TreeNode_) method.

{% tabs %}
{% highlight c# %}
var node = treeGrid.View.Nodes[0];
treeGrid.ExpandNode(node);  
{% endhighlight %}
{% endtabs %}

You can expand the node at specific index also by using [SfTreeGrid.ExpandNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ExpandNode_System_Int32_) method.

{% tabs %}
{% highlight c# %}
treeGrid.ExpandNode(2);
{% endhighlight %}
{% endtabs %}

### Expand the specific node based on business object

You can expand the node corresponding to specific data object by resolving node and calling [SfTreeGrid.ExpandNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ExpandNode_Syncfusion_UI_Xaml_TreeGrid_TreeNode_) method.

{% tabs %}
{% highlight c# %}
var data = (this.DataContext as ViewModel).PersonDetails[0];
var node = this.treeGrid.View.Nodes.GetNode(data);
treeGrid.ExpandNode(node);
{% endhighlight %}
{% endtabs %}

### Expand all the nodes

You can expand the specific node and all its child nodes by using [SfTreeGrid.ExpandAllNodes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ExpandAllNodes_Syncfusion_UI_Xaml_TreeGrid_TreeNode_) methods.

{% tabs %}
{% highlight c# %}
var node = treeGrid.View.Nodes[0];
treeGrid.ExpandAllNodes(node);
{% endhighlight %}
{% endtabs %}

### Cancel the node Expanding using NodeExpanding event

You can cancel the node expanding through [SfTreeGrid.NodeExpanding](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event.

{% tabs %}
{% highlight c# %}
treeGrid.NodeExpanding += TreeGrid_NodeExpanding;

private void TreeGrid_NodeExpanding(object sender, NodeExpandingEventArgs e)
{
    e.Cancel = true;    
}
{% endhighlight %}
{% endtabs %}

You can cancel the specific node being expanded by using `SfTreeGrid.NodeExpanding` event and `Node` property,

{% tabs %}
{% highlight c# %}
treeGrid.NodeExpanding += TreeGrid_NodeExpanding;

private void TreeGrid_NodeExpanding(object sender, NodeExpandingEventArgs e)
{

    if ((e.Node.Item as EmployeeInfo).ID == 2)
        e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

### NodeExpanded Event

You can get the notification once a node is expanded from [TreeGrid.NodeExpanded](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event and here you can get the expanded node and its child nodes.

{% tabs %}
{% highlight c# %}
private void TreeGrid_NodeExpanded(object sender, NodeExpandedEventArgs e)
{
    var node = e.Node;
    var childNodes = e.Node.ChildNodes;
}
{% endhighlight %}
{% endtabs %}

## Collapsing a tree node

You can collapse all the tree nodes or specific node and its child nodes. Here is a list of ways to collapse a node,

<table>
<tr>
<td>
{{'**Method**'| markdownify }}
</td>
<td>
{{'**Description**'| markdownify }}
</td>
</tr>
<tr>
<td>
{{'[CollapseAllNodes()](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_CollapseAllNodes)'| markdownify }}
</td>
<td>
Collapse all the nodes in SfTreeGrid
</td>
</tr>
<tr>
<td>
{{'[CollapseAllNodes(TreeNode treeNode)](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_CollapseAllNodes_Syncfusion_UI_Xaml_TreeGrid_TreeNode_)'| markdownify }}
</td>
<td>
Collapse the specific node and its child nodes
</td>
</tr>
<tr>
<td>
{{'[CollapseNode(int rowIndex)](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_CollapseNode_System_Int32_)'| markdownify }}
</td>
<td>
Collapse the node at specific row index
</td>
</tr>
<tr>
<td>
{{'[CollapseNode(TreeNode treeNode)](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_CollapseNode_Syncfusion_UI_Xaml_TreeGrid_TreeNode_)'| markdownify }}
</td>
<td>
Collapse the specific node in SfTreeGrid
</td>
</tr>
</table>

### Collapse all the nodes

You can collapse all the nodes programmatically at runtime by using [SfTreeGrid.CollapseAllNodes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_CollapseAllNodes) methods

{% tabs %}
{% highlight c# %}
treeGrid.CollapseAllNodes();
{% endhighlight %}
{% endtabs %}

### Collapse the specific node

You can collapse the specific node by using [SfTreeGrid.CollapseNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_CollapseNode_Syncfusion_UI_Xaml_TreeGrid_TreeNode_) method.

{% tabs %}
{% highlight c# %}
var node = treeGrid.View.Nodes[0];
treeGrid.CollapseNode(node); 
{% endhighlight %}
{% endtabs %}

You can collapse the node at specific index also by using [SfTreeGrid.CollapseNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_CollapseNode_System_Int32_) method.

{% tabs %}
{% highlight c# %}
treeGrid.CollapseNode(2);
{% endhighlight %}
{% endtabs %}

### Collapse the specific node based on business object

You can collapse the node corresponding to specific data object by resolving node and calling [SfTreeGrid.CollapseNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_CollapseNode_Syncfusion_UI_Xaml_TreeGrid_TreeNode_) method.

{% tabs %}
{% highlight c# %}
var data = (this.DataContext as ViewModel).PersonDetails[0];
var node = this.treeGrid.View.Nodes.GetNode(data);
treeGrid.CollapseNode(node);
{% endhighlight %}
{% endtabs %}

### Collapse all the nodes

You can collapse the specific node and all its child nodes by using [SfTreeGrid.CollapseAllNodes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_CollapseAllNodes_Syncfusion_UI_Xaml_TreeGrid_TreeNode_) methods.

{% tabs %}
{% highlight c# %}
var node = treeGrid.View.Nodes[0];
treeGrid.CollapseAllNodes(node);
{% endhighlight %}
{% endtabs %}

### Cancel the node collapsing using NodeCollapsing Event

You can cancel the node collapsing operation through [TreeGrid.NodeCollapsing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event.

{% tabs %}
{% highlight c# %}
treeGrid.NodeCollapsing += TreeGrid_NodeCollapsing;

private void TreeGrid_NodeCollapsing(object sender, NodeCollapsingEventArgs e)
{
    e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

You can cancel the specific node being collapsed by using `TreeGrid.NodeCollapsing` event.

{% tabs %}
{% highlight c# %}
treeGrid.NodeCollapsing += TreeGrid_NodeCollapsing;

private void TreeGrid_NodeCollapsing(object sender, NodeCollapsingEventArgs e)
{

    if ((e.Node.Item as EmployeeInfo).ID == 2)
        e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

### NodeCollapsed Event

You can get the notification once a node is collapsed from [TreeGrid.NodeCollapsed](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event and here you can get the collapsed node.

{% tabs %}
{% highlight c# %}
treeGrid.NodeCollapsed += TreeGrid_NodeCollapsed;

private void TreeGrid_NodeCollapsed(object sender, NodeCollapsedEventArgs e)
{
    var node = e.Node;
}
{% endhighlight %}
{% endtabs %}

## Expand/Collapse a node based on mapping property

SfTreeGrid supports to expand/collapse the nodes based on the value of a boolean mapping property in the underlying data object by using [SfTreeGrid.ExpandStateMappingName](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ExpandStateMappingName) property. TreeGrid expand/collapse the node when the specified property value in underlying data object gets changed.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid Name="treeGrid"
                       ExpandStateMappingName="IsExpanded"
                       ChildPropertyName="Children"
                       ItemsSource="{Binding PersonDetails}"
                       ShowCheckBox="True"/>
{% endhighlight %}
{% highlight c# %}
treeGrid.ExpandStateMappingName = "IsExpanded";
{% endhighlight %}
{% endtabs %}

## LiveNodeUpdateMode

SfTreeGrid listens and responds to the manipulation such as add, delete and data update (property change) at runtime. SfTreeGrid refreshes the sorting based on [SfTreeGrid.LiveNodeUpdateMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_LiveNodeUpdateMode) property. If you set `LiveNodeUpdateMode` as `AllowDataShaping`, sorting will be refreshed on data manipulation and property change.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeGrid  Name="treeGrid"
                        AllowEditing="True"
                        AutoExpandMode="RootNodesExpanded"
                        LiveNodeUpdateMode="AllowDataShaping"
                        AutoGenerateColumns="False"
                        ChildPropertyName="ReportsTo"
                        ItemsSource="{Binding Employees}"
                        ParentPropertyName="ID"/>
{% endhighlight %}
{% highlight c# %}
treeGrid.LiveNodeUpdateMode = LiveNodeUpdateMode.AllowDataShaping;
{% endhighlight %}
{% endtabs %}

## Events

### ItemsSourceChanged

[SfTreeGrid.ItemsSourceChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html) event occurs when the data source is changed by using [ItemsSource](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_ItemsSource) property.

This event receives two arguments namely sender that handles SfTreeGrid and `GridItemsSourceChangedEventArgs` as objects.
The `GridItemsSourceChangedEventArgs` object contains the following properties:

* `OldItemsSource` - Gets the value of old data source
* `NewItemsSource` - Get the value of new data source

## View

SfTreeGrid has the [View](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.SfTreeGrid.html#Syncfusion_UI_Xaml_TreeGrid_SfTreeGrid_View) property of type [TreeGridView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridView.html). `View` is responsible for maintaining and manipulating the nodes and other advanced operations like Sorting. When you bind Collection to `ItemsSource` property of SfTreeGrid or wire `RequestTreeItems` event, then `View` will be created and maintains the operations on nodes.

SfTreeGrid creates different types of views derived from TreeGridView based on data population methods.

[TreeGridSelfRelationalView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridSelfRelationalView.html) -  While populating data using self-relational binding

[TreeGridNestedView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridNestedView.html)             -  While populating data using nested collection

[TreeGridUnboundView](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeGridUnboundView.html)         -  While populating data with `RequestTreeItems` event or `LoadOnDemandCommand` command

### Events

The following events are associated with View.

#### RecordPropertyChanged

This event is raised when the DataModel property value is changed, if the DataModel implements the [INotifyPropertyChanged](https://docs.microsoft.com/en-us/dotnet/api/system.collections.specialized.inotifycollectionchanged?redirectedfrom=MSDN&view=net-5.0) interface. The event receives with two arguments namely `sender` that handles the DataModel and `PropertyChangedEventArgs` as object.

`PropertyChangedEventArgs` has below property,

`PropertyName` – It denotes the PropertyName of the changed value.

#### NodeCollectionChanged

This event is raised whenever there is some change in nodes collection. The event receives two arguments namely sender that handles View object and `NotifyCollectionChangedEventArgs` as object.
`NotifyCollectionChangedEventArgs` has below properties,

* `Action` - It contains the current action. (i.e.) Add, Remove, Move, Replace, Reset.
* `NewItems` - It contains the list of new items involved in the change.
* `OldItems` - It contains the list of old items affected by the Action.
* `NewStartingIndex` - It contains the index at which the change occurred.
* `OldStartingIndex` - It contains the index at which the Action occurred.

#### SourceCollectionChanged

This event is raised when you make changes in `SourceCollection` for example add or remove the collection. The event receives two arguments namely sender that handles that handles View object and `NotifyCollectionChangedEventArgs` as object.
`NotifyCollectionChangedEventArgs` has below properties,

* `Action` - It contains the current action. (i.e) Add, Remove, Move, Replace, Reset.
* `NewItems` - It contains the list of new items involved in the change.
* `OldItems` - It contains the list of old items affected by the Action.
* `NewStartingIndex` - It contains the index at which the change occurred.
* `OldStartingIndex`- It contains the index at which the Action occurred.

### Methods

The following are the methods that are associated with `View` which can be used to defer refresh the view.

**DeferRefresh**

Enter the defer cycle so that you can perform all data operations in view and update once. You can refresh the nodes or completely recreates the nodes by using [TreeViewRefreshMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeViewRefreshMode.html) parameter.

{% tabs %}
{% highlight c# %}
using (treeGrid.View.DeferRefresh(TreeViewRefreshMode.NodeRefresh))
{
    treeGrid.SortColumnDescriptions.Add(new SortColumnDescription() { ColumnName = "FirstName", SortDirection = ListSortDirection.Descending });
    treeGrid.SortColumnDescriptions.Add(new SortColumnDescription() { ColumnName = "Id", SortDirection = ListSortDirection.Descending });
}
{% endhighlight %}
{% endtabs %}

**BeginInit and EndInit**

When &lt;code&gt;BeginInit&lt;/code&gt; method is called, it suspends all the updates until &lt;code&gt;EndInit&lt;/code&gt; method is called. You can perform all the update with in these methods and update the view at once. You can refresh the nodes or completely recreates the nodes by using [TreeViewRefreshMode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeGrid.TreeViewRefreshMode.html) parameter.

{% tabs %}
{% highlight c# %}
treeGrid.View.BeginInit(TreeViewRefreshMode.DeferRefresh);
treeGrid.SortColumnDescriptions.Add(new SortColumnDescription() { ColumnName = "FirstName", SortDirection = ListSortDirection.Descending });
treeGrid.SortColumnDescriptions.Add(new SortColumnDescription() { ColumnName = "Id", SortDirection = ListSortDirection.Descending });
treeGrid.View.EndInit();
{% endhighlight %}
{% endtabs %}

N> View has properties (`EnableRecursiveChecking`, `LiveNodeUpdateMode` , `RecursiveCheckingMode`,..)that already defined in SfTreeGrid. It is recommended to set those properties via SfTreeGrid.


N> You can refer to our [WPF TreeGrid](https://www.syncfusion.com/wpf-controls/treegrid) feature tour page for its groundbreaking feature representations. You can also explore our [WPF TreeGrid example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the treegrid.