---
layout: post
title: Events
description: events
platform: wpf
control: DropDownButtonAdv
documentation: ug
---

# Events

The DropDownButtonAdv control comprises the following events:

###DropDownOpening

This event occurs before opening the DropDown.

The following code adds the DropDownOpening event handler to the DropDownButtonAdv control:



<table>
<tr>
<td>
{% highlight xml %} <shared:DropDownButtonAdv DropDownOpening="DropDownButtonAdv_DropDownOpening"/>{% endhighlight %}</td></tr>
<tr>
<td>
{% highlight C# %} DropDownButtonAdv button = new DropDownButtonAdv();button.DropDownOpening +=new CancelEventHandler(button_DropDownOpening);{% endhighlight %}</td></tr>
</table>


###DropDownOpened

This event occurs after opened the DropDown.

The following code adds the DropDownOpened event handler to the DropDownButtonAdv control:



<table>
<tr>
<td>
{% highlight xml %}<shared:DropDownButtonAdv DropDownOpened="DropDownButtonAdv_DropDownOpened"/> {% endhighlight %} </td></tr>
<tr>
<td>
{% highlight C# %} DropDownButtonAdv button = new DropDownButtonAdv();button.DropDownOpened +=new RoutedEventHandler(button_DropDownOpened); {% endhighlight %} </td></tr>
</table>


###DropDownClosing

This event occurs before closing the DropDown.

The following code adds the DropDownClosing event handler to the DropDownButtonAdv control:



<table>
<tr>
<td>
{% highlight xml %} <shared:DropDownButtonAdv DropDownClosing="DropDownButtonAdv_DropDownClosing"/>{% endhighlight %}</td></tr>
<tr>
<td>
{% highlight C# %} DropDownButtonAdv button = new DropDownButtonAdv();button.DropDownClosing +=new CancelEventHandler(button_DropDownClosing);{% endhighlight %}</td></tr>
</table>

###DropDownClosed 

This event occurs after closed the DropDown.

The following code adds the DropDownClosed event handler to the DropDownButtonAdv control:



<table>
<tr>
<td>
{% highlight xml %} <shared:DropDownButtonAdv DropDownClosed="DropDownButtonAdv_DropDownClosed"/> {% endhighlight %} </td></tr>
<tr>
<td>
{% highlight C# %} DropDownButtonAdv button = new DropDownButtonAdv();button.DropDownClosed +=new RoutedEventHandler(button_DropDownClosed); {% endhighlight %} </td></tr>
</table>


