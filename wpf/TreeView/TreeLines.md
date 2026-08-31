---
layout: post
title: Tree Lines in WPF TreeView | Syncfusion®
description: Tree Lines in SfTreeView enable visualizing hierarchical relationships with customizable line display, color, and thickness.
platform: wpf
control: SfTreeView
documentation: ug
---

# Tree lines in WPF TreeView (SfTreeView)

WPF TreeView allows to show the tree lines for its nodes by enabling the [ShowLines](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ShowLines) property to `true`. The default value is `false`.

{% tabs %}
{% highlight xaml %}
<treeview:SfTreeView
    Name="sfTreeView"    
    ShowLines="True"
    ChildPropertyName="Childs"
    ItemTemplate="{StaticResource SfTreeView_ItemTemplate}"
    ItemsSource="{Binding Nodes1}" />

{% endhighlight %}
{% highlight c# %}
sfTreeView.ShowLines = true;
{% endhighlight %}
{% endtabs %}

![WPF TreeView TreeLines](TreeLine_images/wpf-treeview-treelines.png)

## Enable tree line for root nodes

The WPF TreeView also supports showing tree lines for root nodes by enabling the [ShowRootLines](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_ShowRootLines) property to `true`. The default value is `false`.

{% tabs %}
{% highlight xaml %}
<treeview:SfTreeView
    Name="sfTreeView"    
    ShowLines="True"
    ShowRootLines="True"
    ChildPropertyName="Childs"
    ItemTemplate="{StaticResource SfTreeView_ItemTemplate}"
    ItemsSource="{Binding Nodes1}" />

{% endhighlight %}
{% highlight c# %}
sfTreeView.ShowLines = true;
sfTreeView.ShowRootLines = true;
{% endhighlight %}
{% endtabs %}

![WPF TreeView TreeLine for Root Nodes](TreeLine_images/wpf-treeview-treeline-for-root-nodes.png)

## Customizing the tree lines

### Customizing the line color
The WPF TreeView allows to change the color of tree lines by using the [LineStroke](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_LineStroke) property. The default value is `System.Windows.Media.Colors.LightSlateGray`.

{% tabs %}
{% highlight xaml %}
<treeview:SfTreeView
    Name="sfTreeView"    
    ShowLines="True"
    ShowRootLines="True"
    LineStroke="DeepSkyBlue"
    ChildPropertyName="Childs"
    ItemTemplate="{StaticResource SfTreeView_ItemTemplate}"
    ItemsSource="{Binding Nodes1}" />
{% endhighlight %}
{% highlight c# %}
sfTreeView.ShowLines = true;
sfTreeView.ShowRootLines = true;
sfTreeView.LineStroke = new SolidColorBrush(Colors.DeepSkyBlue);
{% endhighlight %}
{% endtabs %}

![WPF TreeView Custom TreeLines](TreeLine_images/wpf-treeview-custom-treelines.png)

### Customizing the line thickness
The WPF TreeView allows to change the thickness of tree lines by using the [LineStrokeThickness](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.TreeView.SfTreeView.html#Syncfusion_UI_Xaml_TreeView_SfTreeView_LineStrokeThickness) property. The default value is `1`.

{% tabs %}
{% highlight xaml %}
<treeview:SfTreeView
            Name="sfTreeView"           
            ShowLines="True"
            ShowRootLines="True"
            LineStrokeThickness="1.5"
            ChildPropertyName="Childs"
            ItemTemplate="{StaticResource SfTreeView_ItemTemplate}"
            ItemsSource="{Binding Nodes1}" />        
{% endhighlight %}
{% highlight c# %}
sfTreeView.ShowLines = true;
sfTreeView.ShowRootLines = true;
sfTreeView.LineStrokeThickness = 1.5;
{% endhighlight %}
{% endtabs %}

![WPF TreeView TreeLines Thickness](TreeLine_images/wpf-treeview-custom-treelines-thickness.png)

N> You can refer to our [WPF TreeView](https://www.syncfusion.com/wpf-controls/treeview) feature tour page for its key feature highlights. You can also explore our [WPF TreeView example](https://github.com/syncfusion/wpf-demos) to know how to represent hierarchical data in a tree-like structure with expand and collapse node options.
