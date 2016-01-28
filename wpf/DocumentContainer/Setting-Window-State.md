---
layout: post
title: Setting Window State| DocumentContainer | Wpf | Syncfusion
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



{% highlight xaml %}


<!-- Adding Document Container -->

<syncfusion:DocumentContainer Name="DocContainer" Mode="MDI">

<FlowDocumentScrollViewer syncfusion:DocumentContainer.MDIWindowState="Minimized" >

</FlowDocumentScrollViewer>

…....

…....

</syncfusion:DocumentContainer>

{% endhighlight %}

![](Setting-Window-State_images/Setting-Window-State_img1.jpeg)



