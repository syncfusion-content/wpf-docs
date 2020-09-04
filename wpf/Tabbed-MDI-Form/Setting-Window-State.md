---
layout: post
title: Setting Window State| DocumentContainer | Wpf | Syncfusion
description: Explains about window states of MDIWindow in DocumentContainer
platform: wpf
control: DocumentContainer
documentation: ug
---
# Window States of MDIWindow

## Setting Window State

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

![Displays maximized MDI window](Setting-Window-State_images/Setting-Window-State_img1.jpeg)


## Notify event for MDIWindow State Changes

The [MDIWindowStateChanging](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DocumentContainer.html) event occurs before the state of the MDIWindow is changed. The state changing of MDIWindow can be handled by setting e.Cancel to true.

{% tabs %}
{% highlight XAML %}

<syncfusion:DocumentContainer Name="DocContainer" Mode="MDI" MDIWindowStateChanging="DocContainer_MDIWindowStateChanging">

<FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Window1" >

</FlowDocumentScrollViewer>
<FlowDocumentScrollViewer syncfusion:DocumentContainer.Header="Window2" >

</FlowDocumentScrollViewer>

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
