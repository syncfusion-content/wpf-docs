---
layout: post
title: AutoHide Window of Syncfusion DockingManager control for WPF
description: Learn how to customize SidePanel, SideTabItem and change pinning behaviour of AutoHide window
platform: wpf
control: DockingManager
documentation: ug
---
# Auto Hide Window

AutoHide window is one of the state in the DockingManager. To enable Auto hidden for DockingManager's children, set its `State` value as `AutoHidden`.

![](Auto-Hide-Window_images/Auto-Hide-Window_img1.jpeg)


## Configuring window in Different Side

AutoHidden window can be placed in four different sides such as Top, Bottom, Left and Right. To place the four auto hidden children in four different sides, set `SideInDockedMode` property according to its corresponding values in the DockingManager.
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

{% endtabs %}

![](Auto-Hide-Window_images/Auto-Hide-Window_img2.jpeg)



The AutoHideWindow can be placed on a required target window through the `TargetNameInDockedMode` property of the DockingManager. DockingWindow will auto hidden in place according to its Parent position, if any target exist. For example: Here "Output" docked at bottom of "SolutionExplorer" which docked at left side. While auto hiding Output window, it will auto hide at left due to it's TargetWindow side.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager>

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer" x:Name="SolutionExplorer"/>

<ContentControl syncfusion:DockingManager.Header="Server Explorer"
                syncfusion:DockingManager.SideInDockedMode="Bottom"
                syncfusion:DockingManager.TargetNameInDockedMode="AutoHideWindow1" />

<ContentControl syncfusion:DockingManager.Header="ToolBox"
                syncfusion:DockingManager.SideInDockedMode="Right"
                syncfusion:DockingManager.TargetNameInDockedMode="AutoHideWindow1" />

<ContentControl syncfusion:DockingManager.Header="Output"
                syncfusion:DockingManager.SideInDockedMode="Bottom"
                syncfusion:DockingManager.TargetNameInDockedMode="AutoHideWindow1" />

<ContentControl syncfusion:DockingManager.Header="Properties"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
                syncfusion:DockingManager.TargetNameInDockedMode="AutoHideWindow1" />

</syncfusion:DockingManager>

{% endhighlight %}

{% endtabs %}


![](Auto-Hide-Window_images/Auto-Hide-Window_img3.jpeg)


## Side panel Customization

The side panel and side panel header can be customized by applying its Background, BorderBrush and BorderThickness through SidePanelBackground, SidePanelBorderBrush, SidePanelBorderThickness, SideItemBackground and SideItemBorderBrush properties of the DockingManager.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager SidePanelBackground="Brown"
                           SidePanelBorderBrush="Yellow" SideItemsBackground="Green"
                           SidePanelBorderThickness="2,2,2,2" SideItemsBorderBrush="BlueViolet">

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer" syncfusion:DockingManager.State="AutoHidden" />

<ContentControl syncfusion:DockingManager.Header="ToolBox" />

</syncfusion:DockingManager>

{% endhighlight %}

{% endtabs %}


![](Auto-Hide-Window_images/Auto-Hide-Window_img4.jpeg)


### SideTabItem Customization

The SideTabItem can be customized using the attached properties `SideTabItemForeground` and `SideTabItemBackground` of DockingManager.


