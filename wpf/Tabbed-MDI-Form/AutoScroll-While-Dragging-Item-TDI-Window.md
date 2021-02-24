---
layout: post
title: AutoScroll on drag item in WPF DocumentContainer control | Syncfusion
description: Learn about AutoScrolling while dragging items in TDI window support in Syncfusion WPF DocumentContainer control and more details.
platform: wpf
control: DocumentContainer
documentation: ug
---

# Rearrange position of document items with auto scrolling

You can move document items to position beyond the non-visual items by setting the `EnableAutoScroll` property value as `true` and dragging the respective item over the overflow button (with three dots) or beyond the overflow button to auto scroll to the required position.
The default value of `EnableAutoScroll` property is `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DocumentContainer x:Name="documentContainer" EnableAutoScroll="True" Mode="TDI" >
    <ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Document1" />
    <ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Document2" />
    <ContentControl x:Name="Content3" syncfusion:DockingManager.Header="Document3" />
    <ContentControl x:Name="Content4" syncfusion:DockingManager.Header="Document4" />
    <ContentControl x:Name="Content5" syncfusion:DockingManager.Header="Document5" />
</syncfusion:DocumentContainer>

{% endhighlight %}
{% highlight C# %}

DocumentContainer documentContainer = new DocumentContainer();
documentContainer.EnableAutoScroll = true;

{% endhighlight %}
{% endtabs %}

![Document items are rearranged by drag and drop](AutoScroll-While-Dragging-Item-TDI-Window-images/EnableAutoScroll.gif)