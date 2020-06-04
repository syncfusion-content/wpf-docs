---
layout: post
title: Getting Started | TileView | wpf | Syncfusion
description: This section gives detailed information of Getting Started information ofTileView control in application.
platform: wpf
control: TileView Control
documentation: ug
---

# Getting Started of TileViewControl

This section describes how to design a [TileViewControl](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl_members.html) control in a WPF application and overview of its basic functionalities.

## Structure of the TileViewControl

![Structure of TileView control](Getting-Started_images/Getting-Started_img1.jpg)

## Creating simple application with TileViewControl

The [TileViewControl](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl_members.html)  can be added to an application using Visual Studio and Blend.

You can create the WPF application with [TileViewControl](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl_members.html) control as follows:

1. [Creating project](#creating-the-project)
2. [Adding control via designer](#adding-control-via-designer)
3. [Adding control manually in XAML](#adding-control-manually-in-XAML)
3. [Adding control manually in C#](#adding-control-manually-in-code)

## Creating the project

The steps to create a [TileViewControl](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl_members.html) control using Visual Studio in C# are as follows:

1.	Open Visual Studio.

2.	On the File menu, select New -> Project. This opens the New Project Dialog box.

## Adding control via designer

[TileViewControl](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl_members.html)  can be added to the application by dragging it from the toolbox and dropping it in a designer view. The following required assembly **Syncfusion.Shared.WPF** references will be added automatically.

### Through Visual Studio

The following are the steps to create the [TileViewControl](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl_members.html) using Visual Studio.

1. Drag TileViewControl from the Toolbox and drop it in the Designer area. It will generate the TileViewControl. 

     ![TileViewControl by VS designer](Getting-Started_images/Getting-Started_img2.png)

2. To add items to the [TileViewControl](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl_members.html) using the Collection Editor, select the TileViewControl and look at its properties.
3. Click the button in the Items property. This will open the Collection Editor.

     ![Collection Editor of TileViewControl](Getting-Started_images/Getting-Started_img3.png)

4.  Using the Collection Editor, add the GroupBarItems and configure their properties.

### Through Expression Blend

The [TileViewControl](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl_members.html) can also be created and configured using Expression Blend. The following are the steps to do so.

1. Create a WPF project in Expression Blend and reference the following assemblies.
   1. Syncfusion.Shared.Wpf
   2. Syncfusion.Core
2. Search for [TileViewControl](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl_members.html) in the Toolbox.

     ![TileViewControl by Blend ToolBox](Getting-Started_images/Getting-Started_img4.png)

3. Drag the TileViewControl to the designer.

     ![TileViewControl by Blend Designer](Getting-Started_images/Getting-Started_img5.png)

4. To add items to the [TileViewControl](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl_members.html) using the Collection Editor, select TileViewControl and go to Properties.
5. Click Items (Collection) under Common Properties.

     ![CollectionEditor in Blend](Getting-Started_images/Getting-Started_img6.png)

6. Once the Collection Editor window opens, click Add another item. The Select Object window will open. 
7. Select [TileViewItem](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem.html) by typing _TileViewItem_ in the search box, and then click OK.

     ![Adding TileViewItem](Getting-Started_images/Getting-Started_img7.png)

8. Configure the [TileViewItem](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem.html) using the properties in the Collection Editor.

N> You can customize the appearance of the [TileViewControl](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl_members.html) and its Item using the template-editing feature available in the Expression Blend.

## Adding control manually in XAML

The [TileViewControl](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl_members.html) can also be created through XAML. 

{% tabs %}

{% highlight xaml %}

<Window
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
xmlns:local="clr-namespace:WPF_ForDocumentation"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
x:Class="WPF_ForDocumentation.MainWindow"
mc:Ignorable="d"
Name="mainWindow"
Title="MainWindow" Height="450" Width="700" >
<Grid>
<syncfusion:TileViewControl Name="tileViewControl1" >
     <syncfusion:TileViewItem Header="Item 1" />
     <syncfusion:TileViewItem Header="Item 2" />
     <syncfusion:TileViewItem Header="Item 3" />
     <syncfusion:TileViewItem Header="Item 4" />
</syncfusion:TileViewControl>
</Grid>
</Window>
{% endhighlight %}

{% endtabs %}

## Adding control manually in C#

To create the [TileViewControl](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl_members.html) through C#, include the following namespace to the directives list.

{% tabs %}

{% highlight c# %}

using Syncfusion.Windows.Shared;

{% endhighlight %}

{% highlight VB %}

Imports Syncfusion.Windows.Shared

{% endhighlight %}

{% endtabs %}

Create an instance for [TileViewControl](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl_members.html) and add the TileViewItems in it.

{% tabs %}

{% highlight c# %}

TileViewControl tvControl = new TileViewControl();
TileViewItem tvitem1 = new TileViewItem() { Header = "Item 1" };
TileViewItem tvitem2 = new TileViewItem() { Header = "Item 2" };
TileViewItem tvitem3 = new TileViewItem() { Header = "Item 3" };
TileViewItem tvitem4 = new TileViewItem() { Header = "Item 4" };

tvControl.Items.Add(tvitem1);
tvControl.Items.Add(tvitem2);
tvControl.Items.Add(tvitem3);
tvControl.Items.Add(tvitem4);

{% endhighlight %}

{% highlight VB %}

Dim tvControl As TileViewControl = New TileViewControl
Dim tvitem1 As TileViewItem = New TileViewItem
Dim tvitem2 As TileViewItem = New TileViewItem
Dim tvitem3 As TileViewItem = New TileViewItem
Dim tvitem4 As TileViewItem = New TileViewItem

tvControl.Items.Add(tvitem1)
tvControl.Items.Add(tvitem2)
tvControl.Items.Add(tvitem3)
tvControl.Items.Add(tvitem4)

{% endhighlight %}

{% endtabs %}

![TileViewControl added by codebehind](Getting-Started_images/Getting-Started_img8.png)

### Selection using IsSelected in TileViewControl 

You can set the TileViewItem to be selected when [TileViewControl](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl_members.html) is loaded by using [IsSelected](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem~IsSelected.html) property in respective [TileViewItem](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem.html).

{% tabs %}

{% highlight xaml %}

<syncfusion:TileViewControl x:Name="TileView" Height="600" Width="800">
     <syncfusion:TileViewItem x:Name="Tile1" Header="TileViewItem 1" />
     <syncfusion:TileViewItem x:Name="Tile2" Header="TileViewItem 2" IsSelected="True" /> 
</syncfusion:TileViewControl>

{% endhighlight %}

{% highlight c# %}

TileViewControl tvControl = new TileViewControl();
TileViewItem tvitem1 = new TileViewItem() { Header = "Item 1" };
TileViewItem tvitem2 = new TileViewItem() { Header = "Item 2" };

tvControl.Items.Add(tvitem1);
tvControl.Items.Add(tvitem2);
tvitem1.IsSelected = true;

{% endhighlight %}

{% highlight VB %}

Dim tvControl As TileViewControl = New TileViewControl
Dim tvitem1 As TileViewItem = New TileViewItem
Dim tvitem2 As TileViewItem = New TileViewItem

tvControl.Items.Add(tvitem1)
tvControl.Items.Add(tvitem2)

tvitem1.IsSelected = true

{% endhighlight %}

{% endtabs %}

## Maximizing TileViewItem in TileViewControl

You can maximize the [TileViewItem](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewItem.html) by clicking on its header after enabling the [ClickHeaderToMaximize](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl~ClickHeaderToMaximize.html) property in [TileViewControl](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.Shared.Wpf~Syncfusion.Windows.Shared.TileViewControl_members.html).The TileViewItem’s state will remain same if you click on the header of the TileViewItem which is in maximized state

{% tabs %}

{% highlight xaml %}
<syncfusion:TileViewControl x:Name="TileView" Height="600" Width="800" ClickHeaderToMaximize ="True" >
     <syncfusion:TileViewItem x:Name="Tile1" Header="TileViewItem 1" />
     <syncfusion:TileViewItem x:Name="Tile2" Header="TileViewItem 2" />
</syncfusion:TileViewControl>

{% endhighlight %}
{% highlight c# %}

TileViewControl tvControl = new TileViewControl();
TileViewItem tvitem1 = new TileViewItem() { Header = "Item 1" };
TileViewItem tvitem2 = new TileViewItem() { Header = "Item 2" };

tvControl.Items.Add(tvitem1);
tvControl.Items.Add(tvitem2);
tvControl.ClickHeaderToMaximize = true;      

{% endhighlight %}

{% endtabs %}
