---
layout: post
title: Auto-Hide Window
description: Auto-Hide Window
platform: wpf
control: DockingManager
documentation: ug
---
## Auto Hide Window

AutoHide window is one of the state in the DockingManager. To make children of the DockingManager to Autohidden, set its **State** value **as** **AutoHidden**. 

![](Auto-Hide-Window_images/Auto-Hide-Window_img1.jpeg)


### Configuring window in Different Side

AutoHidden window can be placed in four different sides such as Top, Bottom, Left, and Right. To place the four autohidden children in four different sides, set **SideInDockedMode** property according to its corresponding values in the DockingManager.

{% highlight xml %}
<ContentControl x:Name="AutoHideWindow1"

syncfusion:DockingManager.Header="Top”                                                    syncfusion:DockingManager.State="AutoHidden”                                                  syncfusion:DockingManager.SideInDockedMode="Top”></ContentControl>

<ContentControl x:Name="AutoHideWindow2" syncfusion:DockingManager.Header="Left"                                                   syncfusion:DockingManager.State="AutoHidden”                                                   syncfusion:DockingManager.SideInDockedMode="Left"></ContentControl>

<ContentControl x:Name="AutoHideWindow3" syncfusion:DockingManager.Header=" Right "                                         syncfusion:DockingManager.State="AutoHidden"

syncfusion:DockingManager.SideInDockedMode="Right"></ContentControl>

<ContentControl x:Name="AutoHideWindow4" syncfusion:DockingManager.Header=" Bottom"

syncfusion:DockingManager.State="AutoHidden"

syncfusion:DockingManager.SideInDockedMode="Bottom"></ContentControl>





{% endhighlight %}

![](Auto-Hide-Window_images/Auto-Hide-Window_img2.jpeg)




The AutoHidewindow can be placed according to the TargetName through the property **TargetNameInDockedMode** property of the DockingManager.  When autohide the dockingwindow , it will autohidden in the place according to its Parent position. For instance, when the parent is in left side, by default the autohide window will place in the left side, irrespective of its SideInDockedMode value.

{% highlight xml %}

<syncfusion:DockingManager >

<ContentControl x:Name="AutoHideWindow1" syncfusion:DockingManager.Header="SolutionExplorer" 

></ContentControl>

<ContentControl x:Name="AutoHideWindow2" syncfusion:DockingManager.Header="Server Explorer"

syncfusion:DockingManager.SideInDockedMode="Bottom"                       

syncfusion:DockingManager.TargetNameInDockedMode="AutoHideWindow1"></ContentControl>

<ContentControl x:Name="AutoHideWindow3" syncfusion:DockingManager.Header="ToolBox" 

syncfusion:DockingManager.SideInDockedMode="Right"

syncfusion:DockingManager.TargetNameInDockedMode="AutoHideWindow1"></ContentControl>

<ContentControl  x:Name="AutoHideWindow4" syncfusion:DockingManager.Header="Output"      

syncfusion:DockingManager.SideInDockedMode="Bottom"

syncfusion:DockingManager.TargetNameInDockedMode="AutoHideWindow1"></ContentControl>

<ContentControl  x:Name="AutoHideWindow5" syncfusion:DockingManager.Header="Properties"         

syncfusion:DockingManager.SideInDockedMode="Tabbed"

syncfusion:DockingManager.TargetNameInDockedMode="AutoHideWindow1"></ContentControl>

</syncfusion:DockingManager>





{% endhighlight %}

![](Auto-Hide-Window_images/Auto-Hide-Window_img3.jpeg)


###  Side panel Customization

The side panel and side panel header can be customize by applying its background, borderbrush and  borderthickness  through  **SidePanelBackground , SidePanelBorderBrush ,SidePanelBorderThickness, SideItemBackground and SideItemBorderBrush** properties of the DockingManager.

