---
layout: post
title: Interactive-Features
description: interactive features
platform: wpf
control: DockingManager
documentation: ug
---

# Interactive Features

A basic requirement in creating any WPF application that uses our DockingManager control, is the ability to set a window as an active window. DockingManager's ActiveWindow property can be used for this. ActiveWindow is an element, which returns a window object that is currently focused. To set a window as active, use the following code.



<table>
<tr>
<td>
[XAML]&lt;!--Adding Docking Manager--&gt;        &lt;syncfusion:DockingManager AutoHideAnimationMode="Fade" Name="DockingManager" Loaded="DockingManager_Loaded"&gt;            &lt;!--Adding Children for the Docking Manager control with state as Dock and a side in dock mode as left--&gt;            <StackPanel syncfusion:DockingManager.State="Dock" Name="Element One"              syncfusion:DockingManager.SideInDockedMode="Left"/>            <StackPanel syncfusion:DockingManager.State="Dock" Name="Element Two"              syncfusion:DockingManager.SideInDockedMode="Right"/>        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]//Setting the active window, giving the name of the children element as the parameter for the Activate Window.DockingManager.ActivateWindow("Name of the Window");</td></tr>
</table>


Event

_Event table_

<table>
<tr>
<td>
Event</td><td>
Description</td></tr>
<tr>
<td>
OnActiveWindowChanged</td><td>
Handled when an active window is changed.</td></tr>
</table>


Method

_Method table_

<table>
<tr>
<td>
Method</td><td>
Description</td></tr>
<tr>
<td>
OnActivateWindow</td><td>
This method is called when an active window is changed. </td></tr>
</table>


Retrieving an Active Window from DockingManager

Sometimes, you need to identify an active window to perform some operations at run time. For this, create an object for the FrameWorkElement and set the DockingManager active window to it. Now the FrameWorkElement object returns the active window.

The following code snippet explains how to retrieve the Active window from the Docking Manager control.



