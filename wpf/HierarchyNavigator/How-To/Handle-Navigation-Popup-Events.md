---
layout: post
title: Handle-Navigation-Popup-Events
description: handle navigation popup events 
platform: wpf
control: Hierarchical Navigator
documentation: ug
---

## Handle Navigation Popup Events 

Passing the argument “HierarchyNavigator item” in a method called ShowNavigationPopupItems can open the Navigation Popup for the corresponding item passed in the method.

{% highlight c# %}



HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();

hierarchyNavigator.ShowNavigationPopupItems(hierarchyitem);
{% endhighlight  %}

### NavigationPopupOpening

NavigationPopupOpening occurs when the navigation pop-up window is in the process of opening.

{% highlight xml %}
<syncfusion:HierarchyNavigator NavigationPopupOpening="NavigationPopupOpening"/>
{% endhighlight %}
{% highlight c# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();<br>hierarchyNavigator.NavigationPopupOpening +=new EventHandler(NavigationPopupOpening);

private void NavigationPopupOpening(object sender, EventArgs e)<br>{<br>    //Occurs when Navigation Popup attempt to open<br>}
{% endhighlight %}

### NavigationPopupOpened

NavigationPopupOpened occurs when the navigation pop-up window is open.
{% highlight xml %}

<syncfusion:HierarchyNavigator NavigationPopupOpened="NavigationPopupOpened"/>

HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();<br>hierarchyNavigator.NavigationPopupOpened += new EventHandler(NavigationPopupOpened);
{% endhighlight %}
{% highlight c# %}
private void NavigationPopupOpened(object sender, EventArgs e)<br>{<br>    //Occurs when Navigation Popup is opened}
{% endhighlight  %}

### NavigationPopupClosing

NavigationPopupClosing occurs when the navigation pop-up window is closing.

{% highlight xml %}
<syncfusion:HierarchyNavigator NavigationPopupClosing="NavigationPopupClosing"/>
{% endhighlight %}
{% highlight c# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();<br>hierarchyNavigator.NavigationPopupClosing +=new EventHandler(NavigationPopupClosing);

private void NavigationPopupClosing(object sender, EventArgs e)<br>{<br>    //Occurs when Navigation Popup is Closing}
{% endhighlight %}

### NavigationPopupClosed 

NavigationPopupClosed occurs when the navigation pop-up window is closed.

{% highlight xml %}
<syncfusion:HierarchyNavigator NavigationPopupClosing="NavigationPopupClosing"/>
{% endhighlight  %}
{% highlight c# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();<br>hierarchyNavigator.NavigationPopupClosing +=new EventHandler(NavigationPopupClosing);

C#private void NavigationPopupClosing(object sender, EventArgs e)<br>{<br>    //Occurs when Navigation Popup is Closing}

{% endhighlight %}

