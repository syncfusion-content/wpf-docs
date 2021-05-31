---
layout: post
title: Activate a particular window | DockingManager | wpf | Syncfusion
description: activate a particular window
platform: wpf
control: DockingManager
 documentation: ug
---

# Activate a particular window

A Particular child window can be activated using its name or using its reference as follows:

{% highlight c# %}

//Activating Window using its name.

DockingManager.ActivateWindow("element1");

//Activating Window using its reference.

DockingManager.ActiveWindow = element1;

{% endhighlight  %}

#### Refer Also

Using ActiveWindow Property

