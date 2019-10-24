---
layout: post
title: Maximizing MDI window| DocumentContainer | Wpf | Syncfusion
description: maximizing mdi window
platform: wpf
control: DocumentContainer
documentation: ug
---

# Maximizing MDI window

You can maximize the MDI window by setting the CanMDIMaximize property to True. The following code snippet shows the MDI Window in the maximized state.



{% highlight xaml %}



<!-- Adding Document Container -->

<syncfusion:DocumentContainer Name="DocContainer" CanMDIMaximize = "True"  Mode="MDI">

<FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Features">

</FlowDocumentScrollViewer>


</syncfusion:DocumentContainer>

{% endhighlight %}

![](Maximizing-MDI-window_images/Maximizing-MDI-window_img1.jpeg)



