---
layout: post
title: Maximizing MDI window in WPF Tabbed MDI Form control | Syncfusion
description: Learn here all about Maximizing MDI window support in Syncfusion WPF Tabbed MDI Form (DocumentContainer) control and more.
platform: wpf
control: DocumentContainer
documentation: ug
---

# Maximizing MDI window in WPF Tabbed MDI Form (DocumentContainer)

You can maximize the `MDI` window by setting the [CanMDIMaximize](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_CanMDIMaximize) property as `true`. The default value of `CanMDIMaximize` property is `false`.

{% tabs %}
{% highlight xaml %}

<syncfusion:DocumentContainer Name="DocContainer"
                              CanMDIMaximize="True" 
                              Mode="MDI">
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Features"/>
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Window1"/>
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Document Container"/>
</syncfusion:DocumentContainer>

{% endhighlight %}
{% endtabs %}

![Maximizing MDI window in Document Container](Maximizing-MDI-window_images/Maximizing-MDI-window_img1.jpeg)

## Restrict Maximizing the MDI window

You can restrict maximizing the `MDI` window by setting the `CanMDIMaximize` property as `false`.

{% tabs %}
{% highlight xaml %}

<syncfusion:DocumentContainer Name="DocContainer"
                              CanMDIMaximize="False" 
                              Mode="MDI">
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Features"/>
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Window1"/>
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Document Container"/>
</syncfusion:DocumentContainer>

{% endhighlight %}
{% endtabs %}

![Restrict the Maximizing MDI window in Document Container](Maximizing-MDI-window_images/Restrict_Maximizing.png)



