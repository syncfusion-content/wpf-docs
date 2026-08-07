---
layout: post
title: How to clear StatePersistence entries in Docking in WPF  | Syncfusion
description: Learn How to clear StatePersistence entries in Docking in WPF  using Syncfusion controls. It supports data operations, UI customization, and enterprise features.
platform: WPF
control: DockingManager
documentation: ug
---

# How to clear StatePersistence entries in Docking in WPF 

In StatePersistence of DockingManager we have five ways to store the state. Similarly, we have ways to clear those entries as given below

{% highlight c# %}

//Deletes the Registry Entries.

DockingManager.DeleteDockState();

//Deletes the persistence file in IsolatedStorage location.

DockingManager.DeleteInternalIsolatedStorage();

//Deletes the specified state file.

DockingManager.DeleteDockState(filename);

{% endhighlight %}

#### Refer Also

State Persistence in DockingManager

