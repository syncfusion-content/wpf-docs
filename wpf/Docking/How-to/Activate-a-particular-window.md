---
layout: post
title: How to activate a particular window in WPF Docking | Syncfusion®
description: Learn here how to activate a particular window in Syncfusion® WPF Docking (DockingManager) control, its elements and more.
platform: WPF
control: DockingManager
documentation: ug
---

# How to activate a particular window in WPF Docking

A Particular child window can be activated using its name or using its reference as follows:

{% highlight c# %}

//Activating Window using its name.

DockingManager.ActivateWindow("element1");

//Activating Window using its reference.

DockingManager.ActiveWindow = element1;

{% endhighlight  %}

#### Refer Also

Using ActiveWindow Property

