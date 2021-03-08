---
layout: post
title: AutoHide Windows | Docking Manager | Syncfusion
description: This section describes how to customize SidePanel, SideTabItem and change pinning behaviour of AutoHide window.
platform: wpf
control: DockingManager
documentation: ug
---
# Auto Hide Window in WPF DockingManager

AutoHide window is one of the state in the DockingManager. To enable Auto hidden for DockingManager's children, set its `State` value as `AutoHidden`.

![Auto hide window](Auto-Hide-Window_images/Auto-Hide-Window_img1.jpeg)


## Configuring window in Different Side

AutoHidden window can be placed in four different sides such as Top, Bottom, Left and Right. To place the four auto hidden children in four different sides, set [SideInDockedMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_SideInDockedMode) property according to its corresponding values in the DockingManager.
{% tabs %}

{% highlight XAML %}
<ContentControl syncfusion:DockingManager.Header="Top” x:Name="AutoHideWindow1"
                syncfusion:DockingManager.State="AutoHidden” syncfusion:DockingManager.SideInDockedMode="Top” />

<ContentControl syncfusion:DockingManager.Header="Left" x:Name="AutoHideWindow2"
                syncfusion:DockingManager.State="AutoHidden” syncfusion:DockingManager.SideInDockedMode="Left" />

<ContentControl syncfusion:DockingManager.Header="Right" x:Name="AutoHideWindow3"
                syncfusion:DockingManager.State="AutoHidden" syncfusion:DockingManager.SideInDockedMode="Right" />

<ContentControl syncfusion:DockingManager.Header="Bottom" x:Name="AutoHideWindow4"
                syncfusion:DockingManager.State="AutoHidden" syncfusion:DockingManager.SideInDockedMode="Bottom" />

{% endhighlight %}