[C#]



//Checking the active window as null or not.

if (DockingManager1.ActiveWindow != null)

{

    //Setting the Frameworkelement object with the Docking Manager's active window

    FrameworkElement ffelement = DockingManager1.ActiveWindow;



    //Returning the active window

    return ffelement;

}



Where, the 'ffelement' returns the active window.

You can also iterate through all the child elements of the DockingManager control, and get the active window to perform the actions, if any. This behavior is demonstrated in the following example on a button click event.



[C#]

// Handles the Click event of the dockingactivewindow control.

        private void dockingactivewindow_Click(object sender, RoutedEventArgs e)

        {

            //Getting the sender as Docking Manager

            DockingManager1 = sender as DockingManager;



            //Iterating through the children of the Docking Manager control

            foreach (FrameworkElement felement in DockingManager1.Children)

            {

                //Checking the active window

                if (ffelement == DockingManager1.ActiveWindow)

                {

                    //Do the actions here

                }

            };

        }

## Using ActiveWindow Property

ActiveWindow Property is used to Get/Set ActiveWindow for DockingManager



[C#]

  DockingManager.ActiveWindow=element1;



Refer Also

How to Activate Particular Window

## Customizing the Appearance

### FloatWindow Customization

Under this section you will find all the possible customization options available for the Float window.

_FloatWindow Customization properties table_

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
FloatWindowBorderBrush</td><td>
This dependency property defines border brush of the float window. </td></tr>
<tr>
<td>
FloatWindowHeaderBackground</td><td>
This dependency property defines header background of the Float window. </td></tr>
<tr>
<td>
FloatWindowHeaderForeground</td><td>
This dependency property defines header foreground of the float window.</td></tr>
<tr>
<td>
FloatWindowMouseOverBorderBrush</td><td>
This dependency property defines border brush of the float window. </td></tr>
<tr>
<td>
FloatWindowMouseOverHeaderBackground</td><td>
This dependency property defines header background of the float window. </td></tr>
<tr>
<td>
FloatWindowMouseOverHeaderForeground</td><td>
This dependency property defines header foreground of the float window.</td></tr>
<tr>
<td>
FloatWindowSelectedBorderBrush</td><td>
This dependency property defines selected border brush of the float window. </td></tr>
<tr>
<td>
FloatWindowSelectedHeaderBackground</td><td>
This dependency property defines selected header background of the float window. </td></tr>
<tr>
<td>
FloatWindowSelectedHeaderForegroundProperty</td><td>
This dependency property defines selected header foreground of the float window. </td></tr>
</table>


> _Note: The default value of all the above listed properties is Transparent._ 

Use the below code snippet for applying all the customization related properties of the float windows.



[XAML]

&lt;!--Creating the Docking Manager--&gt;

        &lt;syncfusion:DockingManager FloatWindowBorderBrush="AliceBlue" FloatWindowHeaderBackground="Bisque" FloatWindowHeaderForeground="Red" FloatWindowMouseOverBorderBrush="Yellow" FloatWindowMouseOverHeaderBackground="Blue" FloatWindowMouseOverHeaderForeground="Aqua" FloatWindowSelectedBorderBrush="Pink" FloatWindowSelectedHeaderBackground="BlanchedAlmond" FloatWindowSelectedHeaderForeground="RoyalBlue"&gt;

            &lt;!--Creating the float window for the Docking Manager--&gt;

            &lt;StackPanel syncfusion:DockingManager.State="Float" Name="elementone" syncfusion:DockingManager.Header="Float" syncfusion:DockingManager.SideInDockedMode="Left"/&gt;

        &lt;/syncfusion:DockingManager&gt;





{ ![C:/Users/Hemanth/Desktop/Documentation/Images/FloatWindow.jpg](Interactive-Features_images/Interactive-Features_img1.jpeg) | markdownify }
{:.image }


_Customized Float Window_

### Border Thickness of Child Elements

You can set the border thickness for the hosted children of the Docking Manager control. The following properties are used to set the thickness for the individual child elements in various dock states.

* ElementBorderThickness 
* FloatWindowBorderThickness 
* SidePanelBorderThickness 
* SidePanelItemsBorderThickness 
* TabPanelBorderThickness 
* TabItemBorderThickness 
* TabItemsBorderThicknessSelected 
* HeaderBorderThickness 

ElementBorderThickness

ElementBorderThickness property is used to store border thickness value for host. The default value of this property is 1. It is a dependency property, which defines the border thickness of the element inside the window. 

The below code snippet is used to set an element border thickness for the Docking Manager control.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager ElementBorderThickness="20"&gt;            &lt;StackPanel syncfusion:DockingManager.State="Dock" syncfusion:DockingManager.SideInDockedMode="Left"/&gt;        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]//Creating the instance of the Docking Manager.DockingManager = new DockingManager();//Setting the element thickness for the docking managerDockingManager.ElementBorderThickness = new Thickness(20);</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/Thickness1.jpg](Interactive-Features_images/Interactive-Features_img2.jpeg) | markdownify }
{:.image }


_ElementBorderThickness = "20"_

FloatWindowBorderThickness

This property specifies the border thickness value of the floating window. The default value of the FloatWindowBorderThickness property is 22,4,4,4 . 

Use the following XAML and C# code, for setting the float window border thickness.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager FloatWindowBorderThickness="20"&gt;            &lt;StackPanel syncfusion:DockingManager.State="Dock" syncfusion:DockingManager.SideInDockedMode="Left"/&gt;        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]//Creating the instance of the Docking Manager.DockingManager = new DockingManager();//Setting the Float Window Border Thickness for the Docking Manager.DockingManager.FloatWindowBorderThickness = new Thickness(20);</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/Thickness2jpg.jpg](Interactive-Features_images/Interactive-Features_img3.jpeg) | markdownify }
{:.image }


_FloatWindowBorderThickness = "20"_

SidePanelBorderThickness

This dependency property defines the border thickness of the side panel, which is usually seen once you auto hide the children of the DockingManager control. The default value is 0.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager SidePanelBorderThickness="20"&gt;            &lt;StackPanel syncfusion:DockingManager.State="Dock" syncfusion:DockingManager.SideInDockedMode="Left"/&gt;        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]//Creating the instance of the Docking Manager.DockingManager = new DockingManager();//Setting the Side Panel Border Thickness for the Docking Manager.DockingManager.SidePanelBorderThickness = new Thickness(20);</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/Thickness3.jpg](Interactive-Features_images/Interactive-Features_img4.jpeg) | markdownify }
{:.image }


_SidePanelBorderThickness = "20"_

SidePanelItemsBorderThickness - This dependency property specifies the border thickness of the side panel items. The default value is 1. 

Here is the code snippet for setting this property.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager SidePanelItemsBorderThickness="20"&gt;            &lt;StackPanel syncfusion:DockingManager.State="Dock" syncfusion:DockingManager.SideInDockedMode="Left"/&gt;        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]//Creating the instance of the Docking Manager.DockingManager = new DockingManager();//Setting the element thickness for the Docking Manager.DockingManager.SidePanelItemsBorderThickness = new Thickness(20);</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/Thickness4.jpg](Interactive-Features_images/Interactive-Features_img5.jpeg) | markdownify }
{:.image }


_SidePanelItemsBorderThickness = "20"_

TabPanelBorderThickness - This dependency property defines the border thickness of the tab panel. The default value of the TabPanelBorderThickness property is 0.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager TabPanelBorderThickness="50"&gt;            &lt;StackPanel syncfusion:DockingManager.State="AutoHidden" Name="Element One" syncfusion:DockingManager.SideInDockedMode="Bottom"/&gt;            <StackPanel syncfusion:DockingManager.State="Dock" Name="Element Two" syncfusion:DockingManager.TargetNameInDockedMode="Element One"syncfusion:DockingManager.SideInDockedMode="Tabbed"/>        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]//Creating the instance of the Docking Manager.DockingManager = new DockingManager();//Setting the Tab Panel Border Thickness for the Docking ManagerDockingManager.TabPanelBorderThickness = new Thickness(20);</td></tr>
</table>


TabItemBorderThickness - This dependency property defines the border thickness of the tab item. The default value is 1. 



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager TabItemBorderThickness="50"&gt;            &lt;StackPanel syncfusion:DockingManager.State="AutoHidden" Name="Element One" syncfusion:DockingManager.SideInDockedMode="Bottom"/&gt;            <StackPanel syncfusion:DockingManager.State="Dock" Name="Element Two" syncfusion:DockingManager.TargetNameInDockedMode="Element One"syncfusion:DockingManager.SideInDockedMode="Tabbed"/>        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]//Creating the instance of the Docking Manager.DockingManager = new DockingManager();//Setting the Tab Item Border Thickness for the Docking Manager.DockingManager.TabItemBorderThickness = new Thickness(20);</td></tr>
</table>


