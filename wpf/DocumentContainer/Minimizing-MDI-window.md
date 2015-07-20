---
layout: post
title: Minimizing-MDI-window
description: minimizing mdi window
platform: wpf
control: DocumentContainer
documentation: ug
---

# Minimizing MDI window

You can minimize the MDI window by setting the CanMDIMinimize property to _true_. The following code snippet shows the MDI Window in the minimize state.



[XAML]



&lt;!-- Adding Document Container --&gt;

&lt;syncfusion:DocumentContainer Name="DocContainer" CanMDIMinimize="True"  Mode="MDI"&gt;

&lt;FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Features"&gt;

&lt;/FlowDocumentScrollViewer&gt;

…....

…....

&lt;/syncfusion:DocumentContainer&gt;



{ ![](Minimizing-MDI-window_images/Minimizing-MDI-window_img1.jpeg) | markdownify }
{:.image }


