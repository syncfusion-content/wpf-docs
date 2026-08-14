---
layout: post
title: MDI Resize in WPF Tabbed MDI Form | Syncfusion®
description: Enable or disable resizing of MDI child windows in the Syncfusion WPF Tabbed MDI Form (DocumentContainer) control using built-in options.
platform: wpf
control: DocumentContainer
documentation: ug
---

# MDI Resize in WPF Tabbed MDI Form

Document Container provides options to resize its elements. Setting AllowMDIResize property to _true__,_ will enable the end users to resize the container elements. 

To set this property, use the below code.



{% highlight xaml %}



<!-- Adding Document Container -->

<syncfusion:DocumentContainer Name="DocContainer" IsAllowMDIResize="True"  Mode="MDI">

<FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Features">

</FlowDocumentScrollViewer>

…....

…....

</syncfusion:DocumentContainer>


{% endhighlight %}
