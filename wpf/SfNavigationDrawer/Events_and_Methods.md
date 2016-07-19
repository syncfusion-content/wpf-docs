---
layout: post
title: Events and Methods | NavigationDrawer | WPF | Syncfusion
description: Events and Methods 
platform: WPF
control: NavigationDrawer
documentation: ug
---

#Events

The below two events are implemented in Transition.

* Opened
* Closed

##Opened

Opened event will be raised when the drawercontentview is opened in NavigationDrawer.

  {% tabs %}

  {% highlight c# %}

    public event DrawerEventHandler Opened;
        
   {% endhighlight %}

   {% endtabs %}

##Closed

Closed event will be raised when the drawercontentview is closed in NavigationDrawer.

{% tabs %}

{% highlight c# %}

    public event DrawerEventHandler Closed;
	
{% endhighlight %}

{% endtabs %}

#Methods

##Toggle Drawer

Represents the opening and closing of the navigation drawer

{% tabs %}

{% highlight c# %}

     drawer.ToggleDrawer();
	
{% endhighlight %}

{% endtabs %}