TabItemsBorderThicknessSelected - This dependency property defines border thickness of the selected tab items. The default value of the TabItemsBorderThicknessSelected property is 0.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager TabItemsBorderThicknessSelected="50"&gt;            &lt;StackPanel syncfusion:DockingManager.State="Dock" Name="Element One" syncfusion:DockingManager.SideInDockedMode="Left"/&gt;            <StackPanel syncfusion:DockingManager.State="Dock" Name="Element Two" syncfusion:DockingManager.TargetNameInDockedMode="Element One"syncfusion:DockingManager.SideInDockedMode="Tabbed"/>        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]//Creating the instance of the Docking Manager.DockingManager = new DockingManager();//Setting the Tab Items Border Thickness Selected for the Docking Manager.DockingManager.TabItemsBorderThicknessSelected = new Thickness(20);</td></tr>
</table>


HeaderBorderThickness 

HeaderBorderThickness dependency property defines the border thickness of the window's header. The default value is 1.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager HeaderBorderThickness="20"&gt;            &lt;StackPanel syncfusion:DockingManager.State="Dock" Name="Element One" syncfusion:DockingManager.SideInDockedMode="Left"/&gt;        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td colspan = "2">
[C#]//Creating the instance of the Docking ManagerDockingManager = new DockingManager();//Setting the Header Border Thickness for the Docking ManagerDockingManager.HeaderBorderThickness = new Thickness(20);</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/Thickness5.jpg](Interactive-Features_images/Interactive-Features_img6.jpeg) | markdownify }
{:.image }


_HeaderBorderThickness = "20"_                             

### Tab Strip Placement

The tabs of the docked windows will be placed at the top of the parent window, by default. This tab placement is changed to any of the following options by using the DockTabAlignment property.

* Top (default)
* Right
* Bottom
* Left

The following code illustrates changing the tab strip placement.



<table>
<tr>
<td>
[XAML]&lt;!-- To set the Tab strip to the Bottom --&gt;        &lt;sftools:DockingManager Name="DocManager1" DockTabAlignment="Bottom"/&gt;        &lt;!-- To set the Tab strip to the Right --&gt;        &lt;sftools:DockingManager Name="DocManager1" DockTabAlignment="Right"/&gt;</td></tr>
<tr>
<td>
[C#]//To set the Tab strip to the Bottom.this.DockingManager.DockTabAlignment = Dock.Bottom;//To set the Tab strip to the Right.this.DockingManager.DockTabAlignment = Dock.Right;</td></tr>
</table>


{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/image140068940.jpg](Interactive-Features_images/Interactive-Features_img7.jpeg) | markdownify }
{:.image }


_DockTabAlignment = "Bottom"_



{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/image1681845622.jpg](Interactive-Features_images/Interactive-Features_img8.jpeg) | markdownify }
{:.image }


_DockTabAlignment = "Right"_

### Sidepanel TabItem Customization

#### SidePanel Header Background

SideTabItemBackground property allows you to set a background color for TabItem’s Header. It is a dependency property, which defines the background color of the element in side panel.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager ElementBorderThickness="20"&gt;    &lt;ContentControl syncfusion.DockingManager.Header=”SideTab1”       syncfusion.DockingManager.SideTabItemBackground=”Blue”/&gt;&lt;/syncfusion:DockingManager&gt; </td></tr>
<tr>
<td>
[C#]//Creates new instance of DockingManger DockingManager manager =new DockingManager();//New instance of content is created.ContentControl content = new ContentControl();//Sets SetSideItemBackground attached propertyDockingManager.SetSideTabItemBackground(content, Brushes.Blue);manager.Children.Add(content);</td></tr>
</table>


The following screen shot illustrates a TabHeader with background color.



{ ![](Interactive-Features_images/Interactive-Features_img9.png) | markdownify }
{:.image }


_TabHeader with background_

#### SidePanel Header Foreground

SideTabItemForeground property allows you to set foreground color for SidePanelTabItem’s Header. It is a dependency property, which defines the foreground color of the element in SidePanel.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager ElementBorderThickness="20"&gt;    &lt;ContentControl syncfusion.DockingManager.Header=”SideTab1”       syncfusion.DockingManager.SideTabItemForeground=”Red”/&gt;&lt;/syncfusion:DockingManager&gt; </td></tr>
<tr>
<td colspan = "2">
[C#]//Creates new instance of DockingManger DockingManager manager =new DockingManager();//New  instance of contentContentControl content = new ContentControl();//setting SetSideItemBackground attached propertyDockingManager.SetSideTabItemBackground(content, Brushes.Red);manager.Children.Add(content);</td></tr>
</table>


The following screen shot illustrates a TabHeader with foreground color.



{ ![](Interactive-Features_images/Interactive-Features_img10.png) | markdownify }
{:.image }


_TabHeader with foreground_

## Customizing the Behavior

### Enable/Disable Docking, Floating, AutoHide, Closing

The following description gives you a clear knowledge aboutdocking, float and closing a dockable window.

Docking a Dockable Window

DockingManager facilitates the users to allow or restrict a dockable window to move to the docked state. This is done by using the CanDock property of the DockingManager. When this property is set to False, the dockable window will be restricted to enter the docked state; it can either be in floating or in auto hidden state. Also this setting will not allow the transition of states from Auto Hide to Float or vice versa, as the window needs to change the dock state as a part of the transition.

For settings, CanDock property, use the following code.



<table>
<tr>
<td>
[XAML]&lt;Grid Name="Properties" sftools:DockingManager.CanDock="True"/&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetCanDock(Properties, true);</td></tr>
</table>


Floating a Dock Window

The Floating state of a dockable window is controlled by using the CanFloat property. When the CanFloat property is set to False, the window can take either docked or auto hidden states. It will not be allowed to float until the CanFloat property is enabled.

To enable the CanFloat property of DockingManager, use the following code. 



<table>
<tr>
<td>
[XAML]&lt;Grid Name="Properties" sftools:DockingManager.CanFloat="True"/&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetCanFloat(Properties, true);</td></tr>
</table>


{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/image803644431.jpg](Interactive-Features_images/Interactive-Features_img11.jpeg) | markdownify }
{:.image }


_CanFloat = "False"_



{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/image188242848.jpg](Interactive-Features_images/Interactive-Features_img12.jpeg) | markdownify }
{:.image }


