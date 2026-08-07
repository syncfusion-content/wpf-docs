---
layout: post
title: How to use Host under the mouse in WPF DockingManager | Syncfusion®
description: Learn here how to use host under the mouse in Syncfusion® WPF Docking (DockingManager) control, its elements and more.
platform: WPF
control: DockingManager
documentation: ug
---

# How to use Host under the mouse in WPF DockingManager

HostUnderMouse is the property, which is used to get the DockedElementTabHost that was under the dragged host. This can be used to update the relevant properties of Element Host while dragging the Float child.

{% highlight xaml %}

DockedElementTabbedHost host = DockingManager.HostUnderMouse;

{% endhighlight  %}
s