---
layout: post
title: Setting Window State in WPF DocumentContainer | Syncfusion®
description: Set the window state of documents in the Syncfusion WPF Tabbed MDI Form (DocumentContainer) control such as normal, minimized, or maximized.
platform: wpf
control: DocumentContainer
documentation: ug
---
# Setting Window State in WPF DocumentContainer 

The DocumentContainer supports the following three window states for MDI child windows:

* **Maximized**
* **Minimized**
* **Normal**

The window state is set per child element using the `MDIWindowState` attached property (`Syncfusion.Windows.Tools.Controls.MDIWindowState` enum).

## Setting the Window State to Minimized

A `FlowDocumentScrollViewer` is used as an example child element below.

{% tabs %}
{% highlight XAML %}
<syncfusion:DocumentContainer Name="DocContainer" Mode="MDI">
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.MDIWindowState="Minimized" />
    <!-- additional child windows -->
</syncfusion:DocumentContainer>
{% endhighlight %}
{% highlight C# %}
FlowDocumentScrollViewer flow = new FlowDocumentScrollViewer();
DocumentContainer.SetMDIWindowState(flow, MDIWindowState.Minimized);
DocContainer.Items.Add(flow);
{% endhighlight %}
{% endtabs %}

## Setting the Window State to Maximized

{% tabs %}
{% highlight XAML %}
<syncfusion:DocumentContainer Name="DocContainer" Mode="MDI">
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.MDIWindowState="Maximized" />
</syncfusion:DocumentContainer>
{% endhighlight %}
{% highlight C# %}
FlowDocumentScrollViewer flow = new FlowDocumentScrollViewer();
DocumentContainer.SetMDIWindowState(flow, MDIWindowState.Maximized);
DocContainer.Items.Add(flow);
{% endhighlight %}
{% endtabs %}

## Setting the Window State to Normal

{% tabs %}
{% highlight XAML %}
<syncfusion:DocumentContainer Name="DocContainer" Mode="MDI">
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.MDIWindowState="Normal" />
</syncfusion:DocumentContainer>
{% endhighlight %}
{% highlight C# %}
FlowDocumentScrollViewer flow = new FlowDocumentScrollViewer();
DocumentContainer.SetMDIWindowState(flow, MDIWindowState.Normal);
DocContainer.Items.Add(flow);
{% endhighlight %}
{% endtabs %}

## Notification of MDI Window State Changes

The [MDIWindowStateChanging](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html#Syncfusion_Windows_Tools_Controls_DocumentContainer_MDIWindowStateChanging) event occurs before the state of an MDI window is changed. The state change can be canceled by setting `e.Cancel` to `true`. The corresponding `MDIWindowStateChanged` event is raised after the state has actually changed.

{% tabs %}
{% highlight XAML %}
<syncfusion:DocumentContainer Name="DocContainer" Mode="MDI"
                              MDIWindowStateChanging="DocContainer_MDIWindowStateChanging">
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Window1" />
    <FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Window2" />
</syncfusion:DocumentContainer>
{% endhighlight %}

{% highlight C# %}
private void DocContainer_MDIWindowStateChanging(object sender, MDIWindowStateChangingEventArgs e)
{
    if (e.NewState == MDIWindowState.Maximized)
        e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}