---
layout: post
title: Detect whether the window is hosted in WPF DockingManager | Syncfusion
description: Detect whether the window is hosted in Syncfusion Essential Studio WPF DockingManager control, its elements and more.
platform: wpf
control: DockingManager
documentation: ug
---

# Detect whether the window is hosted in DockingManager

There two ways to detect whether a FrameworkElement is hosted in DockingManager or not. They are:  

1. Getting DockingManager instance for a FrameworkElement and checking whether it is null or not.
2. Detecting whether the FrameworkElement is present in the Children collection of DockingManager.

The two ways are shown below:


{% highlight c# %}

//Getting DockingManager Instance.

DockingManager manager=DockingManager.GetDockingManager(element1);

//Checking whether element1 is in children collection.

DockingManager.Children.Contains(element1);

{% endhighlight  %}