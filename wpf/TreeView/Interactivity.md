---
layout: post
title: Interactivity in WPF SfTreeView | Syncfusion®
description: Interactivity in SfTreeView supports tap, double-tap, and hold interactions, enabling responsive handling of tree node actions.
platform: wpf
control: SfTreeView
documentation: ug
---

# Interactivity in WPF TreeView (SfTreeView)

This section explains how to interact with the TreeView and its items.

## Interacting with TreeView items

### ItemTapped event

The [ItemTapped](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html) event is triggered whenever an item is tapped. [ItemTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.ItemTappedEventArgs.html) has the following members, which provide information for the `ItemTapped` event:

 * `Node`: Gets the [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) and the data associated with the tapped item.
 * `Position`: Gets the touch position in the tapped item.
 * `Handled`: Gets or sets whether the event is handled.

{% tabs %}
{% highlight c# %}

sfTreeView.ItemTapped += SfTreeView_ItemTapped;

private void SfTreeView_ItemTapped(object sender, ItemTappedEventArgs e)
{
    MessageBox.Show("Tapped Item: " + (e.Node.Content as Model).State);
}

{% endhighlight %}
{% endtabs %}

### ItemDoubleTapped event

The [ItemDoubleTapped](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html) event is triggered whenever an item is double-tapped. The [ItemDoubleTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.ItemDoubleTappedEventArgs.html) has the following members, which provide information for the `ItemDoubleTapped` event:

 * `Node`: Gets the [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) and the data associated with the double-tapped item.
 * `Position`: Gets the touch position in the double-tapped item.
 * `Handled`: Gets or sets whether the event is handled.

{% tabs %}
{% highlight c# %}

sfTreeView.ItemDoubleTapped += SfTreeView_ItemDoubleTapped;

private void SfTreeView_ItemDoubleTapped(object sender, ItemDoubleTappedEventArgs e)
{
    MessageBox.Show("DoubleTapped Item: " + (e.Node.Content as Model).State);
}

{% endhighlight %}
{% endtabs %}

### ItemHolding event

The [ItemHolding](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html) event is triggered whenever an item is long-pressed (held). [ItemHoldingEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.ItemHoldingEventArgs.html) has the following members, which provide information for the `ItemHolding` event:

 * `Node`: Gets the [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) and the data associated with the hold item as its arguments.
 * `Position`: Gets the touch position in the hold item.
 
{% tabs %}
{% highlight c# %}

sfTreeView.ItemHolding += SfTreeView_ItemHolding;
private void SfTreeView_ItemHolding(object sender, ItemHoldingEventArgs e)
{
    MessageBox.Show("HoldItem: " + (e.Node.Content as Model).State);
}

{% endhighlight %}
{% endtabs %}

N> You can refer to our [WPF TreeView](https://www.syncfusion.com/wpf-controls/treeview) feature tour page for its key feature highlights. You can also explore our [WPF TreeView example](https://github.com/syncfusion/wpf-demos) to know how to represent hierarchical data in a tree-like structure with expand and collapse node options.