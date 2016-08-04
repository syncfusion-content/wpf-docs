---
layout: post
title: Events and Methods | NavigationDrawer | WPF | Syncfusion
description: Events and Methods 
platform: WPF
control: NavigationDrawer
documentation: ug
---

# Events

The below two events are implemented in Transition.

* Opened
* Closed

## Opened

Opened event will be raised when the DrawerContentView is opened in NavigationDrawer.

 
  {% highlight c# %}

    public event DrawerEventHandler Opened;
        
   {% endhighlight %}

## Closed

Closed event will be raised when the DrawerContentView is closed in NavigationDrawer.


{% highlight c# %}

    public event DrawerEventHandler Closed;
	
{% endhighlight %}

# Methods

## Toggle Drawer

Represents the opening and closing of the navigation drawer


{% highlight c# %}

     drawer.ToggleDrawer();
	
{% endhighlight %}
