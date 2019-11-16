---
layout: post
title: Events| DropDownButtonAdv | Wpf | Syncfusion
description: events
platform: wpf
control: DropDownButtonAdv
documentation: ug
---

# Events

The DropDownButtonAdv control comprises the following events:

## DropDownOpening

This event occurs before opening the DropDown.

The following code adds the DropDownOpening event handler to the DropDownButtonAdv control:


{% tabs %}
{% highlight xaml %} 
<shared:DropDownButtonAdv DropDownOpening="DropDownButtonAdv_DropDownOpening"/>
{% endhighlight %}

{% highlight C# %} 
DropDownButtonAdv button = new DropDownButtonAdv();
button.DropDownOpening +=new CancelEventHandler(button_DropDownOpening);
{% endhighlight %}
{% endtabs %}


## DropDownOpened

This event occurs after opened the DropDown.

The following code adds the DropDownOpened event handler to the DropDownButtonAdv control:



{% tabs %}
{% highlight xaml %}
<shared:DropDownButtonAdv DropDownOpened="DropDownButtonAdv_DropDownOpened"/> 
{% endhighlight %}

{% highlight C# %} 
DropDownButtonAdv button = new DropDownButtonAdv();
button.DropDownOpened +=new RoutedEventHandler(button_DropDownOpened); 
{% endhighlight %} 
{% endtabs %}


## DropDownClosing

This event occurs before closing the DropDown.

The following code adds the DropDownClosing event handler to the DropDownButtonAdv control:



{% tabs %}
{% highlight xaml %} 
<shared:DropDownButtonAdv DropDownClosing="DropDownButtonAdv_DropDownClosing"/>
{% endhighlight %}

{% highlight C# %} 
DropDownButtonAdv button = new DropDownButtonAdv();
button.DropDownClosing +=new CancelEventHandler(button_DropDownClosing);
{% endhighlight %}
{% endtabs %}

## DropDownClosed 

This event occurs after closed the DropDown.

The following code adds the DropDownClosed event handler to the DropDownButtonAdv control:


{% tabs %}
{% highlight xaml %} 
<shared:DropDownButtonAdv DropDownClosed="DropDownButtonAdv_DropDownClosed"/> 
{% endhighlight %} 

{% highlight C# %} 
DropDownButtonAdv button = new DropDownButtonAdv();
button.DropDownClosed +=new RoutedEventHandler(button_DropDownClosed); 
{% endhighlight %} 
{% endtabs %}


