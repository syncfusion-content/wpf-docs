---
layout: post
title: Tabbed Window in WPF Docking control | Syncfusion®
description: Learn here all about Tabbed Window support in Syncfusion® WPF Docking (DockingManager) control and more.
platform: WPF
control: DockingManager
documentation: ug
---
# Tabbed Window in WPF Docking (DockingManager)

Child window can be arranged as Tabbed windows by setting TargetName and side value as `Tabbed` using the property [SideInDockedMode](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockItem.html#Syncfusion_Windows_Tools_Controls_DockItem_SideInDockedMode).

![WPF Docking Tabbed Window](TabbedWindow_images/wpf-docking-tabbed-window.jpeg)


##  Tab alignments

The tabs of the Docked window are placed at the bottom, by default. To place the tabs of the docked window at different sides set the property [DockTabAlignment](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_DockTabAlignment) with desired values such as Top, Bottom, Left and Right. 

* DockTabAlignment as `Bottom`

![WPF Docking Bottom TabAlignment](TabbedWindow_images/wpf-docking-bottom-tab-alignment.jpeg)


* Setting DockTabAlignment as `Left`.

{% capture codesnippet1 %}
{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" DockTabAlignment="Left">

<ContentControl  syncfusion:DockingManager.Header="Item1" x:Name="TabbedWindow1" />
	
<ContentControl syncfusion:DockingManager.Header="Item2" x:Name="TabbedWindow2"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="TabbedWindow1"/> 

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

DockingManager1.DockTabAlignment = Dock.Left;

{% endhighlight %}

{% endtabs %}
{% endcapture %}
{{ codesnippet1 | UnOrderList_Indent_Level_1 }}


![WPF Docking Left TabAlignment](TabbedWindow_images/wpf-docking-left-tab-alignment.jpeg)

* Setting DockTabAlignment as `Right`

{% capture codesnippet2 %}
{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" DockTabAlignment="Right">

<ContentControl syncfusion:DockingManager.Header="Item1"  x:Name="TabbedWindow1"/>  

<ContentControl syncfusion:DockingManager.Header="Item2" x:Name="TabbedWindow2"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="TabbedWindow1"/>
				
</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

DockingManager1.DockTabAlignment = Dock.Right;

{% endhighlight %}

{% endtabs %}
{% endcapture %}
{{ codesnippet2 | UnOrderList_Indent_Level_1 }}


![WPF Docking Right TabAlignment](TabbedWindow_images/wpf-docking-right-tab-alignment.jpeg)


* Setting DockTabAlignment as `Top`

{% capture codesnippet3 %}

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" DockTabAlignment="Top">

<ContentControl  syncfusion:DockingManager.Header="Item1" x:Name="TabbedWindow1"/> 

<ContentControl syncfusion:DockingManager.Header="Item2" x:Name="TabbedWindow2"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="TabbedWindow1"/>  

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}
			
SyncDockingManager.DockTabAlignment = Dock.Top;

{% endhighlight %}

{% endtabs %}
{% endcapture %}
{{ codesnippet3 | UnOrderList_Indent_Level_1 }}

![WPF Docking Top TabAlignment](TabbedWindow_images/wpf-docking-top-tab-alignment.jpeg)


## Closing a Tabbed window

Tabbed window provides two different closing behaviors. They are CloseActive and CloseAll modes of [CloseTabs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_CloseTabs) property.

`CloseActive` – Used to close the active element of Tabbed window.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" CloseTabs="CloseActive">

<ContentControl syncfusion:DockingManager.Header="Item1" x:Name="TabbedWindow1" />  

<ContentControl syncfusion:DockingManager.Header="Item2" x:Name="TabbedWindow2"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="TabbedWindow1"/>  

<ContentControl syncfusion:DockingManager.Header="Item3" x:Name="TabbedWindow3"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="TabbedWindow1"/>                         

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//To close the active element of Tabbed window.

SyncDockingManager.CloseTabs = CloseTabsMode.CloseActive;

{% endhighlight %}

{% endtabs %}

 `CloseAll` – Used to close all the Tabbed window.

{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" CloseTabs="CloseAll">

<ContentControl syncfusion:DockingManager.Header="Item1" x:Name="TabbedWindow1"/>  

<ContentControl syncfusion:DockingManager.Header="Item2" x:Name="TabbedWindow2"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="TabbedWindow1"/>  

<ContentControl syncfusion:DockingManager.Header="Item3" x:Name="TabbedWindow3"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="TabbedWindow1"/>                         

</syncfusion:DockingManager>

{% endhighlight %}

{% highlight C# %}

//To close all the Tabbed window.

SyncDockingManager.CloseTabs = CloseTabsMode.CloseAll;

{% endhighlight %}

{% endtabs %}

## Tabbed window order changed notification

You will be notified when the tabbed window's order is changed by using the [TabOrderChanged](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_TabOrderChanged) event. You can get the order changed tabbed window with its old and new index values by using the [TargetItem](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabOrderChangedEventArgs.html#Syncfusion_Windows_Tools_Controls_TabOrderChangedEventArgs_TargetItem), [OldIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabOrderChangedEventArgs.html#Syncfusion_Windows_Tools_Controls_TabOrderChangedEventArgs_OldIndex) and [NewIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.TabOrderChangedEventArgs.html#Syncfusion_Windows_Tools_Controls_TabOrderChangedEventArgs_NewIndex) properties.

N> The `TabOrderChanged` event occurs only during drag and drop operation. Not occurs when add or remove items interactively or using code behind.  

{% tabs %}
{% highlight XAML %}

<syncfusion:DockingManager TabOrderChanged="DockingManager1_TabOrderChanged"  
                           DockTabAlignment="Bottom"
                           x:Name="dockingManager1">
    <ContentControl syncfusion:DockingManager.Header="Item1" x:Name="tabbedWindow1" />
    <ContentControl syncfusion:DockingManager.Header="Item2" x:Name="tabbedWindow2"
                    syncfusion:DockingManager.SideInDockedMode="Tabbed"
                    syncfusion:DockingManager.TargetNameInDockedMode="tabbedWindow1"/>
    <ContentControl syncfusion:DockingManager.Header="Item3" x:Name="tabbedWindow3"
                    syncfusion:DockingManager.SideInDockedMode="Tabbed"
                    syncfusion:DockingManager.TargetNameInDockedMode="tabbedWindow2"/>
</syncfusion:DockingManager>

{% endhighlight %}
{% highlight C# %}

dockingManager1.DockTabAlignment = Dock.Bottom;
dockingManager1.TabOrderChanged += DockingManager1_TabOrderChanged;

{% endhighlight %}
{% endtabs %}

You can handle the event as follows,

{% tabs %}
{% highlight c# %}

private void DockingManager1_TabOrderChanged(object sender, TabOrderChangedEventArgs e)
{
    var dragged_Item = e.TargetItem;
    var oldIndex = e.OldIndex;
    var newIndex = e.NewIndex;
}

{% endhighlight %}
{% endtabs %}

![WPF Docking Tabbed Window Order Changed](TabbedWindow_images/wpf-docking-tabbed-window-order-changed.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-docking-manager-wpf-examples/tree/master/Samples/TabbedWindowOrdering)

## Restrict tabbed window reordering

If you want to restrict the user to reordering the tabbed window by drag and drop operation, use the [TabOrderChanging](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.DockingManager.html#Syncfusion_Windows_Tools_Controls_DockingManager_TabOrderChanging) event and set `Cancel` property value as `true`.

N> The `TabOrderChanging` event occurs only during drag and drop operation. Not occurs when add or remove items using code behind.  

{% tabs %}
{% highlight XAML %}

<syncfusion:DockingManager TabOrderChanging="DockingManager1_TabOrderChanging"
                           DockTabAlignment="Bottom"
                           x:Name="DockingManager1">
    <ContentControl  syncfusion:DockingManager.Header="Item1" x:Name="TabbedWindow1" />
    <ContentControl syncfusion:DockingManager.Header="Item2" x:Name="TabbedWindow2"
                    syncfusion:DockingManager.SideInDockedMode="Tabbed"
                    syncfusion:DockingManager.TargetNameInDockedMode="TabbedWindow1"/>
    <ContentControl syncfusion:DockingManager.Header="Item3" x:Name="TabbedWindow3"
                    syncfusion:DockingManager.SideInDockedMode="Tabbed"
                    syncfusion:DockingManager.TargetNameInDockedMode="TabbedWindow2"/>
</syncfusion:DockingManager>

{% endhighlight %}
{% highlight C# %}

dockingManager1.DockTabAlignment = Dock.Bottom;
dockingManager1.TabOrderChanging += DockingManager1_TabOrderChanging;

{% endhighlight %}
{% endtabs %}

You can handle the event as follows,

{% tabs %}
{% highlight c# %}

private void DockingManager1_TabOrderChanging(object sender, Syncfusion.Windows.Tools.Controls.TabOrderChangedEventArgs e)
{
    // Restrict the Tab item order changing
    e.Cancel = true;

    var dragged_Item = e.TargetItem;
    var oldIndex = e.OldIndex;
    var newIndex = e.NewIndex;
}

{% endhighlight %}
{% endtabs %}

![WPF Docking Restrict Tabbed Window Reordering](TabbedWindow_images/wpf-docking-restrict-tabbed-window-reordering.png)

N> [View Sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-docking-manager-wpf-examples/tree/master/Samples/TabbedWindowOrdering)
