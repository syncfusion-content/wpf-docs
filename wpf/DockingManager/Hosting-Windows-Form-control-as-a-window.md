
---
layout: post
title: Hosting Windows Form control as a window
description: Hosting Windows Form control as a window
platform: wpf
control: DockingManager
documentation: ug
---
## Hosting Windows Form control as a window

### Hosting a Windows Form control

DockingManager allows to host a WindowsForm control as a Docking Child 

{%highlight xml%}
<syncfusion:DockingManager x:Name="DockingManager1" DockFill="True"   ><WebBrowser Name="Web1"></syncfusion:DockingManager> Web1.Navigate("http://www.syncfusion.com/");

{%endhighlight%}

![](HostingWindowsFormcontrolasawindow_images/HostingWindowsFormcontrolasawindow_img1.jpeg)


### Interaction with control hosted by Win32 Host 

* While interacting the  WindowsForm control with WPF controls it leads to inaccessibility of WPF controls behind WindowsForm control, since the WindowsForm control will be on top. 
* While floating the WindowsForm control in DockingManager, it will not be visible. For these case , set **UseInteropCompatibilityMode** property as **True** for the DockingManager. 

{%highlight xml %}
<syncfusion:DockingManager x:Name="DockingManager1" DockFill="True" UseInteropCompatibilityMode="True"><WebBrowser Name="Web1"  ></syncfusion:DockingManager>
{%endhighlight%}
