---
layout: post
title: Unpin-all-AutoHide-window
description: unpin all autohide window
platform: wpf
control: DockingManager
documentation: ug
---

## Unpin all AutoHide window

You can Unpin all AutoHidden windows by using the method UnPinAutoHide().This can be shown below:



{% highlight html %}
  <syncfusion:DockingManager Name="DockingManager">            <Grid syncfusion:DockingManager.State="AutoHidden"/>            <Grid syncfusion:DockingManager.State="AutoHidden"/>            <Grid syncfusion:DockingManager.State="AutoHidden"/>            <Grid syncfusion:DockingManager.State="AutoHidden"/>  </syncfusion:DockingManager>

DockingManager. UnPinAllAutoHide();  

{% endhighlight  %}

