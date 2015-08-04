---
layout: post
title: Dropdown-Popup
description: dropdown popup
platform: wpf
control: DateTimeEdit
documentation: ug
---

# Dropdown Popup

## Dropdown popup contains the following parts (Refer Control Structure):

* Calendar Button
* Clock Button
* None Button
* Calendar
* Clock
* Today Button

You can display the Dropdown Popup by checking the DropDown Button. The visibility of the DropDown popup can be enabled by setting the IsPopupEnabled property to true.

## Visibility of Popup Parts

* Calendar Button visibility can be enabled by setting the IsCalendarEnabled property to true. 
* Clock Button visibility can be enabled by setting the IsWatchEnabled property to true. 
* None Button visibility can be enabled by setting the IsEmptyDateEnabled property to true.



{% highlight html %}
XAML

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="230" Margin="10" EnableClassicStyle="True"                         IsCalendarEnabled="False" IsWatchEnabled="True"                          IsEmptyDateEnabled="True"/>

{% endhighlight %}

![](Dropdown-Popup_images/Dropdown-Popup_img1.png)





{% highlight html %}
XAML

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="230" Margin="10" EnableClassicStyle="True"                         IsCalendarEnabled="True" IsWatchEnabled="False"                          IsEmptyDateEnabled="True"/>

{% endhighlight  %}

![](Dropdown-Popup_images/Dropdown-Popup_img2.png)





{% highlight html %}
XAML
<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="230" Margin="10" EnableClassicStyle="True"                          IsCalendarEnabled="True" IsWatchEnabled="True"                          IsEmptyDateEnabled="False"/>
{% endhighlight %}


![](Dropdown-Popup_images/Dropdown-Popup_img3.png)




{% highlight html %}
XAML

<syncfusion:DateTimeEdit x:Name="dateTimeEdit" Height="25" Width="200" EnableClassicStyle="False" IsEmptyDateEnabled="True"                         DateTime="07/05/2010" Pattern="LongDate"/>

{% endhighlight  %}

![](Dropdown-Popup_images/Dropdown-Popup_img4.png)



## Working with DropDown Popup

By clicking the None Button you can set the null value to the DateTime property of the DateTimeEdit control. You can use the Calendar and Clock for changing the Date and Time of the DateTimeEdit control.

