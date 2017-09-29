---
layout: post
title: Flow Direction| Gantt | Wpf | Syncfusion
description: The following section describes the flow direction support in Gantt control.
platform: wpf
control: Gantt
documentation: ug
---

# Flow Direction

Gantt provides support to display the contents from right-to-left or left-to-right direction. It can be achieved by setting the `FlowDirection` property value as “RightToLeft” or “LeftToRight” in the Gantt control. The following code sample explains how to set this property.

{% tabs %}

{% highlight xaml %}

<Sync:GanttControl x:Name="Gantt" ItemsSource="{Binding GanttItemSource}" FlowDirection="RightToLeft"/>

{% endhighlight %}

{% highlight c# %}
 
this.Gantt.FlowDirection = System.Windows.FlowDirection.RightToLeft;

{% endhighlight %}

{% endtabs %}

![](Flow-Direction-Images/Right-To-Left.png)
