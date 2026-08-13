---
layout: post
title: Canceling Progress Bar in WPF HierarchyNavigator | Syncfusion®
description: Canceling Progress Bar in WPF HierarchyNavigator provides control over ongoing operations, improving responsiveness and user experience.
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Canceling Progress Bar in WPF HierarchyNavigator

There are two methods to cancel a progress bar:

1. Calling the CancelProgressBar method in HierarchyNavigator.



   ~~~csharp

			HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();

			hierarchyNavigator.CancelProgressBar();

   ~~~

2. Passing an argument in the method to cancel the progress bar for a specified time span. The image below specifies a time span of 1000 ms.



   ~~~csharp

			HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();

			hierarchyNavigator.OnCancelProgressBar(new TimeSpan(0, 0, 0, 0, 1000));

   ~~~

