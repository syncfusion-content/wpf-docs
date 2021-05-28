---
layout: post
title: Item Height Customization in WPF TreeView control | Syncfusion
description: Learn here all about Item Height Customization support in Syncfusion WPF TreeView (SfTreeView) control and more.
platform: wpf
control: SfTreeView
documentation: ug
---

# Item Height Customization in WPF TreeView (SfTreeView)

The TreeView provides various options to customize the height of items. To achieve this customization, please walkthrough the below sections:

## Customize Item Height

The TreeView allows customizing the height of items by setting the [ItemHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ItemHeight) property. The default value of this property is `24`. This property can be customized at runtime.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView x:Name="sfTreeView" ItemHeight="30" />
{% endhighlight %}
{% highlight c# %}
sfTreeView.ItemHeight = 30;
{% endhighlight %}
{% endtabs %}

## Customize Item height using `QueryNodeSize` event
 The TreeView allows customizing the height of the items using [QueryNodeSize](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html) event. This event is raised whenever the item comes into view and triggered with [QueryNodeSizeEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.QueryNodeSizeEventArgs.html).

The `SfTreeView.QueryNodeSize` event provides the following arguments:
 
 * [Node](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.QueryNodeSizeEventArgs.html#Syncfusion_UI_Xaml_TreeView_QueryNodeSizeEventArgs_Node): This argument contains the [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) and data associated with it.
 * [Height](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.QueryNodeSizeEventArgs.html#Syncfusion_UI_Xaml_TreeView_QueryNodeSizeEventArgs_Height): This argument contains the default item height of the queried item and can be set with desired size.
 * [Handled](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.QueryNodeSizeEventArgs.html#Syncfusion_UI_Xaml_TreeView_QueryNodeSizeEventArgs_Handled): Decides whether the specified or measured height can be set to the item or not. The default value is `false`. When this property is not set, the decided height will not set to the item.

### Customize specific item height using custom value

The TreeView allows customizing the height of the specific item by setting the custom value directly to the [Height](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.QueryNodeSizeEventArgs.html#Syncfusion_UI_Xaml_TreeView_QueryNodeSizeEventArgs_Height) argument which is available in [QueryNodeSizeEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.QueryNodeSizeEventArgs.html).

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView
    x:Name="sfTreeView"
    Margin="10"
    QueryNodeSize="SfTreeView_QueryNodeSize"    
    ExpandActionTrigger="Node"
    ItemsSource="{Binding Menu}" />
{% endhighlight %}
{% highlight c# %}
sfTreeView.QueryNodeSize += SfTreeView_QueryNodeSize;

private void SfTreeView_QueryNodeSize(object sender, Syncfusion.UI.Xaml.TreeView.QueryNodeSizeEventArgs e)
{
    if (e.Node.Level == 0)
    {
        //Returns speified item height for items.
        e.Height = 50;
        e.Handled = true;
    }
}

{% endhighlight %}
{% endtabs %}

## Autofit item height based on content

The TreeView allows adjusting height of items based on the content measured size while loaded by setting the `Height` argument with value returned from [QueryNodeSizeEventArgs.GetAutoFitNodeHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.QueryNodeSizeEventArgs.html#Syncfusion_UI_Xaml_TreeView_QueryNodeSizeEventArgs_GetAutoFitNodeHeight) method.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView
    x:Name="sfTreeView"
    Margin="10"
    QueryNodeSize="SfTreeView_QueryNodeSize"    
    ExpandActionTrigger="Node"
    ItemsSource="{Binding Menu}" />
{% endhighlight %}
{% highlight c# %}
 sfTreeView.QueryNodeSize += SfTreeView_QueryNodeSize;

private void SfTreeView_QueryNodeSize(object sender, Syncfusion.UI.Xaml.TreeView.QueryNodeSizeEventArgs e)
{
    if (e.Node.Level == 0)
    {
        //Returns specified item height for items.
        e.Height = 30;
        e.Handled = true;
    }
    else
    {
        // Returns item height based on the content loaded.
        e.Height = e.GetAutoFitNodeHeight();
        e.Handled = true;
    }
}

{% endhighlight %}
{% endtabs %}

N> View sample in [GitHub](https://github.com/SyncfusionExamples/How-to-autofit-item-height-based-on-content-in-wpf-treeview).

![WPF TreeView with AutoFit Items](ItemHeight_images/wpf-treeview-with-autofit-items.png)

## Limitations

 * Define the size of the image when loading image in the [SfTreeView.ItemTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ItemTemplate). Because, it does not return actual measured size when measuring before item layout.
 