{% highlight C# %}

//To place the auto hidden children in four different sides

DockingManager.SetSideInDockedMode(AutoHideWindow1, DockSide.Top);

DockingManager.SetSideInDockedMode(AutoHideWindow2, DockSide.Left);

DockingManager.SetSideInDockedMode(AutoHideWindow3, DockSide.Right);

DockingManager.SetSideInDockedMode(AutoHideWindow4, DockSide.Bottom);

{% endhighlight %}

{% endtabs %}

![Different side docking](Auto-Hide-Window_images/Auto-Hide-Window_img2.jpeg)

The AutoHideWindow can be placed on a required target window through the [TargetNameInDockedMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_TargetNameInDockedMode) property of the DockingManager. DockingWindow will auto hidden in place according to its Parent position, if any target exist. For example: Here "Output" docked at bottom of "SolutionExplorer" which docked at left side. While auto hiding Output window, it will auto hide at left due to it's TargetWindow side.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager>

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer" x:Name="SolutionExplorer"/>

<ContentControl x:Name="ServerExplorer" syncfusion:DockingManager.Header="Server Explorer"
                syncfusion:DockingManager.SideInDockedMode="Bottom"
                syncfusion:DockingManager.TargetNameInDockedMode="SolutionExplorer" />

<ContentControl x:Name="ToolBox" syncfusion:DockingManager.Header="ToolBox"
                syncfusion:DockingManager.SideInDockedMode="Right"
                syncfusion:DockingManager.TargetNameInDockedMode="SolutionExplorer" />

<ContentControl x:Name="Output" syncfusion:DockingManager.Header="Output"
                syncfusion:DockingManager.SideInDockedMode="Bottom"
                syncfusion:DockingManager.TargetNameInDockedMode="SolutionExplorer" />

<ContentControl x:Name="Properties" syncfusion:DockingManager.Header="Properties"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
                syncfusion:DockingManager.TargetNameInDockedMode="SolutionExplorer" />

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

DockingManager.SetSideInDockedMode(ServerExplorer, DockSide.Bottom);

DockingManager.SetTargetNameInDockedMode(ServerExplorer, "SolutionExplorer");

DockingManager.SetSideInDockedMode(ToolBox, DockSide.Right);

DockingManager.SetTargetNameInDockedMode(ToolBox, "SolutionExplorer");

DockingManager.SetSideInDockedMode(Output, DockSide.Bottom);

DockingManager.SetTargetNameInDockedMode(Output, "SolutionExplorer");

DockingManager.SetSideInDockedMode(Properties, DockSide.Tabbed);

DockingManager.SetTargetNameInDockedMode(Properties, "SolutionExplorer");

{% endhighlight %}

{% endtabs %}


![Configuring window in Different Side](Auto-Hide-Window_images/Auto-Hide-Window_img3.jpeg)


## Side panel Customization

The side panel and side panel header can be customized by applying its Background, BorderBrush, BorderThickness and SidePanelSize through [SidePanelBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_SidePanelBackground), [SidePanelBorderBrush](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_SidePanelBorderBrush), [SidePanelBorderThickness](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_SidePanelBorderThickness),  [SidePanelSize](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_SidePanelSize) properties of the DockingManager. You can also refer to this [sample](https://github.com/SyncfusionExamples/How-to-customize-the-auto-hide-window-of-the-docking-manager.git) which demonstrate the side panel customization.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager SidePanelBackground="Brown"
                           SidePanelBorderBrush="Yellow" SideItemsBackground="Green"
                           SidePanelBorderThickness="2,2,2,2" SideItemsBorderBrush="BlueViolet" SidePanelSize="40">

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer" syncfusion:DockingManager.State="AutoHidden" />

<ContentControl syncfusion:DockingManager.Header="ToolBox" />

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}
			
//Set Customization colors

SyncDockingManager.SidePanelBackground = new SolidColorBrush(Colors.Brown);

SyncDockingManager.SidePanelBorderBrush = new SolidColorBrush(Colors.Yellow);

SyncDockingManager.SideItemsBackground = new SolidColorBrush(Colors.Green);

SyncDockingManager.SideItemsBorderBrush = new SolidColorBrush(Colors.Violet);

SyncDockingManager.SidePanelBorderThickness = new Thickness(2, 2, 2, 2);

SyncDockingManager.SidePanelSize = 40;

{% endhighlight %}

{% endtabs %}


![Appearence customization of side panel in docking manager for wpf](Auto-Hide-Window_images/Auto-Hide-Window_img4.png)


### SideTabItem Customization

The SideTabItem can be customized using the attached properties [SideTabItemForeground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_SideTabItemForeground) and [SideTabItemBackground](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_SideTabItemBackground) of DockingManager. 


{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager">

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer" syncfusion:DockingManager.State="AutoHidden"
                syncfusion:DockingManager.SideTabItemForeground="Blue" syncfusion:DockingManager.SideTabItemBackground="Pink"/>

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//SideTabItem customization  

DockingManager.SetSideTabItemBackground(content1, (new SolidColorBrush(Colors.Pink)));
			
DockingManager.SetSideTabItemForeground(content1, (new SolidColorBrush(Colors.Blue)));

{% endhighlight %}

{% endtabs %}

![SideTabItem Customization](Auto-Hide-Window_images/Auto-Hide-Window_img5.jpeg)


## Excel-like Scrollable panel

The [EnableScrollableSidePanel](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_EnableScrollableSidePanel) feature is used to provide scroll support when Auto Hidden tab items overflow onto the side panel.  By default [EnableScrollableSidePanel](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_EnableScrollableSidePanel) value is `False`, this feature can be enabled by set its value to `True`.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="dockingManager" EnableScrollableSidePanel="True">

<ContentControl syncfusion:DockingManager.SideInDockedMode="Bottom"
                syncfusion:DockingManager.State="AutoHidden" syncfusion:DockingManager.Header="SolutionExplorer"/>

<ContentControl syncfusion:DockingManager.SideInDockedMode="Bottom"
                syncfusion:DockingManager.State="AutoHidden" syncfusion:DockingManager.Header="ToolBox"/>

<ContentControl syncfusion:DockingManager.SideInDockedMode="Bottom"
                syncfusion:DockingManager.State="AutoHidden" syncfusion:DockingManager.Header="Output" />

<ContentControl syncfusion:DockingManager.SideInDockedMode="Bottom"
                syncfusion:DockingManager.State="AutoHidden" syncfusion:DockingManager.Header="Class view" />

<ContentControl syncfusion:DockingManager.SideInDockedMode="Bottom"
                syncfusion:DockingManager.State="AutoHidden" syncfusion:DockingManager.Header="Server Explorer" />

<ContentControl syncfusion:DockingManager.SideInDockedMode="Bottom"
                syncfusion:DockingManager.State="AutoHidden" syncfusion:DockingManager.Header="Team Explorer" />

<ContentControl syncfusion:DockingManager.SideInDockedMode="Bottom"
                syncfusion:DockingManager.State="AutoHidden" syncfusion:DockingManager.Header="ErrorList" />

</syncfusion:DockingManager >

{% endhighlight %}

{% highlight C# %}

//For Scroll Support

dockingManager.EnableScrollableSidePanel = true;

{% endhighlight %}

{% endtabs %}

![Scrollable panel](Auto-Hide-Window_images/Auto-Hide-Window_img6.jpeg)


## Changing pinning behavior

Auto Hidden Tabbed window provides two different pinning behaviors AutoHideActive and AutoHideGroup modes.

`AutoHideActive` – Used to auto-hide current active element of tabbed dock window.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="dockingManager" AutoHideTabsMode="AutoHideActive">

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer" />

<ContentControl syncfusion:DockingManager.Header="ToolBox" />

<ContentControl syncfusion:DockingManager.Header="Output"  />

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//To auto-hide current active element of tabbed dock window

dockingManager.AutoHideTabsMode = AutoHideTabsMode.AutoHideActive;

{% endhighlight %}

{% endtabs %}

![AutoHideActive](Auto-Hide-Window_images/Auto-Hide-Window_img7.jpeg)


`AutoHideGroup` – Used to auto-hide the entire tabbed dock window as a group.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="dockingManager" AutoHideTabsMode="AutoHideGroup">

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer" />

<ContentControl syncfusion:DockingManager.Header="ToolBox" />

<ContentControl syncfusion:DockingManager.Header="Output" />

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//To auto-hide current active element of tabbed dock window
		
dockingManager.AutoHideTabsMode = AutoHideTabsMode.AutoHideGroup;

{% endhighlight %}

{% endtabs %}

![AutoHideGroup](Auto-Hide-Window_images/Auto-Hide-Window_img8.jpeg)


### Configuring Auto Hide Animation

The Animation speed while auto hiding a window can be configured by setting required time delay in [AnimationDelay](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_AnimationDelay) property.

{% tabs %}

{% highlight XAML %}

<ContentControl syncfusion:DockingManager.Header="item1"
                syncfusion:DockingManager.State="AutoHidden" syncfusion:DockingManager.AnimationDelay="100"/>


{% endhighlight %}

{% highlight C# %}

//Set Animation delay

Docking.SetAnimationDelay(autoHideWindow1, new Duration(TimeSpan.FromMilliseconds(100)));

{% endhighlight %}

{% endtabs %}

### Making different animation for AutoHideWindow

DockingManager supports three different built–in animations while auto-hiding the windows such as `Fade`, `scale` and `slide` that can be set through the property [AutoHideAnimationMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_AutoHideAnimationMode).

`Fade` – AutoHideWindow fades while auto hiding

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager AutoHideAnimationMode="Fade">

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer" syncfusion:DockingManager.State="AutoHidden” />

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//Set AnimationMode

Docking.AutoHideAnimationMode = AutoHideAnimationMode.Fade;

{% endhighlight %}

{% endtabs %}

`Scale` – AutoHideWindow scale while auto hiding

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager AutoHideAnimationMode="Scale">

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer" syncfusion:DockingManager.State="AutoHidden"/>

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//Set AnimationMode

Docking.AutoHideAnimationMode = AutoHideAnimationMode.Scale;

{% endhighlight %}

{% endtabs %}

`Slide` – AutoHideWindow slides while auto hiding.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager AutoHideAnimationMode="Slide">

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer"  syncfusion:DockingManager.State="AutoHidden"/>

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//Set AnimationMode

Docking.AutoHideAnimationMode = AutoHideAnimationMode.Slide;

{% endhighlight %}

{% endtabs %}

## Enabling and disabling the AutoHide functionality

The Pin button that performs Auto Hide functionality can be visible by default. It can be invisible to disable the AutoHide functionality through [AutoHideVisibility](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_AutoHideVisibility) property.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager  AutoHideVisibility="False">

<ContentControl x:Name="AutoHideWindow" syncfusion:DockingManager.Header="SolutionExplorer"/>

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//Set Visibility

SyncDockingManager.AutoHideVisibility = false;

{% endhighlight %}

{% endtabs %}

![Auto hide visibility](Auto-Hide-Window_images/Auto-Hide-Window_img9.jpeg)


To enable or disable the AutoHide functionality for a specific child in the DockingManager, [CanAutoHide](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_CanAutoHide) can be used. By default its value is `true`, this functionality can disable by set its value as `false`.

{% tabs %}

{% highlight XAML %}

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer" syncfusion:DockingManager.CanAutoHide="False" />

<ContentControl syncfusion:DockingManager.Header="ToolBox" syncfusion:DockingManager.CanAutoHide="True" />

{% endhighlight %}

{% highlight C# %}

//Disable the Auto hide functionality

DockingManager.SetCanAutoHide(SolutionExplorer, false);

//Enable the Auto hide functionality

DockingManager.SetCanAutoHide(ToolBox, true);

{% endhighlight %}

{% endtabs %}

![Auto hide visibility](Auto-Hide-Window_images/Auto-Hide-Window_img10.jpeg)

## Change AutoHide behavior like Visual Studio 2013

AutoHide panel open and close behavior can be changed as Visual Studio 2013. SidePanel can be opened by click on SideTabItem and already opened side panel can be closed by again click on the same item.  This behavior of DockingManager can be enabled by setting its [IsVs2013SidePanelEnable](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_IsVS2013SidePanelEnable) property to `True` and [IsAnimationEnabledOnMouseOver](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_IsAnimationEnabledOnMouseOver) property to `False`. 

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="Docking1"
                           IsAnimationEnabledOnMouseOver="False"
						   IsVS2013SidePanelEnable="True" >

<ContentControl syncfusion:DockingManager.Header="Content1"
                syncfusion:DockingManager.State="AutoHidden"   />

<ContentControl syncfusion:DockingManager.Header="Content2"
                syncfusion:DockingManager.State="AutoHidden"   />

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

DockingManager Docking1 = new DockingManager();

Docking1.IsAnimationEnabledOnMouseOver = false;

Docking1.IsVS2013SidePanelEnable = true;

ContentControl _content1 = new ContentControl();

DockingManager.SetHeader(_content1, "Content1");

DockingManager.SetState(_content1, DockState.AutoHidden);

ContentControl _content2 = new ContentControl();

DockingManager.SetHeader(_content2, "Content2");

DockingManager.SetState(_content2, DockState.AutoHidden);

Docking1.Children.Add(_content1);

Docking1.Children.Add(_content2);

Grid1.Children.Add(Docking1);

{% endhighlight %}

{% highlight VB %}

Dim Docking1 As DockingManager =  New DockingManager() 

Docking1.IsAnimationEnabledOnMouseOver = False

Docking1.IsVS2013SidePanelEnable = True

Dim _content1 As ContentControl =  New ContentControl() 

DockingManager.SetHeader(_content1, "Content1")

DockingManager.SetState(_content1, DockState.AutoHidden)

Dim _content2 As ContentControl =  New ContentControl() 

DockingManager.SetHeader(_content2, "Content2")

DockingManager.SetState(_content2, DockState.AutoHidden)

Docking1.Children.Add(_content1)

Docking1.Children.Add(_content2)

Grid1.Children.Add(Docking1)

{% endhighlight %}

{% endtabs %}


## AutoHide Animation enabled on Mouse Click

On mouse over the AutoHidden tab, the auto hide animation starts. To disable this functionality, set the property [IsAnimationEnabledOnMouseOver](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_IsAnimationEnabledOnMouseOver) as `False` that changes the auto hide tab start animation behavior. By default, its values is `True`.


{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager IsAnimationEnabledOnMouseOver="False">

<ContentControl x:Name="AutoHideWindow1"
                syncfusion:DockingManager.Header="SolutionExplorer"
                syncfusion:DockingManager.State="AutoHidden" />

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

SyncDockingManager.IsAnimationEnabledOnMouseOver = false;

{% endhighlight %}

{% endtabs %}

## Allow or restrict dragging the AutoHide Window

You can allow dragging of the auto hide window in the `DockingManager` by using the [CanDragAutoHidden](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_CanDragAutoHidden) property value as `true`. You can restrict it by setting the `CanDragAutoHidden` property value as `false`. The default value of `CanDragAutoHidden` property is `false`.

{% tabs %}
{% highlight XAML %}

<syncfusion:DockingManager Name="dockingManager">

     <!--Disable dragging--> 
    <ContentControl Content="First Window"
                    syncfusion:DockingManager.Header="Item1" 
                    syncfusion:DockingManager.State="AutoHidden" 
                    syncfusion:DockingManager.CanDragAutoHidden="False" 
                    Name="AutoHideWindow1" />

     <!--Enable dragging-->
    <ContentControl Content="Second Window"
                    syncfusion:DockingManager.Header="Item2"            
                    syncfusion:DockingManager.State="AutoHidden" 
                    syncfusion:DockingManager.CanDragAutoHidden="True"    
                    Name="AutoHideWindow2"/>
</syncfusion:DockingManager>

{% endhighlight %}
{% highlight C# %}

// Disable dragging
ContentControl AutoHideWindow1 = new ContentControl() { Content = "First Window" };  
DockingManager.SetHeader(AutoHideWindow1, "Item1");           
DockingManager.SetState(AutoHideWindow1, DockState.AutoHidden);
DockingManager.SetCanDragAutoHidden(AutoHideWindow1, false);

// Enable dragging
ContentControl AutoHideWindow2 = new ContentControl() { Content = "Second Window" };
DockingManager.SetHeader(AutoHideWindow2, "Item2");
DockingManager.SetState(AutoHideWindow2, DockState.AutoHidden);
DockingManager.SetCanDragAutoHidden(AutoHideWindow2, true);

//Adding content control to the dockingmanager
DockingManager dockingManager = new DockingManager();
dockingManager.Children.Add(AutoHideWindow1);
dockingManager.Children.Add(AutoHideWindow2);

{% endhighlight %}
{% endtabs %}

![Auto hide window dragging restricted](Auto-Hide-Window_images/RestrictDragAutoHideItem.gif)

N> View [Sample](https://github.com/SyncfusionExamples/syncfusion-wpf-docking-manager-wpf-examples/tree/master/Samples/AutoHideWindow-Dragging) in GitHub

## Pinning / UnPinning All Window

To auto hide all docked windows in the DockingManager, call [AutoHideAllDockWindow](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_AutoHideAllDockWindow) method of the Docking Manager.

{% tabs %}

{% highlight C# %}

DockingManager.AutoHideAllDockWindow();

{% endhighlight %}

{% highlight VB %}

DockingManager.AutoHideAllDockWindow();

{% endhighlight %}

{% endtabs %}

To unpin all auto hide windows in the DockingManager, call [UnPinAllAutoHide](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_UnPinAllAutoHide) method of the Docking Manager.

{% tabs %}

{% highlight C# %}

DockingManager.UnPinAllAutoHide();

{% endhighlight %}

{% highlight VB %}

DockingManager.UnPinAllAutoHide();

{% endhighlight %}

{% endtabs %}

## Changing dock state using context menu

You can change the dock state of AutoHidden window by opening the context menu and selecting the required state in context menu items. The items in context menu is enabled and disabled based on [CanDock](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_CanDockProperty), [CanFloat](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_CanFloatProperty) and [CanDocument](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_CanDocumentProperty) properties value.

![Change dock state of AutoHide window by context menu item click](Auto-Hide-Window_images/AutoHide-Window-Dock-State-Change.png)