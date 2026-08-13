---
layout: post
title: MDI Resize in WPF Tabbed MDI Form control | Syncfusion®
description: Learn here all about MDI Resize support in Syncfusion® WPF Tabbed MDI Form (DocumentContainer) control and more.
platform: WPF
control: DocumentContainer
documentation: ug
---

# MDI Resize in WPF Tabbed MDI Form (DocumentContainer)

## Assembly Deployment

Refer to the [control dependencies](https://help.syncfusion.com/wpf/control-dependencies#documentcontainer) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

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

## See Also

* [Getting Started](Getting-Started.md)
* [Maximizing MDI Window](Maximizing-MDI-window.md)
* [Minimizing MDI Window](Minimizing-MDI-window.md)
* [Setting MDIBounds](Setting-MDIBounds.md)
