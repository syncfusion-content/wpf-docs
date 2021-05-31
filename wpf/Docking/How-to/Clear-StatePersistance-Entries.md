---
layout: post
title: Clear StatePersistance Entries | DockingManager | wpf | Syncfusion
description:  clear statepersistance entries
platform: wpf
control: DockingManager
 documentation: ug
---

#  Clear StatePersistence Entries

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

