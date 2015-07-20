---
layout: post
title: Other-Features
description: other features
platform: wpf
control: DockingManager
documentation: ug
---

# Other Features

## Using Adorner Drag Provider and Adorner FloatWindow

There are two ways to display the Drag provider in DockingManager. One is to display it as a popup, which is default and the other is to display it in an adorner layer for this you need to set UseAdornerDragProvider=true to display the Drag provider as Adorner layer.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager Name="DockingManager"  UseAdornerDragProvider="True"&gt;&lt;Grid/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.UseAdornerDragProvider = true;</td></tr>
</table>


Simlarly, Float child can be displayed in two ways.  One is using the popup and another is using the adorner layer. The Adorner Float window is enabled by setting UseAdornerFloatWindow=true.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager Name="DockingManager" UseAdornerFloatWindow="True"&gt;  &lt;Grid/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.UseAdornerFloatWindow = true;</td></tr>
</table>


## ActiveWindow Changed Event

The ActiveWindowChanged event is raised whenever the ActiveWindow property of DockingManager is changed. This event is used whenever you need to track the change in ActiveChild and do some content changes to the child. The following example demonstrates the changing of the Child header, based on the ActiveWindow.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager Name="DockingManager" ActiveWindowChanged="DockingManager_ActiveWindowChanged"&gt;            &lt;Grid/&gt;            &lt;Grid/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]//Changing the ActiveWindow Header based on activewindow changeprivate void DockingManager_ActiveWindowChanged(DependencyObject d, DependencyPropertyChangedEventArgs e){     if (e.NewValue != null)     {       FrameworkElement element = e.NewValue as FrameworkElement;       DockingManager.SetHeader(element, "Active");     }     if (e.OldValue != null)     {       FrameworkElement element = e.OldValue as FrameworkElement;       DockingManager.SetHeader(element, "");     }}    </td></tr>
</table>


## AutoHide Animation Start /Stop Events

AutoHideAnimationStart event will raise whenever you click on the AWL autohide button. Similarly AutohideAnimationStop is raised after AutohideAnimationStart indicates that animation is completed. You can use these events to update the relevant information in UI or to do some UI related manipulations.

## AutoHide Visibility

CanAutoHide property is used to enable and disable the Autohidden state of children. When CanAutoHide=False, the AWL AutoHidden button will be hidden.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager Name="DockingManager"&gt;  &lt;Grid Name="grid1" syncfusion:DockingManager.CanAutoHide="False"/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetCanAutoHide(grid1, false);</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/CanAutoHiddenflase.jpg](Other-Features_images/Other-Features_img1.jpeg) | markdownify }
{:.image }


## Enabling/Disabling Animation on mouse over for auto hide

By default, whenever you move your mouse over the AutoHidden tab, the autohide animation will start. You can disable this behavior by setting the IsAutoHideAnimationOnMouseOver=true so that when you move the mouse over the autohide tab it does not start the Autohide animation.  But it will make you click the autohide tab to start autohide animation.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager Name="DockingManager" IsAnimationEnabledOnMouseOver="True" &gt;   &lt;Grid/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.IsAnimationEnabledOnMouseOver = true;</td></tr>
</table>


## AutoHide Animation Delay

You can control the animation speed of autohide by using the AnimationDelay property as given below :



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager Name="DockingManager" IsAnimationEnabledOnMouseOver="True" &gt;  &lt;Grid syncfusion:DockingManager.AnimationDelay="100"/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]Duration dur = new Duration(new TimeSpan(100));DockingManager.SetAnimationDelay(element, dur);</td></tr>
</table>
## Events for ContextMenu and BeforeOpen

