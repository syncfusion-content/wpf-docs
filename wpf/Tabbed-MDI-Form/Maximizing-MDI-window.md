---
layout: post
title: Maximizing MDI Window in WPF DocumentContainer | Syncfusion®
description: Maximize an MDI child window inside the Syncfusion WPF Tabbed MDI Form (DocumentContainer) control so it fills the available client area.
platform: wpf
control: DocumentContainer
documentation: ug
---

# Maximizing MDI Window in WPF Document Container

You can maximize the `MDI` window by setting the [CanMDIMaximize](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_CanMDIMaximize) property to `true`. The default value of `CanMDIMaximize` is `false`. When enabled, the maximize, restore, and resize chrome is shown on the MDI window and the user can double-click the title bar to maximize the window.

{% tabs %}
{% highlight XAML %}

<syncfusion:DocumentContainer Name="DocContainer"
                              CanMDIMaximize="True"
                              Mode="MDI">
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Features"/>
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Window1"/>
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Document Container"/>
</syncfusion:DocumentContainer>

{% endhighlight %}
{% highlight C# %}
DocContainer.CanMDIMaximize = true;
{% endhighlight %}
{% endtabs %}

![Maximizing MDI window in Document Container](Maximizing-MDI-window_images/Maximizing-MDI-window_img1.jpeg)

## Restricting Maximizing the MDI Window

You can restrict maximizing the `MDI` window by setting the `CanMDIMaximize` property to `false` (the default). When set to `false`, the maximize/restore button is hidden from the MDI chrome and the user cannot maximize the window through the UI.

{% tabs %}
{% highlight XAML %}

<syncfusion:DocumentContainer Name="DocContainer"
                              CanMDIMaximize="False"
                              Mode="MDI">
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Features"/>
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Window1"/>
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Document Container"/>
</syncfusion:DocumentContainer>

{% endhighlight %}
{% highlight C# %}
DocContainer.CanMDIMaximize = false;
{% endhighlight %}
{% endtabs %}

![Restrict the Maximizing MDI window in Document Container](Maximizing-MDI-window_images/Restrict_Maximizing.png)



