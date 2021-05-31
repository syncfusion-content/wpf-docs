---
layout: post
title: Using the FullScreen mode | DockingManager | wpf | Syncfusion
description: using the fullscreen mode
platform: wpf
control: DockingManager
 documentation: ug
---

# Using the FullScreen mode

The FullScreen Mode is used to display the control in full screen. This will be effective while you use TDI Modes. The TabPanel will be hidden and visible on mouse roll-over. For this, you have TDIFullScreenMode property. This property is of type FullScreen mode which has following values.

### None:

This is the default value and does nothing.

### WindowMode:

This Mode window will be in full screen and the TabPanel will be hidden, and it will be visible only when the mouse roll-over is on top.

### ControlMode:

In this mode, full screen will be disabled and only the Tab panel will be hidden and visible only on mouse roll-over.

{% tabs %}

{% highlight xaml %}

<!-- To use Control Mode-->

<syncfusion:DockingManager UseDocumentContainer="True" TDIFullScreenMode="ControlMode"/>

<!-- None disables this feature-->

<syncfusion:DockingManager UseDocumentContainer="True" TDIFullScreenMode="None"/>

<!-- To use Window Mode-->

<syncfusion:DockingManager UseDocumentContainer="True" TDIFullScreenMode="WindowMode"/>

{% endhighlight  %}

{% highlight c# %}

//Disables this feature.

DockingManager.TDIFullScreenMode = FullScreenMode.None;

//To use controlMode.

DockingManager.TDIFullScreenMode = FullScreenMode.ControlMode;

//To use Window Mode.

DockingManager.TDIFullScreenMode = FullScreenMode.WindowMode;

{% endhighlight  %}

{% endtabs %}