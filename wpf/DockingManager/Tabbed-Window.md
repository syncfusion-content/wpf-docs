---
layout: post
title: Tabbed Window of Syncfusion's DockingManager control for WPF
description: Tabbed Window
platform: wpf
control: DockingManager
documentation: ug
---
# Tabbed Window

Child window can be arranged as Tabbed windows by setting TargetName and side value as `Tabbed` using the property `SideInDockedMode`.

![](TabbedWindow_images/TabbedWindow_img1.jpeg)


##  Tab alignments

The tabs of the Docked window are placed at the bottom, by default. To place the tabs of the docked window at different sides set the property `DockTabAlignment` with desired values such as Top, Bottom, Left and Right. 

* DockTabAlignment as `Bottom`

![](TabbedWindow_images/TabbedWindow_img2.jpeg)


* Setting DockTabAlignment as `Left`.


{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" DockTabAlignment="Left">

<ContentControl  syncfusion:DockingManager.Header="Item1" x:Name="Content1" />
	
<ContentControl syncfusion:DockingManager.Header="Item2" x:Name="Content2"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="Content1"/> 

</syncfusion:DockingManager>



{% endhighlight %}

{% endtabs %}


![](TabbedWindow_images/TabbedWindow_img3.jpeg)


* Setting DockTabAlignment as `Right`

{% tabs %}

{% highlight XAML %}
<syncfusion:DockingManager x:Name="DockingManager1" DockTabAlignment="Right">

<ContentControl syncfusion:DockingManager.Header="Item1"  x:Name="Content1"/>  

<ContentControl syncfusion:DockingManager.Header="Item2" x:Name="Content2"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="Content1"/>
				
</syncfusion:DockingManager>

{% endhighlight %}

{% endtabs %}


![](TabbedWindow_images/TabbedWindow_img4.jpeg)


* Setting DockTabAlignment as `Top`


{% tabs %}

{% highlight XAML %}

<syncfusion:DockingManager x:Name="DockingManager1" DockTabAlignment="Top">

<ContentControl  syncfusion:DockingManager.Header="Item1" x:Name="Content1"/> 

<ContentControl syncfusion:DockingManager.Header="Item2" x:Name="Content2"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="Content1"/>  

</syncfusion:DockingManager>



{% endhighlight %}

{% endtabs %}

![](TabbedWindow_images/TabbedWindow_img5.jpeg)


## Closing a Tabbed window

Tabbed window provides two different closing behaviors. They are CloseActive and CloseAll modes of `CloseTabs` property.

`CloseActive` – Used to close the active element of Tabbed window.

{% tabs %}

{% highlight XAML %}
<syncfusion:DockingManager x:Name="DockingManager1" CloseTabs="CloseActive">

<ContentControl syncfusion:DockingManager.Header="Item1" x:Name="Content1" />  

<ContentControl syncfusion:DockingManager.Header="Item2" x:Name="Content2"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="Content1"/>  

<ContentControl syncfusion:DockingManager.Header="Item3" x:Name="Content3"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="Content1"/>                         

</syncfusion:DockingManager>



{% endhighlight %}

{% endtabs %}

 `CloseAll` – Used to close all the Tabbed window.

{% tabs %}

{% highlight XAML %}
<syncfusion:DockingManager x:Name="DockingManager1" CloseTabs="CloseAll">

<ContentControl syncfusion:DockingManager.Header="Item1" x:Name="Content1"/>  

<ContentControl syncfusion:DockingManager.Header="Item2" x:Name="Content2"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="Content1"/>  

<ContentControl syncfusion:DockingManager.Header="Item3" x:Name="Content3"
                syncfusion:DockingManager.SideInDockedMode="Tabbed"
				syncfusion:DockingManager.TargetNameInDockedMode="Content1"/>                         

</syncfusion:DockingManager>


{% endhighlight %}

{% endtabs %}
