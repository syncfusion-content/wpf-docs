---
layout: post
title: Handle Navigation Popup in WPF Hierarchical Navigator | Syncfusion
description: Handle navigation popup events in Syncfusion Essential Studio WPF Hierarchy Navigator control, its elements and more.
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

{% tabs %}
{% highlight xaml %}
<syncfusion:HierarchyNavigator NavigationPopupOpening="NavigationPopupOpening"/>
{% endhighlight %}
{% highlight c# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
<br>hierarchyNavigator.NavigationPopupOpening +=new EventHandler(NavigationPopupOpening);

private void NavigationPopupOpening(object sender, EventArgs e)<br>
{
<br>
    //Occurs when Navigation Popup attempt to open
<br>
}
{% endhighlight %}
{% endtabs %}

### NavigationPopupOpened

NavigationPopupOpened occurs when the navigation pop-up window is open.

{% tabs %}
{% highlight xaml %}

<syncfusion:HierarchyNavigator NavigationPopupOpened="NavigationPopupOpened"/>

HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();<br>hierarchyNavigator.NavigationPopupOpened += new EventHandler(NavigationPopupOpened);
{% endhighlight %}
{% highlight c# %}
private void NavigationPopupOpened(object sender, EventArgs e)<br>
{
<br>
    //Occurs when Navigation Popup is opened
}
{% endhighlight  %}
{% endtabs %}

### NavigationPopupClosing

NavigationPopupClosing occurs when the navigation pop-up window is closing.

{% tabs %}
{% highlight xaml %}
<syncfusion:HierarchyNavigator NavigationPopupClosing="NavigationPopupClosing"/>
{% endhighlight %}
{% highlight c# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
<br>hierarchyNavigator.NavigationPopupClosing +=new EventHandler(NavigationPopupClosing);

private void NavigationPopupClosing(object sender, EventArgs e)<br>
{<br>    
//Occurs when Navigation Popup is Closing
}
{% endhighlight %}
{% endtabs %}

### NavigationPopupClosed 

NavigationPopupClosed occurs when the navigation pop-up window is closed.

{% tabs %}
{% highlight xaml %}
<syncfusion:HierarchyNavigator NavigationPopupClosing="NavigationPopupClosing"/>
{% endhighlight  %}
{% highlight c# %}
HierarchyNavigator hierarchyNavigator = new HierarchyNavigator();
<br>
hierarchyNavigator.NavigationPopupClosing +=new EventHandler(NavigationPopupClosing);

private void NavigationPopupClosing(object sender, EventArgs e)<br>
{<br>  
  //Occurs when Navigation Popup is Closing
}

{% endhighlight %}
{% endtabs %}

