---
layout: post
title: Right to left(RTL) in WPF TreeView control | Syncfusion
description: Learn here all about Right to left(RTL) support in Syncfusion WPF TreeView (SfTreeView) control and more.
platform: wpf
control: SfTreeView
documentation: ug
---

# Right to left(RTL) in WPF TreeView (SfTreeView)

TreeView supports to change the flow of text to the right-to-left direction by setting the [FlowDirection](https://docs.microsoft.com/en-us/dotnet/api/system.windows.frameworkelement.flowdirection?view=netframework-4.0) to `RightToLeft`. 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfTreeView x:Name="sfTreeView" FlowDirection="RightToLeft"/>

{% endhighlight %}
{% highlight c# %}

sfTreeView.FlowDirection = FlowDirection.RightToLeft;

{% endhighlight %}
{% endtabs %}

![WPF TreeView with Right to Left](Right-To-Left_images/wpf-treeview-right-to-left.png)

N> You can refer to our [WPF TreeView](https://www.syncfusion.com/wpf-controls/treeview) feature tour page for its groundbreaking feature representations. You can also explore our [WPF TreeView example](https://github.com/syncfusion/wpf-demos) to knows how to represents hierarchical data in a tree-like structure with expand and collapse node options.


