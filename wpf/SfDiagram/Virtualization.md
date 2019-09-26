---
layout: post
title: Quick rendering by loading object lies in viewport alone | Syncfusion.
description: how to enable faster rendering in Diagram?
platform: wpf
control: SfDiagram
documentation: ug
---

# Virtualization

Virtualization is the process of loading the diagramming objects available in the visible area of the Diagram control, that is, only the diagramming objects that lie within the ViewPort of the ScrollViewer are loaded (remaining objects are loaded only when they come into view).

This feature gives optimized performance while loading and dragging items to the SfDiagram that consists of many Nodes and Line Connectors.

{% tabs %}
{% highlight C# %}

diagram.Constraints = diagram.Constraints | GraphConstraints.Virtualize;

{% endhighlight %}
{% endtabs %}

## Deferred Scrolling

To improve scrolling performance, the outline of a diagram element will be displayed until the UI element is loaded, regardless of the weight of the element. 

{% tabs %}
{% highlight C# %}

diagram.Constraints |= GraphConstraints.Virtualize | GraphConstraints.Outline;

{% endhighlight %}
{% endtabs %}

N> In SfDiagram, we named Deferred Scrolling support as `Outline`. Outline is only applicable when virtualization is enabled.

![DeferredScrolling](Virtualization_images/Virtualization_img1.gif)

### Outline customization

Options are provided to override the appearance, style and interval time of outline by using [OutlineSettings](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfDiagram.WPF~Syncfusion.UI.Xaml.Diagram.OutlineSettings_members.html) property of SfDiagram.