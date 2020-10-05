---
layout: post
title: Editing with WPF TreeView control | Syncfusion
description: Learn here about editing of TreeViewNode with Syncfusion WPF TreeView (SfTreeView) control and editing related events. 
platform: wpf
control: SfTreeView
documentation: ug
---

# Editing in WPF TreeView (SfTreeView)

This section explains how to perform editing and its related operations in the TreeView.

## Entering Edit Mode
SfTreeView provides support for editing and it can be enabled or disabled by using [SfTreeView.AllowEditing](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_AllowEditing) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView x:Name="sfTreeView" AllowEditing="True"/>
{% endhighlight %}
{% highlight c# %}
sfTreeView.AllowEditing = true;
{% endhighlight %}
{% endtabs %}

You can enter edit mode in a node by pressing <kbd>F2</kbd> key only. The editing changes in a node will be committed only when user move to next node or pressing <kbd>Enter</kbd> key. Also when user press <kbd>Esc</kbd> key, then the changes made in a node will be reverted. 

[WPF TreeView in Edit Mode](Editing_images/Editing_image1.png);

W> It is necessary to define [EditTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_EditTemplate) / [EditTemplateSelector](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_EditTemplateSelector) for bound mode, to enable editing. For UnboundMode, textbox will be loaded in edit mode by default.

## Programmatic Editing

### BeginEdit

SfTreeView allows you to edit the node programmatically by calling the [BeginEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_BeginEdit_Syncfusion_UI_Xaml_TreeView_Engine_TreeViewNode_) method.

{% tabs %}
{% highlight c# %}
this.sfTreeView.Loaded += TreeView_Loaded;

private void TreeView_Loaded(object sender, RoutedEventArgs e)
{
    this.sfTreeView.BeginEdit(this.sfTreeView.Nodes[0]);
}
{% endhighlight %}
{% endtabs %}

N> [CurrentItem](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_CurrentItem) is set to the node for which the BeginEdit is called.

### EndEdit

You can call [EndEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_EndEdit_Syncfusion_UI_Xaml_TreeView_Engine_TreeViewNode_) method to programmatically end edit.

{% tabs %}
{% highlight c# %}
this.sfTreeView.Loaded += TreeView_Loaded;

private void TreeView_Loaded(object sender, RoutedEventArgs e)
{
    this.sfTreeView.EndEdit(this.sfTreeView.Nodes[0]);
}
{% endhighlight %}
{% endtabs %}

## Editing Events

### ItemBeginEdit Event

The [ItemBeginEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ItemBeginEdit) event occurs when the node enters edit mode. The [TreeViewItemBeginEditEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.TreeViewItemBeginEditEventArgs.html) has the following members which provides information about the `ItemBeginEdit` event.

* [Node](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.TreeViewItemEditEventArgs.html#Syncfusion_UI_Xaml_TreeView_TreeViewItemEditEventArgs_Node) : Gets the [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) which is being edited.

You can cancel the editing of certain node within this event by setting `TreeViewItemBeginEditEventArgs.Cancel` as true.

{% tabs %}
{% highlight c# %}
sfTreeView.ItemBeginEdit += TreeView_ItemBeginEdit;

private void TreeView_ItemBeginEdit(object sender, TreeViewItemBeginEditEventArgs e)
{
    if (e.Node.Content == "Grains")
		e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

### ItemEndEdit Event

The [ItemEndEdit](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ItemEndEdit) event occurs when the node leaves the edit mode. The [TreeViewItemEndEditEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.TreeViewItemEndEditEventArgs.html) has the following members which provides information about the `ItemEndEdit` event.

* [Node](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.TreeViewItemEditEventArgs.html#Syncfusion_UI_Xaml_TreeView_TreeViewItemEditEventArgs_Node) : Gets the [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) which is being edited.

You can cancel the editing from being ended for certain nodes within this event by setting `TreeViewItemEndEditEventArgs.Cancel` as true.

{% tabs %}
{% highlight c# %}
sfTreeView.ItemEndEdit += TreeView_ItemEndEdit;

private void TreeView_ItemEndEdit(object sender, TreeViewItemEndEditEventArgs e)
{
	if (e.Node.Content == "Balnc")
		e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

