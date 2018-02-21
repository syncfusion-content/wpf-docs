---
layout: post
title: Virtualization is a technique to enable faster rendering by loading only object that lies in viewport area of scrollviewer.
description: how to enable faster rendering in Diagram?
platform: wpf
control: SfDiagram
documentation: ug
---

# Virtualization

Virtualization is the process of loading the diagramming objects available in the visible area of the Diagram control, that is, only the diagramming objects that lie within the ViewPort of the ScrollViewer are loaded (remaining objects are loaded only when they come into view).

This feature gives optimized performance while loading and dragging items to the SfDiagram that consists of many Nodes and Line Connectors.

Virtualization is disabled in Diagram by default, to enable this you can use `Constraints` property of the SfDiagram.

{% highlight C# %}

sfdiagram.Constraints = sfdiagram.Constraints | GraphConstraints.Virtualize;

{% endhighlight %}

## Deferred Scrolling

To improve scrolling performance, the outline of a diagram element will be displayed until the UI element is loaded, regardless of the weight of the element. 

I> In SfDiagram, we named this support as `Outline`.

Outline is disabled in Diagram by default, to enable this you can use `Constraints` property of the SfDiagram.

{% highlight C# %}

diagram.Constraints |= GraphConstraints.Outline;

{% endhighlight %}

![](Virtualization_images/Virtualization_img1.gif)

Outline customization
{:.caption}

Options are provided to override the appearance, style and interval time of outline. `OutlineSettings` property of SfDiagram will help you to achieve customization of Outline.
 
Refer to the [OutlineSettings Class members](https://help.syncfusion.com/cr/cref_files/wpf/sfdiagram/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.OutlineSettings_members.html)