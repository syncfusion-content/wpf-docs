---
layout: post
title: How to use Host under the mouse in DockingManager in WPF  | Syncfusion
description: Learn How to use Host under the mouse in DockingManager in WPF  using Syncfusion controls. It supports data operations, UI customization, and enterprise features.
platform: WPF
control: DockingManager
documentation: ug
---

# How to use Host under the mouse in DockingManager in WPF 

HostUnderMouse is the property, which is used to get the DockedElementTabHost that was under the dragged host. This can be used to update the relevant properties of Element Host while dragging the Float child.

{% highlight xaml %}

DockedElementTabbedHost host = DockingManager.HostUnderMouse;

{% endhighlight  %}
s