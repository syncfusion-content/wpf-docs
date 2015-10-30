---
layout: post
title: Tabbed Window | DockingManager | WPF | Syncfusion
description: Tabbed Window
platform: wpf
control: DockingManager
documentation: ug
---
# Tabbed Window

To make the children as Tabbed windows, you can use the TargetName and set the side value as `“Tabbed”` using the property `SideInDockedMode`.

![](TabbedWindow_images/TabbedWindow_img1.jpeg)


##  Tab alignments

The tabs of the Docked window are placed at the bottom, by default. To place the tabs of the docked window at different sides set the property `DockTabAlignment` with desired values such as `Top` , `Bottom` , `Left` and `Right`. 

* DockTabAlignment as `Bottom`

![](TabbedWindow_images/TabbedWindow_img2.jpeg)


* Setting `DockTabAlignment` as Left.
{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager1" DockTabAlignment="Left">

<ContentControl  x:Name="Content1" syncfusion:DockingManager.Header="Item1" /> <ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Item2"/>                                      syncfusion:DockingManager.SideInDockedMode="Tabbed"

syncfusion:DockingManager.TargetNameInDockedMode="Content1"/> 

</syncfusion:DockingManager>



{% endhighlight %}

![](TabbedWindow_images/TabbedWindow_img3.jpeg)


* Setting DockTabAlignment as Right

{% highlight xml %}
<syncfusion:DockingManager x:Name="DockingManager1" DockTabAlignment="Right">

<ContentControl  x:Name="Content1" syncfusion:DockingManager.Header="Item1"/>  

<ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Item2"                                       syncfusion:DockingManager.SideInDockedMode="Tabbed"

syncfusion:DockingManager.TargetNameInDockedMode="Content1"/>                                                                                                   </syncfusion:DockingManager>



{% endhighlight %}



![](TabbedWindow_images/TabbedWindow_img4.jpeg)


* Setting DockTabAlignment as Top
{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager1" DockTabAlignment="Top">

<ContentControl  x:Name="Content1" syncfusion:DockingManager.Header="Item1"/> 

<ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Item2"/>                                      syncfusion:DockingManager.SideInDockedMode="Tabbed"

syncfusion:DockingManager.TargetNameInDockedMode="Content1"/>  

</syncfusion:DockingManager>



{% endhighlight %}

![](TabbedWindow_images/TabbedWindow_img5.jpeg)


## Closing a Tabbed window

Tabbed window provides two different closing behaviors. They are `CloseActive` and `CloseAll` modes of `CloseTabs` property.

`CloseActive` – Used to close the active element of Tabbed window.

{% highlight xml %}
<syncfusion:DockingManager x:Name="DockingManager1" CloseTabs="CloseActive">

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1"/>  

<ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Item2"                                    syncfusion:DockingManager.SideInDockedMode="Tabbed"                                      syncfusion:DockingManager.TargetNameInDockedMode="Content1"/>  

<ContentControl x:Name="Content3" syncfusion:DockingManager.Header="Item3"                                       syncfusion:DockingManager.SideInDockedMode="Tabbed"                                       syncfusion:DockingManager.TargetNameInDockedMode="Content1"/>                         

</syncfusion:DockingManager>



{% endhighlight %}

 `CloseAll` – Used to close all the Tabbed window.

{% highlight xml %}
<syncfusion:DockingManager x:Name="DockingManager1" CloseTabs="CloseAll">

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Item1"/>  

<ContentControl x:Name="Content2" syncfusion:DockingManager.Header="Item2"                                    syncfusion:DockingManager.SideInDockedMode="Tabbed"                                      syncfusion:DockingManager.TargetNameInDockedMode="Content1"/>  

<ContentControl x:Name="Content3" syncfusion:DockingManager.Header="Item3"                                       syncfusion:DockingManager.SideInDockedMode="Tabbed"                                       syncfusion:DockingManager.TargetNameInDockedMode="Content1"/>                         

</syncfusion:DockingManager>



{% endhighlight %}
