---
layout: post
title: Getting Started with Syncfusion ToolBarAdv control for WPF
description: A quick tour to initial users on Syncfusion ToolBarAdv control for WPF
platform: wpf
control: ToolBarAdv
documentation: ug
---

# Getting Started

>**Important**
Starting with v16.2.0.x, if you refer to Syncfusion assemblies from trial setup or from the NuGet feed, include a license key in your projects. Refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to learn about registering Syncfusion license key in your WPF application to use our components.

This section explains how to add the ToolBarAdv control to an application and its structure.

## Adding ToolBarAdv to a WPF Application

ToolBarAdv can be added to an application in a following way.

### Create the ToolBarAdv Control to an application by using XAML:

The following ways explains how to add ToolBarAdv control using XAML code:

* Create a WPF project in Visual Studio and refer “Syncfusion.Shared.Wpf” assembly to the project.    
* Include an XML namespace for the above assemblies to the Main window.

{% tabs %}

{% highlight XAML %}

<Window x:Class="Application_New.MainWindow"

xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

xmlns:syncfusion="http://schemas.syncfusion.com/wpf"

Title="MainWindow" Height="350" Width="525">



{% endhighlight %}

{% endtabs %}
* Now add the ToolBarAdv control with a required optimal name using the namespace 

{% tabs %}

{% highlight XAML %}

<syncfusion:ToolBarAdv Height="100" HorizontalAlignment="Left" Margin="92,90,0,0" Name="toolBarAdv1" VerticalAlignment="Top" Width="200" />



{% endhighlight %}

{% endtabs %}

### Create the ToolBarAdv control to an application by C#:

{% tabs %}