BeforeContextMenuOpen – When the user right clicks on the header of the Docked Child, this can be used to initiate the various actions before the context menu open.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager Name="DockingManager"  BeforeContextMenuOpen="DockingManager_BeforeContextMenuOpen"&gt;    &lt;Grid/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]private void DockingManager_BeforeContextMenuOpen(object sender, RoutedEventArgs e){    //TODO:your code here.}</td></tr>
</table>
## DockAbility of Child

DockAbility is the property, which is used to decide whether which child can be allowed to dock in using the internal Drag Provider.



[C#]

DockAbility ability=DockAbility.None;

ability |= DockAbility.Left;

ability |= DockAbility.Right;

DockingManager.SetDockAbility(grid1, ability);



{ ![C:/Users/Hemanth/Desktop/Documentation/Images/DockAbility.jpg](Other-Features_images/Other-Features_img2.jpeg) | markdownify }
{:.image }


## Get/Set DockedElementTabbed host size

Get/Set HostSize() method has direct control over the size of the DockedElementTabbedHost,  which  acts as a container for the dockingchild in both Dock and Float state. The container for Dock and Float state, which belongs to the given element, can be obtained as follows.



[C#]

//To get DockedElementTabbedHost Container for Dock State.

DockedElementTabbedHost dockHost = DockingManager.ResolveHost(element, DockState.Dock);



//To get DockedElementTabbedHost Container for float State.

DockedElementTabbedHost floathost = DockingManager.ResolveHost(element, DockState.Float);



Now you can set the size of the host as follows:



[C#]

//To get DockedElementTabbedHost Container for Dock State.

DockedElementTabbedHost dockHost = DockingManager.ResolveHost(element, DockState.Dock);

//To set HostSize.

DockingManager.SetHostSize(dockHost, new Size(50, 100));



//To get HostSize.

Size hostsize = DockingManager.GetHostSize(dockHost);

## Disabling the Header of the Docked Window

NoHeader is the attached property, which is used to hide the header of the Docked Child .This can be shown below.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager Name="DockingManager"&gt;   &lt;Grid Name="grid1"  syncfusion:DockingManager.NoHeader="True"&gt;       &lt;TextBlock Text="Content with Noheader"/&gt;   &lt;/Grid&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetNoHeader(grid1, true);</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/NoHeader.jpg](Other-Features_images/Other-Features_img3.jpeg) | markdownify }
{:.image }


## Detecting the maximized state of the MDI window

IsInMDIMaximizedState property indicates whether any of the MDI children is in a maximized state.



[C#]

bool mdimax = DockingManager.IsInMDIMaximizedState;

## Setting MDI Layout

SetMDILayout()  method is used to set the MDILayout of the child. There are three types of layouts that are available: They are:

* Cascade
* Horizontal
* Vertical

Cascade:

Cascade layout just cascades the window one by one as shown below:



[C#]

DockingManager.SetMDILayout(MDILayout.Cascade);



{ ![C:/Users/Hemanth/Desktop/Documentation/Images/cascade.jpg](Other-Features_images/Other-Features_img4.jpeg) | markdownify }
{:.image }


Horizontal:

This layout arranges the MDI windows in a horizontal manner as shown below:



[C#]

DockingManager.SetMDILayout(MDILayout.Horizontal);



{ ![C:/Users/Hemanth/Desktop/Documentation/Images/horizontal.jpg](Other-Features_images/Other-Features_img5.jpeg) | markdownify }
{:.image }


Vertical Layout:

This layout arranges the MDI windows in a vertical manner as shown below:



[C#]

DockingManager.SetMDILayout(MDILayout.Vertical);



{ ![C:/Users/Hemanth/Desktop/Documentation/Images/vertical.jpg](Other-Features_images/Other-Features_img6.jpeg) | markdownify }
{:.image }


## Rolling the FloatWindow up

IsRollupFloatWindow property is used to enable the Rollup feature of Float window when it is double clicked.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager Name="DockingManager"&gt;&lt;Grid Name="grid1" syncfusion:DockingManager.State="Float" syncfusion:DockingManager.IsRollupFloatWindow="True"/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetIsRollupFloatWindow(grid1, true);</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/Rollup.jpg](Other-Features_images/Other-Features_img7.jpeg) | markdownify }
{:.image }


This can also be applied to all the children of DockingManager as follows:



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager Name="DockingManager" IsRollupFloatWindow="True"&gt;   &lt;Grid Name="grid1" syncfusion:DockingManager.State="Float"/&gt;   &lt;Grid Name="grid2" syncfusion:DockingManager.State="Float"/&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.IsRollupFloatWindow = true;</td></tr>
</table>


## Different Keyboard Navigation Modes

SwitchMode is a property used to specify the different types of switches while using   ctrl + tab navigation. There are five types of switches available. They are:

* Immediate
* List
* QuickTabs
* VistaFlip and 
* VS2005

Immediate Mode:



{ ![C:/Users/Hemanth/Desktop/Documentation/Images/Immediate.jpg](Other-Features_images/Other-Features_img8.jpeg) | markdownify }
{:.image }


List Mode:



{ ![C:/Users/Hemanth/Desktop/Documentation/Images/List.jpg](Other-Features_images/Other-Features_img9.jpeg) | markdownify }
{:.image }


QuickTabs:



{ ![C:/Users/Hemanth/Desktop/Documentation/Images/QuickTabs.jpg](Other-Features_images/Other-Features_img10.jpeg) | markdownify }
{:.image }


Vista Flip:



{ ![C:/Users/Hemanth/Desktop/Documentation/Images/VistaFlip.jpg](Other-Features_images/Other-Features_img11.jpeg) | markdownify }
{:.image }


VS2005:



{ ![C:/Users/Hemanth/Desktop/Documentation/Images/VS2005.jpg](Other-Features_images/Other-Features_img12.jpeg) | markdownify }
{:.image }


## VS2010 Behavior of Docking Manager

This feature enables the user to drag the TDI Windows, which will automatically generate the Float window which will then be dropped at any corner of the docked windows or dropped at any specific TDI Index.

Use Case Scenarios

Users can drag the TDI window which will automatically generate the Float window which can be dropped at any corner of the docked windows instead of using Context Menu to choose Floating and then Dockable to achieve the above operation.

Properties

_Properties Table_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Type </td><td>
Data Type </td><td>
Reference links </td></tr>
<tr>
<td>
IsVS2010DraggingEnabled</td><td>
Gets or sets a value indicating whether the VS2010 behavior can be enabled or not</td><td>
Dependency Property </td><td>
Boolean</td><td>
</td></tr>
</table>


Adding VS2010 Behavior to an Application 

The VS2010 behavior can be enabled by setting IsVS2010DraggingEnabled property to true which will enable the VS2010 drag and drop support of TDI Windows. The default value is set to false.

The property in Docking Manager and can be set in the following ways:

* Through XAML
* Through Code behind



<table>
<tr>
<td>
   [XAML]        &lt;syncfusion:DockingManager UseDocumentContainer="True" Grid.RowSpan="2"   IsVS2010DraggingEnabled="True"&gt;            &lt;StackPanel syncfusion:DockingManager.Header="Tabbed Window 1" syncfusion:DockingManager.State="Document"/&gt;            &lt;ContentControl syncfusion:DockingManager.Header="Tabbed Window 2" syncfusion:DockingManager.State="Document"/&gt;            &lt;ContentControl syncfusion:DockingManager.Header="Tabbed Window 3" syncfusion:DockingManager.State="Document"/&gt;            &lt;ContentControl syncfusion:DockingManager.Header="Tabbed Window 4" syncfusion:DockingManager.State="Document"/&gt;            &lt;ContentControl syncfusion:DockingManager.Header="Tabbed Window 5" syncfusion:DockingManager.State="Document"/&gt;        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]             DockingManager dockingManager = new DockingManager();            dockingManager.IsVS2010DraggingEnabled = true; </td></tr>
</table>
## Support to Enable or Disable Resize in Docked and Float Windows

 Support has been added to enable or disable resize in docked and float windows.

### Use Case Scenarios

Using this feature, users can decide whether the docked and float windows can be resized or not.

### Tables for Properties, Methods, and Events

#### Properties

_Properties Table_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Type </td><td>
Data Type </td></tr>
<tr>
<td>
CanResizeInDockedState</td><td>
Used to enable or disable resize for docked windows. </td><td>
Dependency Attached </td><td>
Bool</td></tr>
<tr>
<td>
CanResizeInFloatState</td><td>
Used to enable or disable resize for float windows. </td><td>
Dependency Attached </td><td>
Bool</td></tr>
<tr>
<td>
CanResizeHeightInDockedState</td><td>
Used to enable or disable only height resize for docked windows.</td><td>
Dependency Attached </td><td>
Bool</td></tr>
<tr>
<td>
CanResizeWidthInDockedState</td><td>
Used to enable or disable only width resize for docked windows.</td><td>
Dependency Attached </td><td>
Bool</td></tr>
<tr>
<td>
CanResizeHeightInFloatState</td><td>
Used to enable or disable only height resize for float windows.</td><td>
Dependency Attached </td><td>
Bool</td></tr>
<tr>
<td>
CanResizeWidthInFloatState</td><td>
Used to enable or disable only width resize for float windows.</td><td>
Dependency Attached </td><td>
Bool</td></tr>
</table>
### Sample Link

SystemDrive\Users\&lt;user_name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version_number&gt;\ WPF\Tools.WPF\Samples\3.5\WindowsSamples\Docking Manager\Docking Demo

### Adding CanResize properties to an Application 

Users can decide whether the docked and float windows can be resized or not using the CanResize properties. 

* CanResizeInDockedState: To enable resize for docked windows, set this property to True. To disable resize for the docked windows, set this property to False. By default the value of the CanResizeInDockedState property is set to True.
* CanResizeInFloatState: To enable resize for float windows, set this property to True. To disable resize for the float windows, set this property to False. By default the value of the CanResizeInFloatState property is set to True.
* CanResizeHeightInDockedState: To enable only height resize for docked windows, set this property to True. To disable only height resize for the docked windows, set this property to False. By default the value of the CanResizeHeightInDockedState property is set to True.
* CanResizeWidthInDockedState: To enable only width resize for docked windows, set this property to True. To disable only width resize for the docked windows, set this property to False. By default the value of the CanResizeWidthInDockedState property is set to True.
* CanResizeHeightInFloatState: To enable only height resize for float windows, set this property to True. To disable only height resize for the float windows, set this property to False. By default the value of the CanResizeHeightInFloatState property is set to True.
* CanResizeWidthInFloatState: To enable only width resize for float windows, set this property to True. To disable only width resize for the float windows, set this property to False. By default the value of the CanResizeWidthInFloatState property is set to True.



The following code snippet shows how to set values for the CanResize properties: 



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager x:Name="dockingManager"&gt;&lt;!-- Product Showcase Window --&gt;<ListBox BorderThickness="0" Name="Parent1" syncfusion:DockingManager.Header="Product Showcase" syncfusion:DockingManager.CanResizeInDockedState="false" syncfusion:DockingManager.CanResizeInFloatState ="false" >&lt;/ListBox&gt;&lt;!-- Docking Manager Window--&gt;<ListBox BorderThickness="0" syncfusion:DockingManager.TargetNameInDockedMode="Parent1"syncfusion:DockingManager.SideInDockedMode="Bottom" syncfusion:DockingManager.Header="Docking Manager"syncfusion:DockingManager.CanResizeHeightInDockedState="false" syncfusion:DockingManager.CanResizeHeightInFloatState ="false"  >&lt;/ListBox&gt;&lt;!-- Ribbon Window--&gt;<ListBox BorderThickness="0" Name="Parent2"syncfusion:DockingManager.TargetNameInDockedMode="Parent1"syncfusion:DockingManager.SideInDockedMode="Right" syncfusion:DockingManager.Header="Ribbon" >&lt;/ListBox&gt;&lt;!-- TreeView Window--&gt;<ListBox BorderThickness="0" syncfusion:DockingManager.TargetNameInDockedMode="Parent2"syncfusion:DockingManager.SideInDockedMode="Right" syncfusion:DockingManager.Header="TreeView" syncfusion:DockingManager.CanResizeWidthInDockedState="false" syncfusion:DockingManager.CanResizeWidthInFloatState ="false" >&lt;/ListBox&gt;&lt;/syncfusion:DockingManager &gt; </td></tr>
<tr>
<td>
[C#]DockingManager.SetCanResizeInDockedState(Parent1, false);DockingManager.SetCanResizeInFloatState(Parent1, false);DockingManager.SetCanResizeHeightInDockedState(Parent2, false);DockingManager.SetCanResizeWidthInDockedState(Parent2, false);DockingManager.SetCanResizeHeightInFloatState(Parent2, false);DockingManager.SetCanResizeWidthInFloatState(Parent2, false);</td></tr>
</table>
## Support to Enable or Disable Fixed Size for Docked Windows

Support to enable or disable fixed size for docked windows.

### Use Case Scenarios

Using this feature, users can decide whether the docked windows sizes can be made fixed or not.

### Tables for Properties, Methods, and Events

#### Properties

_Property table_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Type </td><td>
Data Type </td></tr>
<tr>
<td>
IsFixedSize</td><td>
Used to enable or disable fixed size for docked window.</td><td>
Dependency Attached </td><td>
Bool</td></tr>
<tr>
<td>
IsFixedHeight</td><td>
Used to enable or disable fixed height for docked window.</td><td>
Dependency Attached </td><td>
Bool</td></tr>
<tr>
<td>
IsFixedWidth</td><td>
Used to enable or disable fixed width for docked window.</td><td>
Dependency Attached </td><td>
Bool</td></tr>
</table>
### Sample Link

SystemDrive\Users\&lt;user_name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version_number&gt;\ WPF\Tools.WPF\Samples\3.5\WindowsSamples\Docking Manager\Docking Demo

### Adding Fixed Size Properties to an Application 

The user can decide whether the docked windows can be given a fixed size using the FixedSize properties. 

* IsFixedSize:To enable fixed sizes for the docked windows, set this property to True. To disable fixed sizes for the docked windows, set this property to False. By default the value of the IsFixedSize property is set to False. When fixed size is enabled for docked windows, the corresponding CanResizeInDockedState property should be set to False.
* IsFixedHeight: To enable fixed height for the docked windows, set this property to True. To disable fixed height for the docked windows, set this property to False. By default the value of the IsFixedHeight property is set to False. When fixed height is enabled for docked windows, the corresponding CanResizeHeightInDockedState property should be set to False.
* IsFixedWidth: To enable fixed width for docked windows, set this property to True. To disable fixed width for the docked windows, set this property to False. By default the value of the IsFixedWidth property is set to False. When fixed width is enabled for docked windows, the corresponding CanResizeWidthInDockedState property should be set to False.

The fixed-size docked windows will not have dockable options to allow other docked windows to be docked inside them.

The following code snippet shows how to set values for the FixedSize properties: 



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager x:Name="dockingManager"&gt;&lt;!-- Product Showcase Window --&gt;<ListBox BorderThickness="0" Name="Parent1" syncfusion:DockingManager.Header="Product Showcase" syncfusion:DockingManager.CanResizeInDockedState="false" syncfusion:DockingManager.IsFixedSize ="true" >&lt;/ListBox&gt;&lt;!-- Docking Manager Window--&gt;<ListBox BorderThickness="0" syncfusion:DockingManager.TargetNameInDockedMode="Parent1"syncfusion:DockingManager.SideInDockedMode="Bottom" syncfusion:DockingManager.Header="Docking Manager"syncfusion:DockingManager.CanResizeHeightInDockedState="false" syncfusion:DockingManager.IsFixedHeight ="true"  >&lt;/ListBox&gt;&lt;!-- Ribbon Window--&gt;<ListBox BorderThickness="0" Name="Parent2"syncfusion:DockingManager.TargetNameInDockedMode="Parent1"syncfusion:DockingManager.SideInDockedMode="Right" syncfusion:DockingManager.Header="Ribbon" syncfusion:DockingManager.CanResizeWidthInDockedState="false" syncfusion:DockingManager.IsFixedWidth ="true" >&lt;/ListBox&gt;&lt;/syncfusion:DockingManager &gt; </td></tr>
<tr>
<td>
[C#]DockingManager dockingmanager = new DockingManager();dockingmanager.MaximizeButtonEnabled = true;dockingmanager.MaximizeButtonMode = VisibilityMode.Disable;Grid grid = new Grid();DockingManager.SetCanMaximize(grid, false);dockingmanager.Children.Add(grid);</td></tr>
</table>
## Support to manage Maximize Button Visibiliity in Docking Windows

This support will be useful to decide whether the Maximize button should be disabled or collapsed when the CanMaximize property is set to False.

### Use Case Scenarios

This support enhances the usability of the Maximize button.

### Tables for Properties, Methods, and Events

#### Properties

_Property table_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Type </td><td>
Data Type </td></tr>
<tr>
<td>
MaximizeButtonMode</td><td>
Useful for choosing the MaximizeButtonMode when CanMaximize is set to False.MaximizeButtonMode:* VisibilityMode.Collapse (default)* VisibilityMode.Disable<br></td><td>
Dependency property </td><td>
MaximizeButtonMode</td></tr>
</table>
### Sample Link

N/A

### Adding MaximizeButtonMode to an Application 

The user can choose whether the Maximize button should be collapsed or disabled when the CanMaximize property is set to False. 

By setting VisibilityMode as Collapsed when the CanMaximize property is set to False, the Maximize button will be collapsed. By setting VisibilityMode as Disable, the Maximize button is visible, but we set the IsEnabled property of the Maximize button to False.

The following code snippet shows how to set values for the MaximizeButtonMode property: 



<table>
<tr>
<td colspan = "2">
[XAML]&lt;syncfusion:DockingManager MaximizeButtonEnabled="True" MaximizeButtonMode="Disable" &gt;   &lt;Grid syncfusion:DockingManager.CanMaximize="True" /&gt;&lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager dockingmanager = new DockingManager();dockingmanager.MaximizeButtonEnabled = true;dockingmanager.MaximizeButtonMode = VisibilityMode.Disable;Grid grid = new Grid();DockingManager.SetCanMaximize(grid, false);dockingmanager.Children.Add(grid);</td></tr>
</table>
## Native Float Window

### UseNativeFloatWindow

The UseNativeFloatWindow property is used to enable or disable the native float window which inherits the window architecture. By disabling this propety, you can use the existing float window.

Property

_Property table_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Type </td><td>
Data Type </td></tr>
<tr>
<td>
UseNativeFloatWindow</td><td>
Enables or disables the native float window.</td><td>
Dependency Property</td><td>
bool</td></tr>
</table>


Adding Native Float Window to an Application 

By enabling the UseNativeFloatWindow property, you can use the native float window as a floating window. This property cannot be changed dynamically.



<table>
<tr>
<td>
 [C#]dockingmanager.UseNativeFloatWindow = true;</td></tr>
<tr>
<td>
[XAML]&lt;Syncfusion:DockingManager x:Name="dockingmanager" UseNativeFloatWindow="True" &gt;    &lt;ContentControl Syncfusion:DockingManager.Header="Item1"/&gt;&lt;/Syncfusion:DockingManager&gt;</td></tr>
</table>


{ ![](Other-Features_images/Other-Features_img13.png) | markdownify }
{:.image }


### CanFloatMaximize

The CanFloatmaximize property allows the native float window to get maximized using the Maximize button. By using this property, you can make the Maximize button visible on the title bar of the native floating window.

Property

_Property table_

<table>
<tr>
<td>
Property </td><td>
Description </td><td>
Type </td><td>
Data Type </td></tr>
<tr>
<td>
CanFloatmaximize</td><td>
Enables or disables maximization of the native float window.</td><td>
Attached Property</td><td>
bool</td></tr>
</table>


Maximizing the Native Float Window

By enabling the CanFloatMaximize property, the native float window can be maximized.



<table>
<tr>
<td>
 [C#]DockingManager.SetCanFloatMaximize(Item1, true);</td></tr>
<tr>
<td>
[XAML]&lt;Syncfusion:DockingManager x:Name="dockingmanager" UseNativeFloatWindow="True" &gt;            &lt;ContentControl x:Name="Item1" Syncfusion:DockingManager.Header="Item1" Syncfusion:DockingManager.CanFloatMaximize="True"/&gt;&lt;/Syncfusion:DockingManager&gt;</td></tr>
</table>


{ ![](Other-Features_images/Other-Features_img14.png) | markdownify }
{:.image }


## Support to Add Document Tab Group

This feature provides a document tab group that can be added at run time. It supports both horizontal and vertical orientation, and allows elements to be added into an existing tab group. 

Use Case Scenarios

Users can add a document tab group at run time in either a horizontal and vertical orientation, instead of using the context menu to create a new horizontal tab group or new vertical tab group.

### Tables for Properties, Methods, and Events

Methods

_Methods table_

<table>
<tr>
<th>
Method</th><th>
Description</th><th>
Parameters</th><th>
Type</th><th>
Return Type</th></tr>
<tr>
<th>
CreateHorizontalTabGroup</th><th>
Enables users to add a horizontal document tab group.</th><th>
(UIElement TabGroupElement) </th><th>
NA</th><th>
void</th></tr>
<tr>
<th>
CreateVerticalTabGroup</th><th>
Enables users to add a vertical document tab group.</th><th>
(UIElement TabGroupElement) </th><th>
NA</th><th>
void</th></tr>
<tr>
<th>
AddElementToTabGroup</th><th>
Enables users to add an element to an existing tab group.</th><th>
(DocumentTabControl TargetTabGroup, UIElement ElementToAdd)</th><th>
NA</th><th>
void</th></tr>
</table>


Events

_Events table_

<table>
<tr>
<th>
Event</th><th>
Description</th><th>
Arguments</th><th>
Type</th></tr>
<tr>
<th>
TabGroupCreated</th><th>
The TabGroupCreated event occurs after a new tab group is created.</th><th>
CurrentTabGroup,PreviousTabGroup,Orientation,TargetItem</th><th>
TabGroupEventArgs</th></tr>
<tr>
<th>
MoveToOtherTabGroup</th><th>
The MoveToOtherTabGroup event occurs after an element is added or moved into existing tab group.</th><th>
CurrentTabGroup,PreviousTabGroup,Orientation,TargetItem</th><th>
TabGroupEventArgs</th></tr>
</table>
### Adding a Document Tab Group to an Application 

#### CreateHorizontalTabGroup

To create a horizontal tab group as a new element, use the following code:



[C#]

FrameworkElement newelement = new FrameworkElement();

DockingManager.SetState(newelement as DependencyObject, DockState.Document);

DockingManager.SetHeader(newelement as DependencyObject, "TabGroup1");

dockingManager.CreateHorizontalTabGroup(newelement);





To create a horizontal tab group as an existing element in the docking manager children collection, use the following code:



[C#]

dockingManager.CreateHorizontalTabGroup(dockingManager.Children[2]);



#### CreateVerticalTabGroup

To create a vertical tab group as a new element, use the following code:



[C#]

FrameworkElement newelement = new FrameworkElement();

DockingManager.SetState(newelement as DependencyObject, DockState.Document);

DockingManager.SetHeader(newelement as DependencyObject, "TabGroup1");

dockingManager.CreateVerticalTabGroup(newelement);





To create a vertical tab group as an existing element in the docking manager children collection, use the following code:



[C#]

dockingManager.CreateVerticalTabGroup(dockingManager.Children[2]);

#### AddElementToTabGroup

To add an element to an existing tab group, use the following code:



[C#]

FrameworkElement newelement = new FrameworkElement();

DockingManager.SetState(newelement as DependencyObject, DockState.Document);

DockingManager.SetHeader(newelement as DependencyObject, "TabGroup1");

DocumentTabControl targetTabGroup =  

         DockingManager.GetTabControl(dockingManager.Children[0]) as DocumentTabControl;

dockingManager.AddElementToTabGroup(targetTabGroup, newelement);





