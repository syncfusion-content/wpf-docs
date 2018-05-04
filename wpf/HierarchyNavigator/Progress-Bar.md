---
layout: post
title: Progress Bar| Hierarchical Navigator | Wpf | Syncfusion
description: progress bar
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Progress Bar

The progress bar for the HierarchyNavigator control can be displayed or removed.

![](Progress-Bar_images/Progress-Bar_img1.png)



There are two methods to display the progress bar:

1. Calling the ShowProgressBar method in HierarchyNavigator, which displays the progress bar for a time span of 500 ms.

{% tabs %}
{% highlight c# %}

HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.ShowProgressBar();

{% endhighlight %}
{% endtabs %}

2. Passing an argument in the method to show a specified time span.  The image below shows a time span of 1000 ms that has been passed.

{% tabs %}
{% highlight c# %}

HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.ShowProgressBar(new TimeSpan(0, 0, 0, 0, 1000));

{% endhighlight %}
{% endtabs %}

The progress bar can be canceled by using two methods:

1. Calling the CancelProgressBar method in HierarchyNavigator.

{% tabs %}
{% highlight c# %}

HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.CancelProgressBar();

{% endhighlight %}
{% endtabs %}

2. Passing an argument in the method to cancel the progress bar within a particular span of time. This method helps users cancel the progress bar when preferred. The image displayed below shows a time span of 1000 ms that has been passed.

{% tabs %}
{% highlight c# %}

HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.CancelProgressBar(new TimeSpan(0, 0, 0, 0, 1000));

{% endhighlight %}
{% endtabs %}
