---
layout: post
title: How to handle navigation popups in WPF Hierarchical Navigator | Syncfusion
description: Learn how to handle navigation popup events in Syncfusion® WPF Hierarchical Navigator control, including opening, opened, closing, and closed events.
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# How to handle navigation popup events in WPF Hierarchical Navigator

You can open the navigation popup programmatically by passing a `HierarchyNavigatorItem` to the `ShowNavigationPopupItems` method.

{% highlight c# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.ShowNavigationPopupItems(hierarchyItem);
{% endhighlight %}

### NavigationPopupOpening

The `NavigationPopupOpening` event occurs when the navigation popup is about to open.

{% tabs %}
{% highlight xaml %}
<syncfusion:HierarchyNavigator
    NavigationPopupOpening="NavigationPopupOpening" />
{% endhighlight %}

{% highlight c# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.NavigationPopupOpening += NavigationPopupOpening;

private void NavigationPopupOpening(object sender, EventArgs e)
{
    // Occurs when the navigation popup is about to open.
}
{% endhighlight %}
{% endtabs %}

### NavigationPopupOpened

The `NavigationPopupOpened` event occurs after the navigation popup has been opened.

{% tabs %}
{% highlight xaml %}
<syncfusion:HierarchyNavigator
    NavigationPopupOpened="NavigationPopupOpened" />
{% endhighlight %}

{% highlight c# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.NavigationPopupOpened += NavigationPopupOpened;

private void NavigationPopupOpened(object sender, EventArgs e)
{
    // Occurs when the navigation popup is opened.
}
{% endhighlight %}
{% endtabs %}

### NavigationPopupClosing

The `NavigationPopupClosing` event occurs when the navigation popup is about to close.

{% tabs %}
{% highlight xaml %}
<syncfusion:HierarchyNavigator
    NavigationPopupClosing="NavigationPopupClosing" />
{% endhighlight %}

{% highlight c# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.NavigationPopupClosing += NavigationPopupClosing;

private void NavigationPopupClosing(object sender, EventArgs e)
{
    // Occurs when the navigation popup is about to close.
}
{% endhighlight %}
{% endtabs %}

### NavigationPopupClosed

The `NavigationPopupClosed` event occurs after the navigation popup has been closed.

{% tabs %}
{% highlight xaml %}
<syncfusion:HierarchyNavigator
    NavigationPopupClosed="NavigationPopupClosed" />
{% endhighlight %}

{% highlight c# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.NavigationPopupClosed += NavigationPopupClosed;

private void NavigationPopupClosed(object sender, EventArgs e)
{
    // Occurs when the navigation popup is closed.
}
{% endhighlight %}
{% endtabs %}