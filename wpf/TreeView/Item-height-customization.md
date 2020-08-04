---
layout: post
title: Item Height Customization in WPF TreeView | Syncfusion
description: Learn here about customize the height of the items in WPF TreeView. And autofit the items based on node content.
platform: wpf
control: SfTreeView
documentation: ug
---

# Item Height Customization in WPF TreeView (SfTreeView)

The TreeView provides various options to customize the height of items. To achieve this customization, please walkthrough the below sections:

## Customize Item Height

The TreeView allows customizing the height of items by setting the [ItemHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ItemHeight.html) property. The default value of this property is `24`. This property can be customized at runtime.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView x:Name="sfTreeView" ItemHeight="30" />
{% endhighlight %}
{% highlight c# %}
sfTreeView.ItemHeight = 30;
{% endhighlight %}
{% endtabs %}

## Customize Item height using `QueryNodeSize` event
 The TreeView allows customizing the height of the items using [QueryNodeSize](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~QueryNodeSize_EV.html) event. This event is raised whenever the item comes into view and triggered with [QueryNodeSizeEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.QueryNodeSizeEventArgs.html).

The `SfTreeView.QueryNodeSize` event provides the following arguments:
 
 * [Node](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.QueryNodeSizeEventArgs~Node.html): This argument contains the [TreeViewNode](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.Engine.TreeViewNode.html) and data associated with it.
 * [Height](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.QueryNodeSizeEventArgs~Height.html): This argument contains the default item height of the queried item and can be set with desired size.
 * [Handled](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.QueryNodeSizeEventArgs~Handled.html): Decides whether the specified or measured height can be set to the item or not. The default value is `false`. When this property is not set, the decided height will not set to the item.

### Customize specific item height using custom value

The TreeView allows customizing the height of the specific item by setting the custom value directly to the [Height](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.QueryNodeSizeEventArgs~Height.html) argument which is available in [QueryNodeSizeEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.QueryNodeSizeEventArgs.html).

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

The TreeView allows adjusting height of items based on the content measured size while loaded by setting the `Height` argument with value returned from [QueryNodeSizeEventArgs.GetAutoFitNodeHeight](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.QueryNodeSizeEventArgs~GetAutoFitNodeHeight.html) method.

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

![AutoFit items](ItemHeight_images/ItemHeight_image1.png)

## Limitations

 * Define the size of the image when loading image in the [SfTreeView.ItemTemplate](https://help.syncfusion.com/cr/wpf/Syncfusion.SfTreeView.WPF~Syncfusion.UI.Xaml.TreeView.SfTreeView~ItemTemplate.html). Because, it does not return actual measured size when measuring before item layout.
 
