---
layout: post
title: Use Host under the mouse | DockingManager | wpf | Syncfusion
description: use host under the mouse
platform: wpf
control: DockingManager
 documentation: ug
---

# Use Host under the mouse

HostUnderMouse is the property, which is used to get the DockedElementTabHost that was under the dragged host. This can be used to update the relevant properties of Element Host while dragging the Float child.

{% highlight xaml %}

DockedElementTabbedHost host = DockingManager.HostUnderMouse;

{% endhighlight  %}
s