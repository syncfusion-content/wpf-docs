---
layout: post
title: Handle-Navigation-Popup-Events
description: handle navigation popup events 
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

# Handle Navigation Popup Events 

Passing the argument “HierarchyNavigator item” in a method called ShowNavigationPopupItems can open the Navigation Popup for the corresponding item passed in the method.

{% highlight c# %}

HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();

hierarchyNavigator.ShowNavigationPopupItems(hierarchyitem);

{% endhighlight %}

#### NavigationPopupOpening

NavigationPopupOpening occurs when the navigation pop-up window is in the process of opening.

{% highlight xml %}
XAML
<syncfusion:HierarchyNavigator NavigationPopupOpening="NavigationPopupOpening"/></td></tr>
{% endhighlight %}

{% highlight c# %}
C#
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.NavigationPopupOpening +=new EventHandler(NavigationPopupOpening);
{% endhighlight %}

{% highlight c# %}
C#
private void NavigationPopupOpening(object sender, EventArgs e)
{
    //Occurs when Navigation Popup attempt to open
}
{% endhighlight %}

#### NavigationPopupOpened

NavigationPopupOpened occurs when the navigation pop-up window is open.

{% highlight xml %}
XAML
<syncfusion:HierarchyNavigator NavigationPopupOpened="NavigationPopupOpened"/>

{% endhighlight %}
{% highlight c# %}

C#
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.NavigationPopupOpened += new EventHandler(NavigationPopupOpened);

{% endhighlight %}

{% highlight c# %}
C#
private void NavigationPopupOpened(object sender, EventArgs e)
{
    //Occurs when Navigation Popup is opened
}
{% endhighlight %}

#### NavigationPopupClosing

NavigationPopupClosing occurs when the navigation pop-up window is closing.

{% highlight xml %}

XAML
<syncfusion:HierarchyNavigator NavigationPopupClosing="NavigationPopupClosing"/>
{% endhighlight %}

{% highlight c# %}
C#
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.NavigationPopupClosing +=new EventHandler(NavigationPopupClosing);
{% endhighlight %}

{% highlight c# %}
C#
private void NavigationPopupClosing(object sender, EventArgs e)
{
    //Occurs when Navigation Popup is Closing
}
{% endhighlight %}

#### NavigationPopupClosed 

NavigationPopupClosed occurs when the navigation pop-up window is closed.

{% highlight xml %}
XAML
<syncfusion:HierarchyNavigator NavigationPopupClosing="NavigationPopupClosing"/>

{% endhighlight %}

{% highlight c# %}
C#
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
hierarchyNavigator.NavigationPopupClosing +=new EventHandler(NavigationPopupClosing);
{% endhighlight %}


{% highlight c# %}
C#
private void NavigationPopupClosing(object sender, EventArgs e)
{ 
   //Occurs when Navigation Popup is Closing
}
{% endhighlight %}


