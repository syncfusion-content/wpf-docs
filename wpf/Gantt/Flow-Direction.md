---
layout: post
title: Flow Direction| Gantt | Wpf | Syncfusion
description: The following section describes the flow direction support in Gantt Control.
platform: wpf
control: Gantt
documentation: ug
---

# Flow Direction Support

Gantt provides support to display the contents of the Gantt from right-to-left or left-to-right. It can be achieved by setting the `FlowDirection` property of the Gantt control to "RightToLeft" or "LeftToRight". The following code sample explains how to set this property.

{% tabs %}

{% highlight xaml %}

<Sync:GanttControl x:Name="Gantt" ItemsSource="{Binding GanttItemSource}" FlowDirection="RightToLeft"/>

{% endhighlight %}

{% highlight c# %}
 
this.gantt.FlowDirection = System.Windows.FlowDirection.RightToLeft;

{% endhighlight %}

{% endtabs %}

![](Flow-Direction-Images/Right-To-Left.png)