_CanFloat = "True"_

Closing a Dock Window

The DockingManager gives the option for users to control the closing functionality of the dockable window. A window is restricted from closing by disabling the CanClose property of the DockingManager. When this property is set to False, it will not display the close button in the header of the window.

To set this property, refer the following code.



<table>
<tr>
<td>
[XAML]&lt;Grid Name="Properties" sftools:DockingManager.CanClose="True"&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetCanClose(Properties, true);</td></tr>
</table>


{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/image1015755465.jpg](Interactive-Features_images/Interactive-Features_img13.jpeg) | markdownify }
{:.image }


_CanClose = "False"_



{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/image1824565565.jpg](Interactive-Features_images/Interactive-Features_img14.jpeg) | markdownify }
{:.image }


_CanClose = "True"_

Refer Also

Dealing with States

Document State Child

### AutoHide Button Visibility

By default, all docked windows will have the ability to auto hide, when the user clicks the auto hide button. This feature can be disabled using the AutoHideVisibility property. This property is typically used to allow or deny the changing element's state to auto hidden, through Graphical User Interface (GUI), by showing / hiding the AWL button in the host header and hence auto hiding the context menu item. 

Here is the code snippet for setting the above property.



<table>
<tr>
<td>
[XAML]&lt;!--Declaring Docking Manager AutoHideVisibility to False --&gt;        &lt;syncfusion:DockingManager AutoHideVisibility="False"&gt;            &lt;!--Your contents here--&gt;        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]//Creating an instance for Docking Manager.DockingManager = new DockingManager();//Setting AutoHideVisibility to true.DockingManager.AutoHideVisibility = true;</td></tr>
</table>


{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/image611161089.jpg](Interactive-Features_images/Interactive-Features_img15.jpeg) | markdownify }
{:.image }


_AutoHideVisibility = "False"_



{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/image1917721802.jpg](Interactive-Features_images/Interactive-Features_img16.jpeg) | markdownify }
{:.image }


_AutoHideVisibility = "True"_

Refer Also

AutoHide Visibility

### Auto Hide Mode

There are two modes of auto hiding behavior. They are:

* AutoHideGroup (default): All elements in the tabbed host will be auto hidden.
* AutoHideActive: Only the active window will be auto hidden.



<table>
<tr>
<td>
[XAML]&lt;!--Declaring Docking Manager with AutoHide Active--&gt;        &lt;syncfusion:DockingManager AutoHideTabsMode="AutoHideActive"&gt;            &lt;!--Your contents here--&gt;        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]//Creating the instance of the Docking Manager.DockingManager = new DockingManager();//Setting AutoHideGroup for the Docking Manager.DockingManager.AutoHideTabsMode = AutoHideTabsMode.AutoHideGroup;</td></tr>
</table>


Events Handled While Auto hiding

The following events are handled while Auto hiding.

_Event table_

<table>
<tr>
<td>
Event</td><td>
Description</td></tr>
<tr>
<td>
AutoHideAnimationStartEvent</td><td>
Handled when auto hiding operation starts.</td></tr>
<tr>
<td>
AutoHideAnimationEndEvent</td><td>
Handled when auto hiding operation ends.</td></tr>
</table>


### Using AutoHide Animation Modes

DockingManager supports three different built–in animations for auto-hiding the windows. They are listed below.

* Slide: Elements auto hides in a sliding style.
* Scale: Elements follows a particular scale while auto hiding.
* Fade: Element’s appearance fades while it auto hides.



The animation modes can be applied by using the AutoHideAnimationMode property of the Docking Manager. 

To apply different animation styles to the docking windows, use the following code. This setting will get reflected when the user auto hides a window at run time.



