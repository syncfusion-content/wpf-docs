---
layout: post
title: ToolBarAdv State in WPF ToolBar control | Syncfusion
description: Learn here all about ToolBarAdv State support in Syncfusion WPF ToolBar (ToolBarAdv) control and more.
platform: wpf
control: ToolBarAdv
documentation: ug
---
# ToolBarAdv State in WPF ToolBar (ToolBarAdv)

ToolBarAdv provides different states such as Docking, Floating or Hidden. It can be change using the property `ToolBarState` of the ToolBarManager. 

{% tabs %}

{% highlight XAML %}

<syncfusion:ToolBarManager x:Name="toolBarManager" >

<syncfusion:ToolBarManager.TopToolBarTray>

<syncfusion:ToolBarTrayAdv >

<syncfusion:ToolBarAdv ToolBarName="Standard" Band="0">

<Button syncfusion:ToolBarAdv.Label="New Document"
        syncfusion:ToolBarAdv.Icon="Images/NewDocumentHS.png">

<Image Source="Images/NewDocumentHS.png" Width="16" Height="16"/>

</Button>

<Button syncfusion:ToolBarAdv.Label="Open Document"
        syncfusion:ToolBarAdv.Icon="Images/openHS.png">

<Image Source="Images/openHS.png" Width="16" Height="16"/>

</Button>

<syncfusion:ToolBarAdv Band="1" ToolBarName="Extras"
            syncfusion:ToolBarManager.ToolBarState="Floating"
			FloatingBarLocation="500,300">

<Button syncfusion:ToolBarAdv.Label="Insert Picture"
        syncfusion:ToolBarAdv.Icon="Images/InsertPictureHS.png">

<Image Source="Images/InsertPictureHS.png" Width="16" Height="16"/>

</Button>

<Button syncfusion:ToolBarAdv.Label="Insert Hyperlink"
        syncfusion:ToolBarAdv.Icon="Images/InsertHyperlinkHS.png">

<Image Source="Images/InsertHyperlinkHS.png" Width="16" Height="16"/>

</Button>

<Button syncfusion:ToolBarAdv.Label="Insert Table"
        syncfusion:ToolBarAdv.Icon="Images/TableHS.png">

<Image Source="Images/TableHS.png" Width="16" Height="16"/>

</Button>

</syncfusion:ToolBarAdv>

</syncfusion:ToolBarAdv>

</syncfusion:ToolBarTrayAdv>

</syncfusion:ToolBarManager.TopToolBarTray>

<Grid >

<Grid.RowDefinitions>

<RowDefinition Height="*"/>

<RowDefinition Height="Auto"/>

</Grid.RowDefinitions>

<ScrollViewer >

<Grid Margin="20">

<Border CornerRadius="2" Background="Black"
        Opacity="0.3" Width="600" Height="700">

<Border.Effect>

<BlurEffect Radius="15"/>

</Border.Effect>

</Border>

<RichTextBox Width="600" Height="700" Padding="20"></RichTextBox>

</Grid>

</ScrollViewer>

</Grid>

</syncfusion:ToolBarManager>



{% endhighlight %}

{% highlight C# %}


ToolBarAdv toolBar = new ToolBarAdv(); 

toolBar.FloatingBarLocation = new Point(500, 300); 

ToolBarManager.SetToolBarState(toolBar, ToolBarState.Floating);

Grid1.Children.Add(toolBar);



{% endhighlight %}

{% endtabs %}

![ToolBarAdv-state-img1](ToolBarAdv-state-images/ToolBarAdv-state-img1.jpeg)


ToolBarAdv can be floated only when it is hosted in ToolBarManager.

## Specifying location for floating ToolBarAdv.

The location of the floating ToolBarAdv can be changed using the `FloatingBarLocation` property. The following code illustrates this

{% tabs %}

{% highlight XAML %}

<syncfusion:ToolBarAdv FloatingBarLocation="50,50"/>



{% endhighlight %}

{% highlight C# %}


ToolBarAdv toolBar = new ToolBarAdv();

toolBar.FloatingBarLocation = new Point(50, 50);



{% endhighlight %}

{% endtabs%}

## Restrict Docking of ToolBarAdv for a specific position

By default, the ToolBarAdv can be docked to any position. To restrict docking of ToolBarAdv to particular position, the following properties can be used. Each will restrict docking at corresponding positions in ToolBarManager.

* CanDockAtLeft—restricts docking at the left.
* CanDockAtTop—restricts docking at the top.
* CanDockAtRight—restricts docking at the right.
* CanDockAtBottom—restricts docking at the bottom.

Following code restricts docking at the top:

{% tabs %}

{% highlight XAML %}

<syncfusion:ToolBarManager CanDockAtTop="False"/>



{% endhighlight %}

{% highlight C# %}

ToolBarManager toolBarManager = new ToolBarManager(); 

toolBarManager.CanDockAtTop = false;



{% endhighlight %}

{% endtabs%}

## Implementation of toolbar state changed event to detect when the state of ToolBarAdv changes.

Introducing a state changed event in the ToolbarAdv control that notifies users whenever the toolbar's state changes, including transitions between Docked, Floating, and Hidden states. 

{% tabs %}

{% highlight XAML %}

<syncfusion:ToolBarManager x:Name="toolBarManager" Grid.Row="0" Height="83">

<syncfusion:ToolBarManager.TopToolBarTray>

<syncfusion:ToolBarTrayAdv VerticalAlignment="Top">

<syncfusion:ToolBarAdv x:Name="toolbar" ToolBarStateChanged="ToolBarAdv_ToolBarStateChanged1" Height="40" EnableAddRemoveButton="True">
               
<Button syncfusion:ToolBarAdv.Label="Open Folder" Height="40" Width="40" ToolTip="Open Folder" Margin="5,0,5,0">

<Image Source="C:\OpenFolder.png" Stretch="Uniform"/>

</Button>

<Button syncfusion:ToolBarAdv.Label="Save" Height="40" Width="40" ToolTip="Save" Margin="5,0,5,0">

<Image Source="C:\Save.JPG" Stretch="Uniform"/>

</Button>

<Button syncfusion:ToolBarAdv.Label="Cut" Height="40" Width="40" ToolTip="Cut" Margin="5,0,5,0">

<Image Source="C:\Cut.jpg" Stretch="Fill"/>

</Button>

<Button syncfusion:ToolBarAdv.Label="Copy" Height="40" Width="40" ToolTip="Copy" Margin="5,0,5,0">

<Image Source="C:\Copy.png" Stretch="Uniform"/>

</Button>

<Button syncfusion:ToolBarAdv.Label="Paste" Height="40" Width="40" ToolTip="Paste" Margin="5,0,5,0">

<Image Source="C:\Paste.jpg" Stretch="Uniform"/>

</Button>

</syncfusion:ToolBarAdv>

</syncfusion:ToolBarTrayAdv>

</syncfusion:ToolBarManager.TopToolBarTray>

</syncfusion:ToolBarManager>



{% endhighlight %}

{% highlight C# %}

ToolBarAdv toolbar = new ToolBarAdv();

toolbar.ToolBarStateChanged += ToolBarAdv_ToolBarStateChanged;



{% endhighlight %}

{% endtabs%}

