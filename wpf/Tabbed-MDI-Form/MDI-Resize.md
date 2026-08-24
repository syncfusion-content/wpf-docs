---
layout: post
title: MDI Resize in WPF DocumentContainer | Syncfusion®
description: Enable or disable resizing of MDI child windows in the Syncfusion WPF Tabbed MDI Form (DocumentContainer) control using built-in options.
platform: wpf
control: DocumentContainer
documentation: ug
---

# MDI Resize in WPF DocumentContainer

The DocumentContainer provides options to resize its child elements in MDI mode. Setting the [IsAllowMDIResize](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_IsAllowMDIResize) property to `true` will enable the end user to resize the container elements by dragging the edges of each MDI child window. The default value of `IsAllowMDIResize` is `true`.

{% tabs %}
{% highlight XAML %}
<syncfusion:DocumentContainer Name="DocContainer" IsAllowMDIResize="True" Mode="MDI">
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Features">
    </FlowDocumentScrollViewer>
    <!-- additional child windows -->
</syncfusion:DocumentContainer>
{% endhighlight %}

{% highlight C# %}
DocContainer.IsAllowMDIResize = true;
{% endhighlight %}
{% endtabs %}
