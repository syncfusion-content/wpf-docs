---
layout: post
title: How to clear StatePersistence entries in WPF Docking | Syncfusion®
description: Learn here how to clear statepersistance entries in Syncfusion® WPF Docking (DockingManager) control, its elements and more.
platform: wpf
control: DockingManager
documentation: ug
---

# How to clear StatePersistence entries in WPF Docking

In StatePersistence of WPF Docking Control we have five ways to store the state. Similarly, we have ways to clear those entries as given below

{% highlight c# %}

//Deletes the Registry Entries.

DockingManager.DeleteDockState();

//Deletes the persistence file in IsolatedStorage location.

DockingManager.DeleteInternalIsolatedStorage();

//Deletes the specified state file.

DockingManager.DeleteDockState(filename);

{% endhighlight %}

## Refer Also

State Persistence in WPF Docking Control