<table>
<tr>
<td>
[XAML]&lt;!--To set the Fade animation mode--&gt;        &lt;sftools:DockingManager Name="DocManager1" AutoHideAnimationMode="Fade"/&gt;</td></tr>
<tr>
<td>
[C#]//To set the Fade animation mode.this.DockingManager.AutoHideAnimationMode = AutoHideAnimationMode.Fade;</td></tr>
</table>


Animation Duration

DockingManager enables you to control the duration for animation or the animation delay, while auto hiding the docking windows. Animation delay is set by using the AnimationDelay property of the DockingManager. It accepts the duration in milliseconds. 

The following code sets the AnimationDelay property.



[C#]

//To set Very slow animation delay.

this.DockingManager.SetAnimationDelay(DocManager1, new Duration(new TimeSpan(30000000)));

//To set Very fast animation delay.

this.DockingManager.SetAnimationDelay(DocManager1, new Duration(new TimeSpan(10000)));

### Closing Options for Tabbed Windows

To set CloseTabs as CloseActive mode, use the following code:



<table>
<tr>
<td>
[XAML]&lt;sftools:DockingManager Name="DocManager1" CloseTabs="CloseActive"/&gt;</td></tr>
<tr>
<td>
[C#]this.DockingManager.CloseTabs = CloseTabsMode.CloseActive;</td></tr>
</table>
### Enable/Disable Dragging a Window

The DockingManager enables you to restrict an element to be dragged from one side to another. The dragging functionality is disabled for a window by setting the CanDrag property to false.

The following code is used to enable the CanDrag property.



<table>
<tr>
<td>
[XAML]&lt;Grid Name="Properties" sftools:DockingManager.CanDrag="True"/&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetCanDrag(Properties, true);</td></tr>
</table>


{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/image1537050122.jpg](Interactive-Features_images/Interactive-Features_img17.jpeg) | markdownify }
{:.image }


_CanDrag = "False"_



{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/image27394988.jpg](Interactive-Features_images/Interactive-Features_img18.jpeg) | markdownify }
{:.image }


_CanDrag = "True"_



## Using DockedElementTabbedHost

This topic illustrates the following features:

* Docked Element Tabbed Host Alignment and
* Docked Element Tabbed Host Style
### DockHost Alignment


The DockTabAlignment property is used as a tab strip placement for all TabbedHosts that are docked, inside the DockingManager instance. By default its value is set to Bottom.

You can set the DockTabAlignment to Left, Right, Bottom or Top.



[XAML]

&lt;syncfusion:DockingManager Name="DockingManager" DockTabAlignment="Right" &gt;

            <StackPanel syncfusion:DockingManager.State="Dock"

              syncfusion:DockingManager.SideInDockedMode="Bottom"

              Name="Element One"

              syncfusion:DockingManager.Header="one"/>

            <StackPanel syncfusion:DockingManager.State="Dock"

              syncfusion:DockingManager.SideInDockedMode="Tabbed"

              Name="Element Two"

              syncfusion:DockingManager.TargetNameInDockedMode="Element One"

              syncfusion:DockingManager.Header="Two"/>

            <StackPanel syncfusion:DockingManager.State="Dock"

              syncfusion:DockingManager.SideInDockedMode="Tabbed"

              Name="Element Three"

              syncfusion:DockingManager.TargetNameInDockedMode="Element One"

              syncfusion:DockingManager.Header="Three"/>

        &lt;/syncfusion:DockingManager&gt;



{ ![C:/Users/Hemanth/Desktop/Documentation/Images/Host.jpg](Interactive-Features_images/Interactive-Features_img19.jpeg) | markdownify }
{:.image }


_DockTabAlignment = "Right"_

### DockHost Style

This dependency property will get or set the style used by the TabbedHosts that are docked, when it is rendered. It provides DockedElementTabbedHostStyle value for the Docking Manager. 

The user can initialize the style of the docked element host by setting the DockedElementTabbedHostStyle property in XAML as follows.



[XAML]

&lt;syncfusion:DockingManager  Name="DockingManager1" ContainerMode="TDI"&gt;

            &lt;!--Setting the style for the Docked Element Tabbed Host--&gt;

            &lt;syncfusion:DockingManager.DockedElementTabbedHostStyle&gt;

                &lt;Style TargetType="{x:Type syncfusion:DockedElementTabbedHost}"&gt;

                    &lt;Setter Property="Background" Value="PeachPuff"/&gt;

                &lt;/Style&gt;

            &lt;/syncfusion:DockingManager.DockedElementTabbedHostStyle&gt;



            &lt;!--Children for the Docking Manager control--&gt;

            &lt;StackPanel syncfusion:DockingManager.State="Dock" syncfusion:DockingManager.SideInDockedMode="Left"/&gt;

            &lt;StackPanel syncfusion:DockingManager.State="Document" syncfusion:DockingManager.SideInDockedMode="Left"/&gt;

        &lt;/syncfusion:DockingManager&gt;





## Using Drag modes

The DockingManager enables you to set different drag modes, when a docking window is being dragged. It supports the following three drag modes.

* Normal DragMode
* Border DragMode and
* Shadow DragMode

The DraggingType property of DockingManager is used to change the drag mode. The options provided by this property are as follows:

* NormalDragging (Normal DragMode)
* BorderDragging (Border DragMode) and
* ShadowDragging (Shadow DragMode)

The following code snippet is used to change the Drag mode of the DockingManager. 



<table>
<tr>
<td>
[XAML]        &lt;!--Setting the Normal Drag Mode--&gt;        &lt;sftools:DockingManager Name="DocManager1" DraggingType="NormalDragging"/&gt;        &lt;!--Setting the Border Drag Mode--&gt;        &lt;sftools:DockingManager Name="DocManager1" DraggingType="BorderDragging"/&gt;        &lt;!--Setting the Shadow Drag Mode--&gt;        &lt;sftools:DockingManager Name="DocManager1" DraggingType="ShadowDragging"/&gt;</td></tr>
<tr>
<td>
[C#]//Setting the Normal Drag Mode.this.DockingManager.DraggingType = DraggingType.NormalDragging;//Setting the Border Drag Mode.this.DockingManager.DraggingType = DraggingType.BorderDragging;//Setting the Shadow Drag Mode.this.DockingManager.DraggingType = DraggingType.ShadowDragging;</td></tr>
</table>


{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/image1191835022.jpg](Interactive-Features_images/Interactive-Features_img20.jpeg) | markdownify }
{:.image }


_Normal Drag Mode_



{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/image745951164.jpg](Interactive-Features_images/Interactive-Features_img21.jpeg) | markdownify }
{:.image }


