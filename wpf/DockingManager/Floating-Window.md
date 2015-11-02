---
layout: post
title: Floating Window | DockingManager | WPF | Syncfusion
description: Floating Window
platform: wpf
control: DockingManager
documentation: ug
---
# Floating Window

Floating window is one of the states in the DockingManager. To make children of the DockingManager as `Float`, set its `state` values as `Float`.

Floating window is like a Popup window and it has some limitation in resizing. To avoid this limitation, set the `UseNativeFloatWindow` property for the DockingManager as `True`.

{% highlight xml %}
<syncfusion:DockingManager UseNativeFloatWindow="True">

<ContentControl syncfusion:DockingManager.Header="Item1" syncfusion:DockingManager.State="Float"/>

</syncfusion:DockingManager>



{% endhighlight %}

![](FloatingWindow_images/FloatingWindow_img1.jpeg)


## Rolling Up support

The float window is rolled up to top using the property `IsRollUpTopProperty`. To enable this functionality set its value as `True`, by default its value is `False`.        

{% highlight xml %}
<syncfusion:DockingManager IsRollupFloatWindow="True">

<ContentControl syncfusion:DockingManager.Header="Item1" syncfusion:DockingManager.State="Float"/>

</syncfusion:DockingManager>

{% endhighlight %}

![](FloatingWindow_images/FloatingWindow_img2.jpeg)


## Multiple Monitor functionalities

The default behavior of the float window remains as Popup in the DockingManager. 

On using MultiMonitor scenario, the FloatWindow behavior as follows:

* FloatWindow can be resized both in primary and secondary monitor.
* On showing half of the float window between primary and secondary monitor, the float window remains in half between the monitor while plugged in and plugged out of the secondary monitor.
* When float window is moved to secondary monitor from primary monitor, the float window remains at the secondary monitor itself while plugged in.

### Making the same behavior like WPF window for Float Window in Multiple Monitor

To make float window behave like a WPF window in multiple monitor, set the property `UseNativeFloatWindow` as `True`. 

On using MultiMonitor scenario, the FloatWindow behavior as follows:

* NativeFloatWindow can be resized both in primary and secondary monitor.
* On showing half of the NativeFloatWindow between primary and in secondary monitor, the NativeFloatWindow remains at the left side in primary monitor while plugged in and plugged out of the secondary monitor.
* When NativeFloatWindow is moved to secondary monitor from primary monitor, it remains at the primary monitor itself while plugged in and plugged out.

## Enabling and Disabling the float functionality


The `CanFloat` property helps to enable or disable the floating functionality by setting its value as `True` or `False` respectively. By default its value is `True`, to disable this functionality turn its value to `False`.

{% highlight xml %}
<syncfusion:DockingManager x:Name="DockingManager1" >

<ContentControl syncfusion:DockingManager.Header="Item1" syncfusion:DockingManager.CanFloat="True"/>

<ContentControl syncfusion:DockingManager.Header="Item2" syncfusion:DockingManager.CanFloat="False"/>

</syncfusion:DockingManager>



{% endhighlight %}

![](FloatingWindow_images/FloatingWindow_img3.jpeg)


## Enabling and Disabling the float functionality Operation on Double Click

The float window changes its state to `Dock` when you double click its header by default. To disable this functionality for the specific child, set `NoDock` property as `True`.       

{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager1">

<ContentControl syncfusion:DockingManager.Header="Item1" x:Name="Content1" 
                syncfusion:DockingManager.State="Float" syncfusion:DockingManager.NoDock="True"/>                      

</syncfusion:DockingManager>



{% endhighlight %}

## Maximize/Minimize Support

The float window provides Minimize or Maximize support for better usability. This support can be achieved through the property `UseNativeFloatWindow` 

* It helps a particular Float window to provide a maximized view.
* It can minimize a Float window and can be restored when needed.


### Enabling Maximization feature


To enable the maximizing feature for the Float window, set `CanFloatMaximize` for the specific child and `UseNativeFloatWindow` as `True`.By default, its value is `False`.

{% highlight xml %}
<syncfusion:DockingManager UseNativeFloatWindow="True">

<ContentControl syncfusion:DockingManager.Header="Item1" x:Name="Content1" 
                syncfusion:DockingManager.State="Float" syncfusion:DockingManager.CanFloatMaximize="True"/>    

</syncfusion:DockingManager>



{% endhighlight %}

![](FloatingWindow_images/FloatingWindow_img4.jpeg)


## Positioning on desire location

The FloatWindow can be placed at any desired location. To position the FloatWindow at the desired location with the required Rect Bounds, call `SetFloatingWindowRect` method of the DockingManager.



{% highlight c# %}

DockingManager.SetFloatingWindowRect(Content1,new Rect(200,200,200,200));





{% endhighlight %}

![](FloatingWindow_images/FloatingWindow_img5.jpeg)


