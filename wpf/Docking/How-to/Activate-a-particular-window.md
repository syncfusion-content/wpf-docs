---
layout: post
title: How to activate a particular window in Docking in WPF  | Syncfusion
description: Learn How to activate a particular window in Docking in WPF  using Syncfusion controls. It supports data operations, UI customization, and enterprise features.
platform: WPF
control: DockingManager
documentation: ug
---

# How to activate a particular window in Docking in WPF 

A Particular child window can be activated using its name or using its reference as follows:

{% highlight c# %}

//Activating Window using its name.

DockingManager.ActivateWindow("element1");

//Activating Window using its reference.

DockingManager.ActiveWindow = element1;

{% endhighlight  %}

#### Refer Also

Using ActiveWindow Property

