---
layout: post
title: How to detect hosted window in Docking in WPF  | Syncfusion
description: Learn How to detect hosted window in Docking in WPF  using Syncfusion controls. It supports data operations, UI customization, and enterprise features.
platform: WPF
control: DockingManager
documentation: ug
---

# How to detect hosted window in Docking in WPF 

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