{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager">

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer" syncfusion:DockingManager.State="AutoHidden"
                syncfusion:DockingManager.SideTabItemForeground="Blue" syncfusion:DockingManager.SideTabItemBackground="Pink"/>

</syncfusion:DockingManager>



{% endhighlight %}

{% endtabs %}

![](Auto-Hide-Window_images/Auto-Hide-Window_img5.jpeg)


## Excel-like Scrollable panel

The `EnableScrollableSidePanel` feature is used to provide scroll support when Auto Hidden tab items overflow onto the side panel.  By default EnableScrollableSidePanel value is `False`, this feature can be enabled by set its value to `True`.

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

{% endtabs %}

![](Auto-Hide-Window_images/Auto-Hide-Window_img6.jpeg)



## Changing pinning behavior

Auto Hidden Tabbed window provides two different pinning behaviors `AutoHideActive` and `AutoHideGroup` modes.

`AutoHideActive` – Used to auto-hide current active element of tabbed dock window.

{% tabs %}

{% highlight XAML %}
<syncfusion:DockingManager x:Name="DockingManager" AutoHideTabsMode="AutoHideActive">

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer" />

<ContentControl syncfusion:DockingManager.Header="ToolBox" />

<ContentControl syncfusion:DockingManager.Header="Output"  />

</syncfusion:DockingManager>



{% endhighlight %}

{% endtabs %}

![](Auto-Hide-Window_images/Auto-Hide-Window_img7.jpeg)


`AutoHideGroup` – Used to auto-hide the entire tabbed dock window as a group.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager" AutoHideTabsMode="AutoHideGroup">

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer" />

<ContentControl syncfusion:DockingManager.Header="ToolBox" />

<ContentControl syncfusion:DockingManager.Header="Output" />

</syncfusion:DockingManager>

{% endhighlight %}

{% endtabs %}

![](Auto-Hide-Window_images/Auto-Hide-Window_img8.jpeg)




### Configuring Auto Hide Animation

The Animation speed while auto hiding a window can be configured by setting required time delay in `AnimationDelay` property.

{% tabs %}

{% highlight XAML %}

<ContentControl syncfusion:DockingManager.Header="item1"
                syncfusion:DockingManager.State="AutoHidden" syncfusion:DockingManager.AnimationDelay="100"/>


{% endhighlight %}

{% endtabs %}

### Making different animation for AutoHideWindow

DockingManager supports three different built–in animations while auto-hiding the windows such as `Fade`, `scale` and `slide` that can be set through the property `AutoHideAnimationMode`.



`Fade` – AutoHideWindow fades while auto hiding

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager AutoHideAnimationMode="Fade">

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer" syncfusion:DockingManager.State="AutoHidden” />

</syncfusion:DockingManager>


{% endhighlight %}

{% endtabs %}

`Scale` – AutoHideWindow scale while auto hiding

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager AutoHideAnimationMode="Scale">

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer" syncfusion:DockingManager.State="AutoHidden"/>

</syncfusion:DockingManager>



{% endhighlight %}

{% endtabs %}

`Slide` – AutoHideWindow slides while auto hiding.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager AutoHideAnimationMode="Slide">

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer"  syncfusion:DockingManager.State="AutoHidden"/>

</syncfusion:DockingManager>



{% endhighlight %}

{% endtabs %}

## Enabling and disabling the AutoHide functionality

The Pin button that performs Auto Hide functionality can be visible by default. It can be invisible to disable the AutoHide functionality through `AutoHideVisibility` property.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager  AutoHideVisibility="False">

<ContentControl x:Name="AutoHideWindow" syncfusion:DockingManager.Header="SolutionExplorer"/>

</syncfusion:DockingManager>


{% endhighlight %}

{% endtabs %}

![](Auto-Hide-Window_images/Auto-Hide-Window_img9.jpeg)


To enable or disable the AutoHide functionality for a specific child in the DockingManager, `CanAutoHide` can be used. By default its value is `true`, this functionality can disable by set its value as `false`.

{% tabs %}

{% highlight XAML %}

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer" syncfusion:DockingManager.CanAutoHide="False" />

<ContentControl syncfusion:DockingManager.Header="ToolBox" syncfusion:DockingManager.CanAutoHide="True" />


{% endhighlight %}

{% endtabs %}

![](Auto-Hide-Window_images/Auto-Hide-Window_img10.jpeg)

## Change AutoHide behavior like Visual Studio 2013

AutoHide panel open and close behavior can be changed as Visual Studio 2013. SidePanel can be opened by click on SideTabItem and already opened side panel can be closed by again click on the same item.  This behavior of DockingManager can be enabled by setting its `IsVs2013SidePanelEnabled` property to `True` and `IsAnimationEnabledOnMouseOver` property to `False`. 

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

{% endtabs %}


{% tabs %}

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

On mouse over the AutoHidden tab, the auto hide animation starts. To disable this functionality, set the property `IsAnimationEnabledOnMouseOver` as `False` that changes the auto hide tab start animation behavior. By default, its values is `True`.


{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager IsAnimationEnabledOnMouseOver="False">

<ContentControl x:Name="AutoHideWindow1"
                syncfusion:DockingManager.Header="SolutionExplorer"
                syncfusion:DockingManager.State="AutoHidden" />

</syncfusion:DockingManager>


{% endhighlight %}

{% endtabs %}

## Pinning / UnPinning All Window

To auto hide all docked windows in the DockingManager, call `AutoHideAllDockWindow` method of the Docking Manager.

{% tabs %}

{% highlight C# %}

DockingManager.AutoHideAllDockWindow();

{% endhighlight %}

{% highlight VB %}

DockingManager.AutoHideAllDockWindow();

{% endhighlight %}

{% endtabs %}

To unpin all auto hide windows in the DockingManager, call `UnPinAllAutoHide` method of the Docking Manager.

{% tabs %}

{% highlight C# %}

DockingManager.UnPinAllAutoHide();

{% endhighlight %}

{% highlight VB %}

DockingManager.UnPinAllAutoHide();

{% endhighlight %}

{% endtabs %}