{% highlight C# %}

ToolBarAdv tool = new ToolBarAdv();

tool.Name = "toolBarAdv1";

tool.Width = 100;

tool.Height = 50;





{% endhighlight %}

{% endtabs %}

## Appearance and Structure of the Control

![](Getting-Started-images/Getting-Started-img1.jpeg)


* The Overflow button is a toggle button that displays on clicking the Overflow panel.
* The Gripper is used to drag the ToolBarAdv to change its Band. The state of the ToolBarAdv can be changed to float and dock by clicking the gripper and dragging the ToolBarAdv, when the ToolBarAdv is hosted in ToolBarManager.

## Properties

### Properties of ToolBarAdv

<table>
<tr>
<td>
Property<br/><br/></td><td>
Description<br/><br/></td><td>
Type<br/><br/></td><td>
Data Type<br/><br/></td></tr>
<tr>
<td>
Band<br/><br/></td><td>
Gets or sets a value indicating where the ToolBarAdv should be placed in the ToolBarTrayAdv.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Int<br/><br/></td></tr>
<tr>
<td>
BandIndex<br/><br/></td><td>
Gets or sets the band index number indicating the position of the ToolBarAdv on the band.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Int<br/><br/></td></tr>
<tr>
<td>
ToolBarName<br/><br/></td><td>
Gets or sets the name of the ToolBarAdv.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
String<br/><br/></td></tr>
<tr>
<td>
GripperVisibility<br/><br/></td><td>
Gets or sets a value indicating whether gripper can be visible.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Bool<br/><br/></td></tr>
<tr>
<td>
FloatingBarLocation<br/><br/></td><td>
Gets or sets the location for the floating ToolBarAdv.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Point<br/><br/></td></tr>
<tr>
<td>
ControlsResourceDictionary<br/><br/></td><td>
Gets or sets resource dictionary in which ToolBarAdv will look up for Framework element’s styles.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Resource Dictionary<br/><br/></td></tr>
<tr>
<td>
IsOverflowOpen<br/><br/></td><td>
Gets or sets a value indicating whether overflow popup is open.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Bool<br/><br/></td></tr>
<tr>
<td>
ToolBarItemInfoCollection<br/><br/></td><td>
Gets or sets the items to be displayed in the Add or Remove Buttons popup.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
ObservableCollection<br/><br/></td></tr>
<tr>
<td>
IsOverflowItem<br/><br/></td><td>
Gets or sets a value indicating whether an item can be displayed in overflow panel.<br/><br/></td><td>
Attached Property<br/><br/></td><td>
Bool<br/><br/></td></tr>
<tr>
<td>
OverflowMode<br/><br/></td><td>
Gets or sets an overflow mode for a specified item.<br/><br/></td><td>
Attached Property<br/><br/></td><td>
OverflowMode<br/><br/></td></tr>
<tr>
<td>
Icon<br/><br/></td><td>
Gets or sets an icon for specified item to be displayed in the Add or Remove Buttons menu.<br/><br/></td><td>
Attached Property<br/><br/></td><td>
ImageSource<br/><br/></td></tr>
<tr>
<td>
Label<br/><br/></td><td>
Gets or sets a label for specified item to be displayed in the Add or Remove Buttons menu.<br/><br/></td><td>
Attached Property<br/><br/></td><td>
String<br/><br/></td></tr>
<tr>
<td>
IsAvailable<br/><br/></td><td>
Gets or sets a value indicating whether a specified item should be hidden.<br/><br/></td><td>
Attached Property<br/><br/></td><td>
Boolean<br/><br/></td></tr>
</table>
### Properties of ToolBarManager

<table>
<tr>
<td>
Property<br/><br/></td><td>
Description<br/><br/></td><td>
Type<br/><br/></td><td>
Data Type<br/><br/></td></tr>
<tr>
<td>
IsLocked<br/><br/></td><td>
Gets or Sets a value indicating whether ToolBarTrayAdv is locked.<br/><br/></td><td>
Dependency property<br/><br/></td><td>
bool<br/><br/></td></tr>
<tr>
<td>
Orientation<br/><br/></td><td>
Gets or Sets the orientation of the ToolBarAdv.<br/><br/></td><td>
Dependency property<br/><br/></td><td>
Orientation<br/><br/></td></tr>
<tr>
<td>
ToolBars<br/><br/></td><td>
Gets or sets toolbars.<br/><br/></td><td>
Dependency property<br/><br/></td><td>
ObservableCollection<br/><br/></td></tr>
<tr>
<td>
TopToolBarTray<br/><br/></td><td>
Gets or sets ToolBarTrayAdv which has to be displayed at the Top of ToolBarManager.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
ToolBarTrayAdv<br/><br/></td></tr>
<tr>
<td>
BottomToolBarTray<br/><br/></td><td>
Gets or sets ToolBarTrayAdv which has to be displayed at the bottom of ToolBarManager.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
ToolBarTrayAdv<br/><br/></td></tr>
<tr>
<td>
LeftToolBarTray<br/><br/></td><td>
Gets or sets ToolBarTrayAdv which has to be displayed at the left of ToolBarManager.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
ToolBarTrayAdv<br/><br/></td></tr>
<tr>
<td>
RightToolBarTray<br/><br/></td><td>
Gets or sets ToolBarTrayAdv which has to be displayed at the right of ToolBarManager.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
ToolBarTrayAdv<br/><br/></td></tr>
<tr>
<td>
CanDockAtTop<br/><br/></td><td>
Gets or sets a value indicating whether toolbar can be docked at the top.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
bool<br/><br/></td></tr>
<tr>
<td>
CanDockAtBottom<br/><br/></td><td>
Gets or sets a value indicating whether toolbar can be docked at the bottom.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
bool<br/><br/></td><td>
<tr>
<td>
CanDockAtLeft<br/><br/></td><td>
Gets or sets a value indicating whether toolbar can be docked at the left.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
bool<br/><br/></td><td>
<tr>
<td>
CanDockAtRight<br/><br/></td><td>
Gets or sets a value indicating whether toolbar can be docked at the right.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
bool<br/><br/></td><td>
<tr>
<td>
Content<br/><br/></td><td>
Gets or sets the content of the ToolBarManager.<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
UIElement<br/><br/></td><td>
<tr>
<td>
FloatingToolBarStyle<br/><br/></td><td>
Gets or sets a style of floating tool bar<br/><br/></td><td>
Dependency Property<br/><br/></td><td>
Style<br/><br/></td><td>
<tr>
<td>
ToolBarState<br/><br/></td><td>
Gets or sets the state of the toolbar.<br/><br/></td><td>
Attached Property<br/><br/></td><td>
ToolBarState<br/><br/></td><td>



