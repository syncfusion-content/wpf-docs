---
layout: post
title: Right-to-left in WPF TreeView | Syncfusion
description: Learn here about Right-to-left FlowDirection support in Syncfusion WPF TreeView (SfTreeView) control and more details. 
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

![WPF TreeView with right to left](Right-To-Left_images/Right-To-Left_image1.png)


