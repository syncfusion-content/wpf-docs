---
layout: post
title: Setting-Window-State
description: setting window state
platform: wpf
control: DocumentContainer
documentation: ug
---

# Setting Window State

There are three possible window states of MDI windows for the Document Container control. They are as follows.

* Maximized
* Minimized
* Normal

To set the MDI window state to "minimized", use the below code snippet. FlowDocumentScrollViewer is considered as an element of the Document Container in the below mentioned example.



[XAML]



&lt;!-- Adding Document Container --&gt;

&lt;syncfusion:DocumentContainer Name="DocContainer" Mode="MDI"&gt;

&lt;FlowDocumentScrollViewer syncfusion:DocumentContainer.MDIWindowState="Minimized" &gt;

&lt;/FlowDocumentScrollViewer&gt;

…....

…....

&lt;/syncfusion:DocumentContainer&gt;



{ ![](Setting-Window-State_images/Setting-Window-State_img1.jpeg) | markdownify }
{:.image }


