---
layout: post
title: CRUD Operations with WPF TreeView control | Syncfusion
description: Learn about CRUD operations to manipulate the data in Syncfusion WPF TreeView (SfTreeView) control and more details.
platform: wpf
control: SfTreeView
documentation: ug
---

# CRUD operations in WPF TreeView (SfTreeView)

TreeView listens and responds to the CRUD operations such as add, delete and data update (property change) at runtime. Also, it supports [editing](https://help.syncfusion.com/wpf/treeview/editing), `delete` by pressing <kbd>Delete</kbd> key.

## Add Nodes

Treeview allows user to add new node directly to the underlying collection using Add().

{% tabs %}
{% highlight c# %}
// For bound mode
(sfTreeView.DataContext as ViewModel).Countries.Add(new Country() { Name = "Newly added country"});

// For Unbound mode
sfTreeView.Nodes.Add(new TreeViewNode(){ Content = "NewlyAddedNode" });
{% endhighlight %}
{% endtabs %}

## Delete Nodes

TreeView provides built-in support to delete the selected nodes in user interface (UI) by pressing <kbd>Delete</kbd> key. You can enable the deleting support by setting the [SfTreeView.AllowDeleting](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_AllowDeleting) property to `true`.

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

You can delete node directly in underlying collection also using Remove () or RemoveAt (int index).

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

### Events

#### Conditionally deleting nodes when pressing Delete key

You can cancel the node deletion by using the `ItemDeletingEventArgs.Cancel` of [ItemDeleting](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ItemDeleting) event. You can skip certain nodes when deleting more than one node by removing items from [ItemDeletingEventArgs.Nodes](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.ItemDeletingEventArgs.html#Syncfusion_UI_Xaml_TreeView_ItemDeletingEventArgs_Nodes).

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


#### Handling selection after deleting the node from SfTreeView

You can handle the selection after remove the nodes through [SfTreeView.SelectedItem](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_SelectedItem) property in [ItemDeleted](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ItemDeleted) event.

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

## Modify Nodes

Treeview allows user to modify the data in a node by [editing](https://help.syncfusion.com/wpf/treeview/editing).