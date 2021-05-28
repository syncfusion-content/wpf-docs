---
layout: post
title: Showing the progress bar| Hierarchical Navigator | Wpf | Syncfusion
description: Showing the progress bar in Syncfusion Essential Studio WPF Hierarchy Navigator control, its elements and more.
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

## Showing the progress bar

There are two methods to show the progress bar: 

1. Calling the ShowProgressBar method in HierarchyNavigator, which shows the progress bar with a time span of 500 ms.



   ~~~csharp

			HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();

			hierarchyNavigator.ShowProgressBar();

   ~~~

2. Passing an argument in the method with a specified time span. The image below specifies a time span of 1000 ms.



   ~~~csharp

			HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();

			hierarchyNavigator.ShowProgressBar(new TimeSpan(0, 0, 0, 0, 1000));

   ~~~

