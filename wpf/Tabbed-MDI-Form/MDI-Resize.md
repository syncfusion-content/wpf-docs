---
layout: post
title: MDI Resize| DocumentContainer | Wpf | Syncfusion
description: mdi resize
platform: wpf
control: DocumentContainer
documentation: ug
---

# MDI Resize

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