_Border Drag Mode_



{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/image1136896003.jpg](Interactive-Features_images/Interactive-Features_img22.jpeg) | markdownify }
{:.image }


_Shadow Drag Mode_

## Context Menu Support

### Default Context Menu

A dockable window will be associated with a default context menu with default menu items. The DockingManager provides options to add custom context menu for the dockable window. You can set a context menu using the following code snippet. 



[XAML]

        &lt;syncfusion:DockingManager  Name="DockingManager1"&gt;

            &lt;syncfusion:DockingManager.ContextMenu&gt;

                &lt;ContextMenu&gt;

                    &lt;MenuItem Header="Cut" InputGestureText="Ctrl+X" Command="ApplicationCommands.Cut" /&gt;

                    &lt;MenuItem Header="Copy" InputGestureText="Ctrl+C" Command="ApplicationCommands.Copy" /&gt;

                    &lt;MenuItem Header="Paste" InputGestureText="Ctrl+V" Command="ApplicationCommands.Paste"  /&gt;

                &lt;/ContextMenu&gt;

            &lt;/syncfusion:DockingManager.ContextMenu&gt;

            <TextBox syncfusion:DockingManager.SideInDockedMode="Left"

              syncfusion:DockingManager.State="Dock">

                I am a Docking panel

            &lt;/TextBox&gt;

        &lt;/syncfusion:DockingManager&gt;



The output is as follows.



{ ![C:/Users/Hemanth/Desktop/Documentation/Images/ContextMenu.jpg](Interactive-Features_images/Interactive-Features_img23.jpeg) | markdownify }
{:.image }


_Custom Context Menu Added to the Docked Window_

The frame work provides some in-built events such as ContextMenuOpening and ContextMenuClosing, which are handled when the context menu opens or  closes.