{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager" SidePanelBackground="Brown" SidePanelBorderBrush="Yellow" SidePanelBorderThickness="2,2,2,2" SideItemsBackground="Green" SideItemsBorderBrush="BlueViolet"  >

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer"

syncfusion:DockingManager.State="AutoHidden"

></ContentControl>

<ContentControl syncfusion:DockingManager.Header="ToolBox"         

></ContentControl>

</syncfusion:DockingManager>





{% endhighlight %}

![](Auto-Hide-Window_images/Auto-Hide-Window_img4.jpeg)


#### SideTabItem Customization

The SideTabItem can be customized using an attached property **SideTabItemForeground** and **SideTabItemBackground**  of DockingManager.

{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager"  >

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer"

syncfusion:DockingManager.State="AutoHidden"

syncfusion:DockingManager.SideTabItemForeground="Blue"

syncfusion:DockingManager.SideTabItemBackground="Pink"

></ContentControl>

</syncfusion:DockingManager>



{% endhighlight %}

![](Auto-Hide-Window_images/Auto-Hide-Window_img5.jpeg)


### Excel-like Scrollable panel

This feature **EnableScrollableSidePanel** used to provide scroll support when Auto Hidden tab items get overflow on Side panel.  By default, its values is **False**,to enable this feature turns its values to **True**.

{% highlight xml %}

<syncfusion:DockingManager x:Name="dockingManager" EnableScrollableSidePanel="True">
        <ContentControl 

                     syncfusion:DockingManager.SideInDockedMode="Bottom"
                     syncfusion:DockingManager.State="AutoHidden"
                     syncfusion:DockingManager.Header="SolutionExplorer" />

        <ContentControl                          
                         syncfusion:DockingManager.SideInDockedMode="Bottom"
                         syncfusion:DockingManager.State="AutoHidden"
                         syncfusion:DockingManager.Header="ToolBox"/>
        <ContentControl 

                        syncfusion:DockingManager.SideInDockedMode="Bottom"
                        syncfusion:DockingManager.State="AutoHidden"
                       syncfusion:DockingManager.Header="Output" />

        <ContentControl
                                   
          syncfusion:DockingManager.SideInDockedMode="Bottom"
          syncfusion:DockingManager.State="AutoHidden"
          syncfusion:DockingManager.Header="Class view" />


        <ContentControl

           syncfusion:DockingManager.SideInDockedMode="Bottom"
           syncfusion:DockingManager.State="AutoHidden"
           syncfusion:DockingManager.Header="Server Explorer" />

        <ContentControl
                                   
         syncfusion:DockingManager.SideInDockedMode="Bottom"
         syncfusion:DockingManager.State="AutoHidden"
         syncfusion:DockingManager.Header="Team Explorer" />

        <ContentControl

           syncfusion:DockingManager.SideInDockedMode="Bottom"
           syncfusion:DockingManager.State="AutoHidden"
           syncfusion:DockingManager.Header="ErrorList" />


      </syncfusion:DockingManager >





{% endhighlight %}




![](Auto-Hide-Window_images/Auto-Hide-Window_img6.jpeg)



### Changing pinning behavior        

Auto Hidden Tabbed window provides two different pinning behavior are **AutoHideActive** and **AutoHideGroup** modes of **AutoHideTabsMode** property.

**AutoHideActive** – Used to Auto Hide current active element of Tabbed Dock Window.

{% highlight xml %}
<syncfusion:DockingManager x:Name="DockingManager" AutoHideTabsMode="AutoHideActive">

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer"

></ContentControl>

<ContentControl syncfusion:DockingManager.Header="ToolBox"         

></ContentControl>

<ContentControl syncfusion:DockingManager.Header="Output"         

></ContentControl>

</syncfusion:DockingManager>



{% endhighlight %}

![](Auto-Hide-Window_images/Auto-Hide-Window_img7.jpeg)


**AutoHideGroup** **–** Used to Auto Hide Entire Tabbed Dock Window as a group.

{% highlight xml %}
<syncfusion:DockingManager x:Name="DockingManager" AutoHideTabsMode="AutoHideGroup">

<ContentControl syncfusion:DockingManager.Header="SolutionExplorer"

></ContentControl>

<ContentControl syncfusion:DockingManager.Header="ToolBox"         

></ContentControl>

<ContentControl syncfusion:DockingManager.Header="Output"         

></ContentControl>

</syncfusion:DockingManager>





{% endhighlight %}

![](Auto-Hide-Window_images/Auto-Hide-Window_img8.jpeg)




### Configuring Auto Hide Animation

The Animation speed while Auto Hiding a window can be configured by setting required time delay to **AnimationDelay** property.

{% highlight xml %}

<ContentControl syncfusion:DockingManager.Header="item1"                                       syncfusion:DockingManager.State="AutoHidden" syncfusion:DockingManager.AnimationDelay="100"/>





{% endhighlight %}



#### Making different animation for AutoHideWindow

DockingManager supports three different built–in animations while auto-hiding the windows such as **Fade, scale, and  slide** that can be set through the property **AutoHideAnimationMode**.



* **Fade** – AutoHidewindow fades while autohiding

{% highlight xml %}

<syncfusion:DockingManager AutoHideAnimationMode="Fade">

<ContentControl x:Name="AutoHideWindow" syncfusion:DockingManager.Header="SolutionExplorer"                                                                                                    syncfusion:DockingManager.State="AutoHidden” ></ContentControl>



</syncfusion:DockingManager>



{% endhighlight %}

* **Scale** –AutoHidewindow  scale while autohiding

{% highlight xml %}

<syncfusion:DockingManager AutoHideAnimationMode="Scale">

<ContentControl x:Name="AutoHideWindow" syncfusion:DockingManager.Header="SolutionExplorer"                                                                                                    syncfusion:DockingManager.State="AutoHidden">

</ContentControl>

</syncfusion:DockingManager>





{% endhighlight %}

* **Slide** – AutoHidewindow slides while autohiding.

{% highlight xml %}

<syncfusion:DockingManager AutoHideAnimationMode="Slide">

<ContentControl x:Name="AutoHideWindow" syncfusion:DockingManager.Header="SolutionExplorer"                                                                                                   syncfusion:DockingManager.State="AutoHidden"

></ContentControl>

</syncfusion:DockingManager>





{% endhighlight %}

### Enabling and disabling the Autohide functionality

The Pin button which performs Auto Hide functionality, can be visible by default. It can invisible to disable the AutoHide functionality through **AutoHideVisibility** property. 

{% highlight xml %}

<syncfusion:DockingManager  AutoHideVisibility="False">

<ContentControl x:Name="AutoHideWindow" syncfusion:DockingManager.Header="SolutionExplorer"                                                   

></ContentControl>             

</syncfusion:DockingManager>







{% endhighlight %}

![](Auto-Hide-Window_images/Auto-Hide-Window_img9.jpeg)


To enable or disable the Autohide functionality for a specific child in the DockingManager , an attached property **CanAutoHide** is used. By default its value is **true**,to disable this functionality turn its value to **false**.

{% highlight xml %}

<ContentControl x:Name="AutoHideWindow1" syncfusion:DockingManager.Header="SolutionExplorer"                                                                                                   syncfusion:DockingManager.CanAutoHide="False"

></ContentControl>

<ContentControl x:Name="AutoHideWinodw2" syncfusion:DockingManager.Header="ToolBox"                                                   syncfusion:DockingManager.CanAutoHide="True"></ContentControl>







{% endhighlight %}

![](Auto-Hide-Window_images/Auto-Hide-Window_img10.jpeg)


### AutoHide Animation enabled on Mouse Click

Whenever mouse over the AutoHidden tab, the autohide animation will start. To disable this functionality, set the property **IsAnimationEnabledOnMouseOver** as **False** that allows to click the autohide tab to start autohide animation. By default, its values is **True**.

{% highlight xml %}

<syncfusion:DockingManager IsAnimationEnabledOnMouseOver="False">

<ContentControl x:Name="AutoHideWindow1" syncfusion:DockingManager.Header="SolutionExplorer"

syncfusion:DockingManager.State="AutoHidden"

></ContentControl>

</syncfusion:DockingManager>



{% endhighlight %}


### Pinning / UnPinning All Window

To autohide all docked windows in the DockingManager, call **AutoHideAllDockWindow** method of the Docking Manager.

{% highlight xml %}

DockingManager. AutoHideAllDockWindow();



{% endhighlight %}

To unpin all autohide windows in the DockingManager, call **UnPinAllAutoHide** method of the Docking Manager.

{% highlight c%}

[C#]

DockingManager.UnPinAllAutoHide();





{% endhighlight %}

