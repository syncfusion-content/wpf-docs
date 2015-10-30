---
layout: post
title: Linked Manager | DockingManager | WPF | Syncfusion
description: Linked Manager 
platform: wpf
control: DockingManager
documentation: ug
---
## Linked Manager 

The windows from one DockingManager cannot be dragged and dropped to another, by default. Linked Manager allows you to drag and drop the windows from one DockingManager to another by the TargetDockingManager list.

### Getting Started

{% highlight xml %}

[MainWindow.XAML]

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True">

<ContentControl syncfusion:DockingManager.State="Document"

syncfusion:DockingManager.Header="Window1"></ContentControl>

<ContentControl syncfusion:DockingManager.State="Dock"

syncfusion:DockingManager.Header="Window2"></ContentControl>

<ContentControl syncfusion:DockingManager.State="AutoHidden"

syncfusion:DockingManager.Header="Window3"></ContentControl>

</syncfusion:DockingManager>





{% endhighlight %}

{% highlight xml %}

[MainWindow1.XAML]

<syncfusion:DockingManager x:Name="DockingManager2" UseDocumentContainer="True">

<ContentControl syncfusion:DockingManager.State="Dock"

syncfusion:DockingManager.Header="Window1"></ContentControl>

<ContentControl syncfusion:DockingManager.State="Dock"

syncfusion:DockingManager.Header="Window2"></ContentControl>

<ContentControl syncfusion:DockingManager.State="AutoHidden"

syncfusion:DockingManager.Header="Window3"></ContentControl>

</syncfusion:DockingManager>                   





{% endhighlight %}

{% highlight c# %}

[MainWindow.cs]

public partial class MainWindow : Window

{

static int count = 0;



public MainWindow()

{

InitializeComponent();

count++;      

MainWindow1 MainWindow = new MainWindow1();

MainWindow.Title = "Docking Manager " + count;

MainWindow.Show();

this.DockingManager1.AddToTargetManagersList(MainWindow.DockingManager2);

MainWindow.DockingManager2.AddToTargetManagersList(this.DockingManager1);

}





{% endhighlight %}

![](LinkedManager_images/LinkedManager_img1.jpeg)


#### Adding TargetManager list of DockingManager

To add TargetManager list in the DockingManager call `AddToTargetManagersList()` method of the DockingManager with the valid DockingManager instance as argument.

When only one DockingManager has TargetManagerList, the window drop to TargetManager cannot drag back to Owner DockingManger. 

For instance DockingManager1 and DockingManager2 are the DockingManager instance and the DockingManager2 is added to TargetManagerList of DockingManager1, but the DockingManager2 is not aware of its TargetManager.

Here, the windows from DockingManager1 are only allowed to be dragged and dropped in DockingManager2, 

{% highlight c# %}

this.DockingManager1.AddToTargetManagersList(MainWindow.DockingManager2);





{% endhighlight %}

To drag and drop the window from DockingManager2 to DockingManager1, DockingManager1 must be added to TargetManagerList of DockingManager2.

{% highlight c# %}

this.DockingManager1.AddToTargetManagersList(MainWindow.DockingManager2);

MainWindow.DockingManager2.AddToTargetManagersList(this.DockingManager1);





{% endhighlight %}

#### Removing Target Manager list

To remove DockingManager from the TargetManagerList, call `RemoveFromTargetManagerList()` of DockingManager with the valid DockingManager instance argument. For instance, to remove the DockingManager1 from the TargetManagersList of DockingManager2, you can use the following code example:

{% highlight c# %}

MainWindow.DockingManager2.RemoveFromTargetManagersList(this.DockingManager1);





{% endhighlight %}

### Nested Docking

DockingManager provides the `NestedDockingManager` support, that allows you to add DockingManager as a child window to another DockingManager. 

### Getting Started

In Nested DockingManager, the whole DockingManager can be dragged and dropped inside the Parent DockingManager and DockWindows inside the DockingManager cannot be dragged and dropped on the owner DockingManager.

#### Adding DockingManager as Child in DockingManager

{% highlight xml %}

<syncfusion:DockingManager x:Name="DockingManager1" UseDocumentContainer="True" syncfusion:DockingManager.Header="Dock1"   >

<ContentControl x:Name="Content1" syncfusion:DockingManager.Header="Dock1"/>

<syncfusion:DockingManager x:Name="DockingManager2" UseDocumentContainer="True" SideInDockedMode="Left" syncfusion:DockingManager.Header="Dock2"  >

<ContentControl syncfusion:DockingManager.Header="Dock2"                               syncfusion:DockingManager.DesiredWidthInDockedMode="600"></ContentControl>

</syncfusion:DockingManager>

<syncfusion:DockingManager x:Name="DockingManager3" UseDocumentContainer="True" SideInDockedMode="Bottom"  syncfusion:DockingManager.Header="Dock3">

<ContentControl syncfusion:DockingManager.Header="Dock3" 

syncfusion:DockingManager.DesiredWidthInDockedMode="600"/>

</syncfusion:DockingManager>

</syncfusion:DockingManager>





{% endhighlight %}

![](LinkedManager_images/LinkedManager_img2.jpeg)


