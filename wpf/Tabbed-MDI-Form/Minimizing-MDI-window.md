---
layout: post
title: Minimizing MDI window in WPF Tabbed MDI Form control | Syncfusion
description: Learn here all about Minimizing MDI window support in Syncfusion WPF Tabbed MDI Form (DocumentContainer) control and more.
platform: wpf
control: DocumentContainer
documentation: ug
---

# Minimizing MDI window in WPF Tabbed MDI Form (DocumentContainer)

You can minimize the `MDI` window by setting the [CanMDIMinimize](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_CanMDIMinimize) property as `true`. The default value of `CanMDIMinimize` property is `false`. The minimized  MDI windows are arranged one by one in the bottom-left corner of the window.

{% tabs %}
{% highlight xaml %}

<syncfusion:DocumentContainer Name="DocContainer"
                              CanMDIMinimize="True" 
                              Mode="MDI">
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Features"/>
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Window1"/>
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Document Container"/>
</syncfusion:DocumentContainer>

{% endhighlight %}
{% endtabs %}

![Minimizing MDI window in WPF Document Container](minimizing-mdi-window_images/wpf-document-container-minimizing-window.jpeg)

## Restrict Minimizing the MDI window

You can restrict minimizing the `MDI` window by setting the `CanMDIMinimize` property as `false`.

{% tabs %}
{% highlight xaml %}

<syncfusion:DocumentContainer Name="DocContainer"
                              CanMDIMinimize="False" 
                              Mode="MDI">
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Features"/>
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Window1"/>
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Document Container"/>
</syncfusion:DocumentContainer>

{% endhighlight %}
{% endtabs %}

![Restrict the Minimizing MDI window in Document Container](minimizing-mdi-window_images/wpf-document-container-restrict-minimizing.png)

