---
layout: post
title: How to detect hosted window in WPF Docking | Syncfusion®
description: Learn here how to detect whether the window is hosted in Syncfusion® WPF Docking (DockingManager) control, its elements and more.
platform: wpf
control: DockingManager
documentation: ug
---

# How to detect hosted window in WPF Docking

There two ways to detect whether a FrameworkElement is hosted in WPF Docking Control or not. They are:  

1. Getting WPF Docking Control instance for a FrameworkElement and checking whether it is null or not.
2. Detecting whether the FrameworkElement is present in the Children collection of WPF Docking Control.

The two ways are shown below:


{% highlight c# %}

//Getting DockingManager Instance.

DockingManager manager=DockingManager.GetDockingManager(element1);

//Checking whether element1 is in children collection.

DockingManager.Children.Contains(element1);

{% endhighlight  %}