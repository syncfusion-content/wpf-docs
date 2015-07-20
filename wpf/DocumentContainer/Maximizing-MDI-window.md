---
layout: post
title: Maximizing-MDI-window
description: maximizing mdi window
platform: wpf
control: DocumentContainer
documentation: ug
---

# Maximizing MDI window

You can maximize the MDI window by setting the CanMDIMaximize property to True. The following code snippet shows the MDI Window in the maximized state.



[XAML]



&lt;!-- Adding Document Container --&gt;

&lt;syncfusion:DocumentContainer Name="DocContainer" CanMDIMaximize = "True"  Mode="MDI"&gt;

&lt;FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Features"&gt;

&lt;/FlowDocumentScrollViewer&gt;

…....

…....

&lt;/syncfusion:DocumentContainer&gt;



{ ![](Maximizing-MDI-window_images/Maximizing-MDI-window_img1.jpeg) | markdownify }
{:.image }


