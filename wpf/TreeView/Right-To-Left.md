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


