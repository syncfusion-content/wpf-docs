---
layout: post
title: Use Host under the mouse | DockingManager | wpf | Syncfusion
description: Use host under the mouse in Syncfusion Essential Studio WPF DockingManager control, its elements and more.
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