[C#]

//Creating instance for the Docking Manager.

DockingManager = new DockingManager();

//Triggering using the context menu events.

DockingManager.ContextMenuOpening += new ContextMenuEventHandler(DockingManager_ContextMenuOpening);

DockingManager.ContextMenuClosing += new ContextMenuEventHandler(DockingManager_ContextMenuClosing);



There are some in-built command bindings to handle the actions of the context menu, which will be much handy.

ContextMenuItemClick Event

It is a bubbling routed event, which is handled when a context menu item click is completed.

Use the following code snippet below for triggering this event.



[C#]

//Creating instance for the Docking Manager.

DockingManager = new DockingManager();

//Triggering using the context menu click events.

DockingManager.ContextMenuItemClick += new RoutedEventHandler(DockingManager_ContextMenuItemClick);

/// &lt;summary&gt;

/// Handles the ContextMenuItemClick event of the Docking Manager

/// &lt;/summary&gt;

/// <param name="sender">The source of the event.&lt;/param&gt;

/// <param name="e">The &lt;see cref="System.Windows.RoutedEventArgs"/&gt; instance containing the event data.&lt;/param&gt;

void DockingManager_ContextMenuItemClick(object sender, RoutedEventArgs e)

{

          //Set the required actions here.

}





### Providing Custom Menu Items

Custom Menu Items

A dockable window is well associated with a default context menu with default menu items. You can also add custom menu items to the existing context menu items of the dockable window. CustomMenuItems property is used for this purpose.

CustomMenuItems - This property is attached to a docking manager child, and gives an ability to add some additional menu items to the context menu. This can easily extend GUI functionality by using the Custom menu items.

To add the custom menu item:



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager Name="DockingManager1" &gt;            &lt;syncfusion:DockingManager.CustomMenuItems&gt;                &lt;syncfusion:CustomMenuItemCollection&gt;                    &lt;syncfusion:CustomMenuItem Header="CustomItem" /&gt;                &lt;/syncfusion:CustomMenuItemCollection&gt;            &lt;/syncfusion:DockingManager.CustomMenuItems&gt;            &lt;TextBox syncfusion:DockingManager.SideInDockedMode="Left" syncfusion:DockingManager.State="Dock"/&gt;        &lt;/syncfusion:DockingManager&gt;	</td></tr>
<tr>
<td>
[C#]//Creating instance for the Docking Manager.DockingManager = new DockingManager();//Creating instance for custom items collections.CustomMenuItemCollection collection = new CustomMenuItemCollection();//Creating custom menu items.CustomMenuItem customitem = new CustomMenuItem();//Setting the header for the items.customitem.Header = "Custom Item";//Adding the items to the collection.collection.Add(customitem);//Setting the custom menu items.DockingManager.SetCustomMenuItems(DockingManager, collection);</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/Customenuitem.jpg](Interactive-Features_images/Interactive-Features_img24.jpeg) | markdownify }
{:.image }


_Custom Menu Item added to the Context Menu_                      

### Collapse Default MenuItems

We can disable the default menu item such as Dockable, Floating, AutoHide and so on. This can be done by CollapseDefaultContextMenuItems property.. The usage is shown below.



<table>
<tr>
<td>
[XAML]&lt;syncfusion:DockingManager Name="DockingManager1" CollapseDefaultContextMenuItems="True" &gt;            &lt;syncfusion:DockingManager.CustomMenuItems&gt;                &lt;syncfusion:CustomMenuItemCollection&gt;                    &lt;syncfusion:CustomMenuItem Header="CustomItem" /&gt;                &lt;/syncfusion:CustomMenuItemCollection&gt;            &lt;/syncfusion:DockingManager.CustomMenuItems&gt;            &lt;TextBox syncfusion:DockingManager.SideInDockedMode="Left" syncfusion:DockingManager.State="Dock"/&gt;        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager = new DockingManager();//Creating instance for custom items collections.CustomMenuItemCollection collection = new CustomMenuItemCollection();//Creating custom menu items.CustomMenuItem customitem = new CustomMenuItem();//Setting the header for the items.customitem.Header = "Custom Item";//Adding the items to the collection.collection.Add(customitem);//Setting the custom menu items.DockingManager.SetCustomMenuItems(DockingManager, collection);DockingManager.CollapseDefaultContextMenuItems = true;</td></tr>
</table>


{ ![C:/Users/Hemanth/Desktop/Documentation/Images/CollapseDefaultMenu.jpg](Interactive-Features_images/Interactive-Features_img25.jpeg) | markdownify }
{:.image }


_Collapse Default Menuitems_

## Context Menu, Context Menu Button Visibility

IsContextMenuButtonVisible property is used to control the visibility of the Context Menu Button, which is available when the Header of Docked Window or Float Window is right-clicked. The display of Context Menu can be disabled by setting IsContextMenuVisibile to False.

The following code illustrates the same:



<table>
<tr>
<td>
[XAML]        &lt;syncfusion:DockingManager Name="DockingManager" IsContextMenuVisible="False"&gt;        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.IsContextMenuVisible= "false";</td></tr>
</table>


The default value is set to True.  This property can also be applied to every child inside the DockingManager as shown below:



<table>
<tr>
<td>
[XAML]        &lt;syncfusion:DockingManager Name= "DockingManager"&gt;            &lt;Grid Name="grid1" syncfusion:DockingManager.IsContextMenuVisible="False"&gt;                &lt;Grid&gt;        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]       DockingManager.SetIsContextMenuVisible(grid1,false);</td></tr>
</table>


IsContextMenuButtonVisible property is used to control the visibility of the Context Menu Button (available when child Window is in dock state). The display of Context Menu can be disabled by setting IsContextMenuButtonVisible to False.

The following code illustrates the same.



<table>
<tr>
<td>
[XAML]        &lt;syncfusion:DockingManager Name="DockingManager" IsContextMenuButtonVisible="False"&gt;            &lt;Grid/&gt;        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.IsContextMenuButton="False";</td></tr>
</table>


The default value is set to True.



{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/image354521017.jpg](Interactive-Features_images/Interactive-Features_img26.jpeg) | markdownify }
{:.image }


_IsContextMenuButtonVisible=”False”_



This property can also be applied to every child inside the DockingManager as shown below.



<table>
<tr>
<td>
[XAML]        &lt;syncfusion:DockingManager Name="DockingManager"&gt;            &lt;Grid Name="grid1" syncfusion:DockingManager.IsContextMenuButtonVisible="False"&gt;                &lt;Grid&gt;        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetIsContextMenuButtonVisible(grid1,false);</td></tr>
</table>


{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/image1839791936.jpg](Interactive-Features_images/Interactive-Features_img27.jpeg) | markdownify }
{:.image }


_IsContextMenuButtonVisible=”True” for Individual Child_                

### Layout Related Features

#### DesierWidth and DesierHeight in Dock/Float Modes

Height and width of the docking window in the docked state is set by using properties like DesiredWidthInDockedMode and DesiredHeightInDockedMode respectively.

To set the height and width for the DockingManager elements in the docked state, use the following code snippet.



