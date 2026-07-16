---
layout: post
title: CRUD Operations in WPF TreeView control | Syncfusion®
description: Learn here all about CRUD Operations support in Syncfusion® WPF TreeView (SfTreeView) control and more.
platform: wpf
control: SfTreeView
documentation: ug
---

# CRUD Operations in WPF TreeView (SfTreeView)

TreeView listens to and responds to CRUD operations such as add, delete, and data update (property change) at runtime. It also supports [editing](https://help.syncfusion.com/wpf/treeview/editing) and deleting by pressing the <kbd>Delete</kbd> key.

## Add nodes

The TreeView allows users to add a new node directly by adding a new data object to the underlying collection in bound mode, and by adding a [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) to the [Nodes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_Nodes) collection in unbound mode.

{% tabs %}
{% highlight c# %}
// For bound mode
(sfTreeView.DataContext as ViewModel).Countries.Add(new Country() { Name = "Germany"});

// For Unbound mode
sfTreeView.Nodes.Add(new TreeViewNode(){ Content = "Germany" });
{% endhighlight %}
{% endtabs %}

## Delete nodes

The TreeView provides built-in support to delete the selected nodes in the user interface (UI) by pressing the <kbd>Delete</kbd> key. You can enable delete support by setting the [SfTreeView.AllowDeleting](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_AllowDeleting) property to `true`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView  
                x:Name="sfTreeView" 
				AllowDeleting="True"
				ChildPropertyName="States"
                ItemsSource="{Binding Countries}"/>
{% endhighlight %}
{% highlight c# %}
sfTreeView.AllowDeleting = true;
{% endhighlight %}
{% endtabs %}

You can also delete a node directly in the underlying collection by using `Remove()` or `RemoveAt(int index)`.

{% tabs %}
{% highlight c# %}

//For Bound mode
(sfTreeView.DataContext as ViewModel).Countries.Remove(sfTreeView.SelectedItem as Country);

// OR
(sfTreeView.DataContext as ViewModel).Orders.RemoveAt(2);

// For Unbound mode
sfTreeView.Nodes.Remove(sfTreeView.Nodes[0]);

//OR
sfTreeView.Nodes.RemoveAt(2);
{% endhighlight %}
{% endtabs %}

### Event customization

#### Delete selected nodes conditionally

You can cancel the node deletion by using `ItemDeletingEventArgs.Cancel` of the [ItemDeleting](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ItemDeleting) event. This event occurs when a node is being deleted using the <kbd>Delete</kbd> key. You can skip certain nodes when deleting more than one node by removing items from [ItemDeletingEventArgs.Nodes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.ItemDeletingEventArgs.html#Syncfusion_UI_Xaml_TreeView_ItemDeletingEventArgs_Nodes).

{% tabs %}
{% highlight c# %}
sfTreeView.ItemDeleting += TreeView_ItemDeleting;

private void TreeView_ItemDeleting (object sender, ItemDeletingEventArgs e)
{
    var nodeCollection = e.Nodes.ToList();
    foreach (var node in nodeCollection)
    {
        var country = node.Content as Country;
        if (country != null)
        {
            if (country.Name == "Brazil")
                e.Cancel = true;
            else if (country.Name == "India")
                e.Nodes.Remove(node);
        }        
    }
}
{% endhighlight %}
{% endtabs %}


#### Reset selection after deleting the selected node

You can handle the selection after removing the nodes through the [SfTreeView.SelectedItem](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_SelectedItem) property in the [ItemDeleted](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ItemDeleted) event. This event occurs after a node is deleted using the <kbd>Delete</kbd> key.

{% tabs %}
{% highlight c# %}
sfTreeView.ItemDeleted += TreeView_ItemDeleted;

private void TreeView_ItemDeleted (object sender, ItemDeletedEventArgs e)
{
    if(sfTreeView.Nodes.Count > 0)
    {
        sfTreeView.SelectedItem = sfTreeView.Nodes[0].Content;
    }
}
{% endhighlight %}
{% endtabs %}

## Modify nodes

The TreeView allows users to modify the data in a node by [editing](https://help.syncfusion.com/wpf/treeview/editing).

N> You can refer to our [WPF TreeView](https://www.syncfusion.com/wpf-controls/treeview) feature tour page for its key feature highlights. You can also explore our [WPF TreeView example](https://github.com/syncfusion/wpf-demos) to know how to represent hierarchical data in a tree-like structure with expand and collapse node options.