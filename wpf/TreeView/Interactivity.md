---
layout: post
title: Interacting with TreeView in WPF | Syncfusion
description: Learn here about the different interactions on Syncfusion WPF TreeView (SfTreeView) control and more details.
platform: wpf
control: SfTreeView
documentation: ug
---

# Interactivity in WPF TreeView (SfTreeView)

 This section explains about how to interact with `TreeView` and its items.

## Interacting with TreeView items

### ItemTapped event

The [ItemTapped](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ItemTapped_EV.html) event will be triggered whenever tapping the item.  [ItemTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.ItemTappedEventArgs.html) has the following members which provides the information for `ItemTapped` event:

 * `Node`: Gets the [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) and data associated with the tapped item as its arguments.
 * `Position`: Gets the touch position in the tapped item.
 * `Handled`: Gets or sets whether the event is handled or not.

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

The [ItemDoubleTapped](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ItemDoubleTapped_EV.html) event will be triggered whenever double tapping the item. The [ItemDoubleTappedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.ItemDoubleTappedEventArgs.html) has the following members providing information for the `ItemDoubleTapped` event:

 * `Node`: Gets the [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) and data associated with the double tapped item as its arguments.
 * `Position`: Gets the touch position in the double tapped item.
 * `Handled`: Gets or sets whether the event is handled or not.

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

The [ItemHolding](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ItemHolding_EV.html) event will be triggered whenever the item is long pressed.
 [ItemHoldingEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.ItemHoldingEventArgs.html) has the following members which provides the information for `ItemHolding` event:

 * `Node`: Gets the [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) and data associated with the hold item as its arguments.
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