<table>
<tr>
<td>
[XAML]      &lt;!--To set the width and height of the element in Docked Mode--&gt;        &lt;Grid Name="Properties" sftools:DockingManager.DesiredWidthInDockedMode="400" sftools:DockingManager.DesiredHeightInDockedMode="400"/ &gt;</td></tr>
<tr>
<td>
[C#]//To set the width of the element in Docked Mode.this.DockingManager.SetDesiredWidthInDockedMode(Properties, 400);//To set the Height of the element in Docked Mode.this.DockingManager.SetDesiredHeightInDockedMode(Properties, 400);</td></tr>
</table>


The Height and Width of the DockingManager elements in the floating state is set using the DesiredWidthInFloatingMode and DesiredHeightInFloatingMode properties, respectively.

Use the following code to set the above properties.



<table>
<tr>
<td>
[XAML]        &lt;!--To set the width and height of the element in the Docked Mode--&gt;        &lt;Grid Name="Properties" sftools:DockingManager.DesiredWidthInFloatingMode="400" sftools:DockingManager.DesiredHeightInFloatingMode="400"/&gt;</td></tr>
<tr>
<td>
[C#]//To set the width of the element in Floating Mode.this.DockingManager.SetDesiredWidthInFloatingMode(Properties, 300);//To set the Height of the element in Floating Mode.this.DockingManager.SetDesiredHeightInFloatingMode(Properties, 200);</td></tr>
</table>


#### Hot Tracking the Dock Window

The docking elements can be highlighted when the mouse is hovered over a Docking window. This feature is enabled using the IsEnableHotTracking property.

To enable / disable hot tracking feature in DockingManager, use the following code.



<table>
<tr>
<td>
[XAML]        &lt;!-- To enable HotTracking in Docking Manager --&gt;        &lt;sftools:DockingManager Name="DocManager1" IsEnableHotTracking="True"/&gt;        &lt;!-- To disable HotTracking in Docking Manager --&gt;        &lt;sftools:DockingManager Name="DocManager1" IsEnableHotTracking="False"/&gt;</td></tr>
<tr>
<td>
[C#]//To Enable HotTracking in Docking Manager.this.DockingManager.IsEnableHotTracking = true;//To Disable HotTracking in Docking Manager.this.DockingManager.IsEnableHotTracking = false;</td></tr>
</table>
#### Using SizetoContentInFloat

The Float window can be resized to its child size by setting the sizeToContentInFloat property to True. The Float window will be resized to its child size when dragged from Dock to Float state. 



{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/image393773567.jpg](Interactive-Features_images/Interactive-Features_img28.jpeg) | markdownify }
{:.image }


_SizetoContentInFloat=”True”_



The following code illustrates the same.



<table>
<tr>
<td>
[XAML]        &lt;syncfusion:DockingManager Name="DockingManager" &gt;            &lt;usercontrol1 Name="control1" width=200 height=200 syncfusion:DockingManager. SizeToContentInFloat="true" /&gt;        &lt;/syncfusion:DockingManager&gt;</td></tr>
<tr>
<td>
[C#]DockingManager.SetSizetoContentInFloat(control1,true);</td></tr>
</table>


When user control is dragged out from Dock state the Float window generated will automatically resize itself to the size of the user control. But when user resizes the Float window and changes it to the Dock state again, it converts it back to the Float state. The Float window returns to its previous size.

#### Customizing Document Tab Control and MDI Document

The following three properties allow you to customize the styles of Tab control and MDI document. This feature is integrated with both DockingManager and Document Container. 

* DocumentTabControlStyle 
* DocumentTabItemStyle 
* DocumentMDIHeaderStyle 



#### DocumentTabControlStyle

This property allows you to specify the your own customized style for the Tab control in both DockingManager and Document Container. The following code snippet will illustrate this.



[XAML]

&lt;syncfusion:DockingManager x:Name="DockingManager" ContainerMode="TDI" Height="Auto"&gt;

            &lt;syncfusion:DockingManager.DocumentTabControlStyle&gt;

                &lt;Style TargetType="{x:Type syncfusion:TabControlExt}"&gt;

                    &lt;Setter Property="TabStripPlacement" Value="Left"/&gt;

                    &lt;Setter Property="CloseButtonType" Value="Individual"/&gt;

                    &lt;Setter Property="ShowTabItemContextMenu" Value="False"/&gt;

                &lt;/Style&gt;

            &lt;/syncfusion:DockingManager.DocumentTabControlStyle&gt;

        &lt;/syncfusion:DockingManager&gt;



{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/DocumentTabControlStyle.jpg](Interactive-Features_images/Interactive-Features_img29.jpeg) | markdownify }
{:.image }


_DocumentTabControlStyle in TDI mode_

#### DocumentTabItemStyle

This property allows you to specify your customized style for tab items inside the Tab control in both DockingManager and Document Container. The following code snippet will illustrate this.



[XAML]

&lt;syncfusion:DockingManager x:Name="DockingManager" ContainerMode="TDI" Height="Auto"&gt;

            &lt;syncfusion:DockingManager.DocumentTabItemStyle&gt;

                &lt;Style TargetType="{x:Type syncfusion:TabItemExt}"&gt;

                    &lt;Setter Property="Background" Value="Green" /&gt;

                &lt;/Style&gt;

            &lt;/syncfusion:DockingManager.DocumentTabItemStyle&gt;

&lt;/syncfusion:DockingManager&gt;



{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/DocumentTabItemStyle%20in%20TDI%20mode.jpg](Interactive-Features_images/Interactive-Features_img30.jpeg) | markdownify }
{:.image }


_DocumentTabItemStyle in TDI mode_

#### DocumentMDIHeaderStyle

This property is used to specify the customized style for the MDI window header, in both DockingManager and Document Container. The following code snippet will illustrate this.



[XAML]

&lt;syncfusion:DockingManager x:Name="DockingManager" ContainerMode="MDI" Height="Auto"&gt;

            &lt;syncfusion:DockingManager.DocumentMDIHeaderStyle&gt;

                &lt;Style TargetType="{x:Type syncfusion:DocumentHeader}"&gt;

                    &lt;Setter Property="Foreground" Value="Orange"/&gt;

                    &lt;Setter Property="Background" Value="Green"/&gt;

                    &lt;Setter Property="Height" Value="50"/&gt;

                    &lt;Setter Property="Header" Value="Document"/&gt;

                &lt;/Style&gt;

            &lt;/syncfusion:DockingManager.DocumentMDIHeaderStyle&gt;

        &lt;/syncfusion:DockingManager&gt;



{ ![http://help.syncfusion.com/ug_82/WPFUI_Tools/Images/DocumentMDIHeaderStyle%20in%20MDI%20mode.jpg](Interactive-Features_images/Interactive-Features_img31.jpeg) | markdownify }
{:.image }


_DocumentMDIHeaderStyle in MDI mode_                      

