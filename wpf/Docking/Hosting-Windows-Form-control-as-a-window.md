---
layout: post
title: Hosting Windows Form control | DockingManager | WPF | Syncfusion
description: Learn how to host Windows Forms control as a child window of DockingManager 
platform: wpf
control: DockingManager
documentation: ug
---
# Hosting Windows Form control as a window

## Hosting a Windows Form control

DockingManager allows to host a WindowsForm control as a Docking Child. Here a Windows Forms WebBrowser control added as Child Window

{% tabs %}

{%highlight XAML%}

<syncfusion:DockingManager x:Name="DockingManager1" DockFill="True" >

<WebBrowser Name="Web1" />

</syncfusion:DockingManager> 

{% endhighlight %}

{% highlight C# %}

WebBrowser web1 = new WebBrowser();

web1.Name = "Web1";

dock.Children.Add(web1);

Web1.Navigate("http://www.syncfusion.com/downloads/metrostudio");

{% endhighlight %}

{% endtabs %}

![Hosting a windows form control](HostingWindowsFormcontrolasawindow_images/HostingWindowsFormcontrolasawindow_img1.jpeg)


## Interaction with control hosted by Win32 Host 

* While interacting the  WindowsForm control with WPF controls, it leads to inaccessibility of WPF controls behind WindowsForm control, since the WindowsForm control is on top. 
* While floating the WindowsForm control in DockingManager, it is  invisible. For these cases, set [UseInteropCompatibilityMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_UseInteropCompatibilityMode) property as `True` for the DockingManager. 

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" DockFill="True" UseInteropCompatibilityMode="True">

<WebBrowser Name="Web1" />

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

DockingManager1.UseInteropCompatibilityMode = true;

{% endhighlight %}

{% endtabs %}