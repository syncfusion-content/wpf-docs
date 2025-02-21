---
layout: post
title: Getting Started with WPF Ribbon control | Syncfusion®
description: Learn here about getting started with Syncfusion® Essential Studio® WPF Ribbon control, its elements and more.
platform: WPF
control: Ribbon
documentation: ug
---
# Getting Started with WPF Ribbon

This section explains how to implement a similar UI as Microsoft Outlook using Ribbon. 

## Add ribbon

There are several ways to add Syncfusion<sup>®</sup> control in to Visual Studio WPF project, the following steps will helps to add a Ribbon control through XAML Code.

* Create a WPF project in Visual Studio and refer the following assemblies.

  1. Syncfusion.Tools.Wpf
  2. Syncfusion.Shared.Wpf
  
* Include an XML namespace for the above assemblies to the Main window.

{% capture codesnippet1 %}
{% tabs %}

{% highlight XAML %}

<Window
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="RibbonControl.MainWindow">       
</Window>

{% endhighlight %}

{% endtabs %}
{% endcapture %}
{{ codesnippet1 | UnOrderList_Indent_Level_1 }}

* Change the Window as `RibbonWindow`.

{% capture codesnippet2 %}
{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="RibbonControl.MainWindow">
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}
{% endcapture %}
{{ codesnippet2 | UnOrderList_Indent_Level_1 }}

* Add following namespace and inherit MainWindow from `RibbonWindow` in code behind.

{% capture codesnippet3 %}
{% tabs %}

{% highlight C# %}

using Syncfusion.Windows.Tools.Controls;
public partial class MainWindow : RibbonWindow

{% endhighlight %}

{% highlight VB %}

Imports Syncfusion.Windows.Tools.Controls
Public class As partial

{% endhighlight %}

{% endtabs %}
{% endcapture %}
{{ codesnippet3 | UnOrderList_Indent_Level_1 }}

* Now, Add the Ribbon control with a required optimal name, using the included namespace in XAML.

{% capture codesnippet4 %}
{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf"    x:Class="RibbonControl.MainWindow">
<Grid>
<syncfusion:Ribbon x:Name="_ribbon"/>
</Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}
{% endcapture %}
{{ codesnippet4 | UnOrderList_Indent_Level_1 }}

## Set icon for RibbonWindow

* Icon of the RibbonWindow can be set using the property named `Office2010Icon`. Please refer to the below code.

{% capture codesnippet5 %}
{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
    x:Class="WPFRibbon.MainWindow"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:local="clr-namespace:WPFRibbon"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:sfSkinManager="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
    Title="MainWindow"
    Office2010Icon="Assets/New Microsoft.png"
    sfSkinManager:SfSkinManager.VisualStyle="Office2016White"
    mc:Ignorable="d">
<Grid>
<syncfusion:Ribbon x:Name="_ribbon"/>
</Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}
{% endcapture %}
{{ codesnippet5 | UnOrderList_Indent_Level_1 }}

![Set Icon in WPF Ribbon](getting-started_images/wpf-ribbon-control.jpg)

## Set visual styles

Ribbon supports various visual styles by using the `SfSkinManager`. To apply Visual Studio style on the current layout, refer to the following steps.

* Refer the following assemblies with the project

    1. Syncfusion.SfSkinManager.Wpf
    2. Syncfusion.Themes.Office2013White.Wpf

* Include an XML namespace for the SfSkinManager assembly to the MainWindow.

{% capture codesnippet6 %}
{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="RibbonControl.MainWindow"
xmlns:syncfusionskin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF" >
<Grid>
<syncfusion:Ribbon x:Name="_ribbon"/>
</Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}
{% endcapture %}
{{ codesnippet6 | UnOrderList_Indent_Level_1 }}

* Now apply the value as `Office2013White` to the `VisualStyle` property of the SfSkinManager for the RibbonWindow.

{% capture codesnippet7 %}
{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="RibbonControl.MainWindow"
xmlns:syncfusionskin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
syncfusionskin:SfSkinManager.VisualStyle="Office2013White" >
<Grid>
<syncfusion:Ribbon x:Name="_ribbon"/>
</Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}
{% endcapture %}
{{ codesnippet7 | UnOrderList_Indent_Level_1 }}

![WPF Ribbon with Office2013White Style](getting-started_images/wpf-ribbon-style.jpg)

## Add RibbonTab

Ribbon control accept `RibbonTab` as children, Here four `RibbonTab` are added and that can hold `RibbonItems` with `RibbonBar`.

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="RibbonControl.MainWindow"
xmlns:syncfusionskin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
syncfusionskin:SfSkinManager.VisualStyle="Office2013White" >
<Grid>   
<syncfusion:Ribbon x:Name="_ribbon" VerticalAlignment="Top">
<syncfusion:RibbonTab Caption="HOME"  IsChecked="True"/>
<syncfusion:RibbonTab Caption="SEND/RCEIVE"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="FOLDER"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="VIEW"  IsChecked="False"/>
</syncfusion:Ribbon>
</Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}

![WPF Ribbon with RibbonTab](getting-started_images/wpf-ribbon-with-ribbontab.jpg)

## Add RibbonBar

RibbonTab accepts `RibbonBar` as children, here five `RibbonBar` Controls are added inside "HOME" RibbonTab. To set header for RibbonBar, use its `Header` property.

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="RibbonControl.MainWindow"
xmlns:syncfusionskin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
syncfusionskin:SfSkinManager.VisualStyle="Office2013White" >
<Grid>   
<syncfusion:Ribbon x:Name="_ribbon" VerticalAlignment="Top">
<syncfusion:RibbonTab Caption="HOME"  IsChecked="True">
<syncfusion:RibbonBar Name="New" Width="90"  Header="New"/>
<syncfusion:RibbonBar Name="Delete" Width="150"  Header="Delete"/>
<syncfusion:RibbonBar Name="Respond" Width="90" Header="Respond"/>
<syncfusion:RibbonBar Name="Quicksteps" Width="90" Header="Quick Steps"/>
<syncfusion:RibbonBar Name="Find" Width="90" Header="Find"/>
</syncfusion:RibbonTab>
<syncfusion:RibbonTab Caption="SEND/RCEIVE"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="FOLDER"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="VIEW"  IsChecked="False"/>
</syncfusion:Ribbon>
</Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}

![WPF Ribbon with RibbonBars](getting-started_images/wpf-ribbon-with-ribbonbar.jpg)

## Add RibbonButton

`RibbonButton` provides functionalities like normal Button. It can place inside the RibbonBar. Here, "New" RibbonBar holds a `RibbonButton` with a caption as "New Email" using its `Label` property.It also provides `SizeForm` property for different sizes. 

If the value of `SizeForm` is large,then image of 16 * 16 size has been expanded to 32 * 32 automatically. Similarly,image of 32 * 32 has been compressed to     16 * 16 if `SizeForm` is ExtraSmall.    

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonBar Name="New" Width="90"  Header="New">                    
<syncfusion:RibbonButton SizeForm="Large" Label="New Email"/>
</syncfusion:RibbonBar>

{% endhighlight %}

{% endtabs %}

Also add several other Ribbon Button as per the requirement  

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="RibbonControl.MainWindow"
xmlns:syncfusionskin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
syncfusionskin:SfSkinManager.VisualStyle="Office2013White" >
<Grid>   
<syncfusion:Ribbon x:Name="_ribbon" VerticalAlignment="Top">
<syncfusion:RibbonTab Caption="HOME"  IsChecked="True">
<syncfusion:RibbonBar Name="New" Width="90"  Header="New">
<syncfusion:RibbonButton SizeForm="Large" Label="New Email"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Delete" Width="130"  Header="Delete">
<syncfusion:RibbonButton Label="Ignore"/>
<syncfusion:RibbonButton Label="Delete" SizeForm="Large"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Respond" Width="200" Header="Respond">
<syncfusion:RibbonButton Label="Reply" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Reply All" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Forward" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Meeting"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Quicksteps" Width="90" Header="Quick Steps"/>
<syncfusion:RibbonBar Name="Find" Width="90" Header="Find"/>
</syncfusion:RibbonTab>
<syncfusion:RibbonTab Caption="SEND/RCEIVE"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="FOLDER"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="VIEW"  IsChecked="False"/>
</syncfusion:Ribbon>
</Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}

![WPF Ribbon with RibbonButton](getting-started_images/wpf-ribbon-with-ribbonbutton.jpg)

N> Image of any size has been used for `RibbonButton` and also it supports image of all formats.

## Add DropDownButton

`DropDownButton` appears like normal button that contains a drop arrow. It displays some items, while click on it. It accepts `DropDownMenuItem` as its children.  Here, "New" RibbonBar holds a `DropDownButton` with a caption as "New Items" using its `Label` property also holding items like "E-mail Message", "Appointment", "Meeting", "Contact" and "Task". It also provides `SizeForm` property for different sizes.

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="RibbonControl.MainWindow"
xmlns:syncfusionskin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
syncfusionskin:SfSkinManager.VisualStyle="Office2013White" >
<Grid>   
<syncfusion:Ribbon x:Name="_ribbon" VerticalAlignment="Top">
<syncfusion:RibbonTab Caption="HOME"  IsChecked="True">
<syncfusion:RibbonBar Name="New" Width="90"  Header="New">
<syncfusion:RibbonButton SizeForm="Large" Label="New Email"/>
<syncfusion:DropDownButton SizeForm="Large" Label="New Items">
<syncfusion:DropDownMenuItem Header="E-mail Message"/>
<syncfusion:DropDownMenuItem Header="Appointment"/>
<syncfusion:DropDownMenuItem Header="Meeting"/>
<syncfusion:DropDownMenuItem Header="Contact"/>
<syncfusion:DropDownMenuItem Header="Task"/>
</syncfusion:DropDownButton>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Delete" Width="130"  Header="Delete">
<syncfusion:RibbonButton Label="Ignore"/>
<syncfusion:RibbonButton Label="Delete" SizeForm="Large"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Respond" Width="200" Header="Respond">
<syncfusion:RibbonButton Label="Reply" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Reply All" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Forward" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Meeting"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Quicksteps" Width="90" Header="Quick Steps"/>
<syncfusion:RibbonBar Name="Find" Width="90" Header="Find"/>
</syncfusion:RibbonTab>
<syncfusion:RibbonTab Caption="SEND/RCEIVE"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="FOLDER"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="VIEW"  IsChecked="False"/>
</syncfusion:Ribbon>
</Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}

![WPF Ribbon with DropDownButton](getting-started_images/wpf-ribbon-with-dropdownbutton.jpg)

## Add SplitButton

SplitButton also appears with a drop arrow. It displays some items while click on it. It accepts `DropDownMenuItem` as its children.  Here, "Delete" RibbonBar holds a `SplitButton` with a caption as "Clean Up" using its `Label` property also holding items like "Clean Up Folder", "Clean Up Conversation" and "Clean Up Folder/SubFolder". It also provides `SizeForm` property for different sizes.

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="RibbonControl.MainWindow"
xmlns:syncfusionskin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
syncfusionskin:SfSkinManager.VisualStyle="Office2013White" >
<Grid>
<syncfusion:Ribbon x:Name="_ribbon" VerticalAlignment="Top">
<syncfusion:RibbonTab Caption="HOME"  IsChecked="True">
<syncfusion:RibbonBar Name="New" Width="90"  Header="New">
<syncfusion:RibbonButton SizeForm="Large" Label="New Email"/>
<syncfusion:DropDownButton SizeForm="Large" Label="New Items">
<syncfusion:DropDownMenuItem Header="E-mail Message"/>
<syncfusion:DropDownMenuItem Header="Appointment"/>
<syncfusion:DropDownMenuItem Header="Meeting"/>
<syncfusion:DropDownMenuItem Header="Contact"/>
<syncfusion:DropDownMenuItem Header="Task"/>
</syncfusion:DropDownButton>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Delete" Width="130"  Header="Delete">
<syncfusion:RibbonButton Label="Ignore"/>
<syncfusion:SplitButton Label="Clean Up">
<syncfusion:DropDownMenuItem Header="Clean Up Folder"/>
<syncfusion:DropDownMenuItem Header="Clean Up Conversation"/>
<syncfusion:DropDownMenuItem Header="Clean Up Folder/SubFolder"/>
</syncfusion:SplitButton>
<syncfusion:SplitButton Label="Junk" Margin="0,0,12,0" Width="76"/>
<syncfusion:RibbonButton Label="Delete" SizeForm="Large"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Respond" Width="200" Header="Respond">
<syncfusion:RibbonButton Label="Reply" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Reply All" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Forward" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Meeting"/>
<syncfusion:SplitButton Label="IM" Margin="-2,0,6,0" Width="68"/>
<syncfusion:SplitButton Label="More" Margin="-2,0,6,0" Width="68"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Quicksteps" Width="90" Header="Quick Steps"/>
<syncfusion:RibbonBar Name="Find" Width="90" Header="Find"/>
</syncfusion:RibbonTab>
<syncfusion:RibbonTab Caption="SEND/RCEIVE"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="FOLDER"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="VIEW"  IsChecked="False"/>
</syncfusion:Ribbon>
</Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}

![WPF Ribbon with SplitButton](getting-started_images/wpf-ribbon-with-splitbutton.jpg)

## Add RibbonGallery

`RibbonGallery` displays items with good look and feel and it also used to classify the items as groups for easy navigation. Here, "QuickSteps" RibbonBar holds a `RibbonGallery` with `InRibbon` visual mode to place gallery items with in Ribbon. Also `ItemHeight`, `ItemWidth` properties are used to set height and width respectively.

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="RibbonControl.MainWindow"
xmlns:syncfusionskin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
syncfusionskin:SfSkinManager.VisualStyle="Office2013White" >
<Grid>   
<syncfusion:Ribbon x:Name="_ribbon" VerticalAlignment="Top">
<syncfusion:RibbonTab Caption="HOME"  IsChecked="True">
<syncfusion:RibbonBar Name="New" Width="90"  Header="New">
<syncfusion:RibbonButton SizeForm="Large" Label="New Email"/>
<syncfusion:DropDownButton SizeForm="Large" Label="New Items">
<syncfusion:DropDownMenuItem Header="E-mail Message"/>
<syncfusion:DropDownMenuItem Header="Appointment"/>
<syncfusion:DropDownMenuItem Header="Meeting"/>
<syncfusion:DropDownMenuItem Header="Contact"/>
<syncfusion:DropDownMenuItem Header="Task"/>
</syncfusion:DropDownButton>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Delete" Width="130"  Header="Delete">
<syncfusion:RibbonButton Label="Ignore"/>
<syncfusion:SplitButton Label="Clean Up">
<syncfusion:DropDownMenuItem Header="Clean Up Folder"/>
<syncfusion:DropDownMenuItem Header="Clean Up Conversation"/>
<syncfusion:DropDownMenuItem Header="Clean Up Folder/SubFolder"/>
</syncfusion:SplitButton>
<syncfusion:SplitButton Label="Junk" Margin="0,0,12,0" Width="76"/>
<syncfusion:RibbonButton Label="Delete" SizeForm="Large"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Respond" Width="200" Header="Respond">
<syncfusion:RibbonButton Label="Reply" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Reply All" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Forward" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Meeting"/>
<syncfusion:SplitButton Label="IM" Margin="-2,0,6,0" Width="68"/>
<syncfusion:SplitButton Label="More" Margin="-2,0,6,0" Width="68"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Width="170" Name="QuickSteps" Header="Quick Steps">
<syncfusion:RibbonGallery Width="160"    VisualMode="InRibbon" ItemHeight="20" ItemWidth="70">
<syncfusion:RibbonGalleryItem  Content="Move to?"/>
<syncfusion:RibbonGalleryItem  Content="Team Email"/>
<syncfusion:RibbonGalleryItem  Content="ReplyDelete"/>
<syncfusion:RibbonGalleryItem  Content="To Manager"/>
<syncfusion:RibbonGalleryItem  Content="Done"/>
<syncfusion:RibbonGalleryItem  Content="Create New"/>
</syncfusion:RibbonGallery>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Find" Width="90" Header="Find"/>
</syncfusion:RibbonTab>
<syncfusion:RibbonTab Caption="SEND/RCEIVE"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="FOLDER"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="VIEW"  IsChecked="False"/>
</syncfusion:Ribbon>
</Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}

![WPF Ribbon with Ribbon Gallery](getting-started_images/wpf-ribbon-with-ribbon-gallery.jpg)

## Add RibbonComboBox

`RibbonComboBox` is used to display the list of items.It accepts `ComboBoxItems` as its children.  Here, "Find" RibbonBar holds a `RibbonComboBox` with a caption as "Filter Email" using its `Label` property also holding items like "Person1@mail.com", "Person1@mail.com" and "Person1@mail.com".

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="RibbonControl.MainWindow"
xmlns:syncfusionskin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
syncfusionskin:SfSkinManager.VisualStyle="Office2013White" >
<Grid>   
<syncfusion:Ribbon x:Name="_ribbon" VerticalAlignment="Top">
<syncfusion:RibbonTab Caption="HOME"  IsChecked="True">
<syncfusion:RibbonBar Name="New" Width="90"  Header="New">
<syncfusion:RibbonButton SizeForm="Large" Label="New Email"/>
<syncfusion:DropDownButton SizeForm="Large" Label="New Items">
<syncfusion:DropDownMenuItem Header="E-mail Message"/>
<syncfusion:DropDownMenuItem Header="Appointment"/>
<syncfusion:DropDownMenuItem Header="Meeting"/>
<syncfusion:DropDownMenuItem Header="Contact"/>
<syncfusion:DropDownMenuItem Header="Task"/>
</syncfusion:DropDownButton>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Delete" Width="130"  Header="Delete">
<syncfusion:RibbonButton Label="Ignore"/>
<syncfusion:SplitButton Label="Clean Up">
<syncfusion:DropDownMenuItem Header="Clean Up Folder"/>
<syncfusion:DropDownMenuItem Header="Clean Up Conversation"/>
<syncfusion:DropDownMenuItem Header="Clean Up Folder/SubFolder"/>
</syncfusion:SplitButton>
<syncfusion:SplitButton Label="Junk" Margin="0,0,12,0" Width="76"/>
<syncfusion:RibbonButton Label="Delete" SizeForm="Large"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Respond" Width="200" Header="Respond">
<syncfusion:RibbonButton Label="Reply" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Reply All" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Forward" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Meeting"/>
<syncfusion:SplitButton Label="IM" Margin="-2,0,6,0" Width="68"/>
<syncfusion:SplitButton Label="More" Margin="-2,0,6,0" Width="68"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Width="170" Name="QuickSteps" Header="Quick Steps">
<syncfusion:RibbonGallery Width="160"    VisualMode="InRibbon" ItemHeight="20" ItemWidth="70">
<syncfusion:RibbonGalleryItem  Content="Move to?"/>
<syncfusion:RibbonGalleryItem  Content="Team Email"/>
<syncfusion:RibbonGalleryItem  Content="ReplyDelete"/>
<syncfusion:RibbonGalleryItem  Content="To Manager"/>
<syncfusion:RibbonGalleryItem  Content="Done"/>
<syncfusion:RibbonGalleryItem  Content="Create New"/>
</syncfusion:RibbonGallery>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Width="170" Header="Find" Name="Find"  >
<syncfusion:RibbonComboBox Label="Filter Email" Width="160">
<ComboBoxItem>Person1@mail.com</ComboBoxItem>
<ComboBoxItem>Person2@mail.com</ComboBoxItem>
<ComboBoxItem>Person3@mail.com</ComboBoxItem>
</syncfusion:RibbonComboBox>
</syncfusion:RibbonBar>
</syncfusion:RibbonTab>
<syncfusion:RibbonTab Caption="SEND/RCEIVE"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="FOLDER"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="VIEW"  IsChecked="False"/>
</syncfusion:Ribbon>
</Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}

## Add QAT

QuickAccessToolbar (QAT) is used to group the frequently used commands and access the commands easily without having to search for the command in the menu bar. Also it can be placed above or below the ribbon.

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="RibbonControl.MainWindow"
xmlns:syncfusionskin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
syncfusionskin:SfSkinManager.VisualStyle="Office2013White" >
<Grid>
<syncfusion:Ribbon x:Name="_ribbon" VerticalAlignment="Top">
<syncfusion:RibbonTab Caption="HOME"  IsChecked="True">
<syncfusion:RibbonBar Name="New" Width="90"  Header="New">
<syncfusion:RibbonButton SizeForm="Large" Label="New Email"/>
<syncfusion:DropDownButton SizeForm="Large" Label="New Items">
<syncfusion:DropDownMenuItem Header="E-mail Message"/>
<syncfusion:DropDownMenuItem Header="Appointment"/>
<syncfusion:DropDownMenuItem Header="Meeting"/>
<syncfusion:DropDownMenuItem Header="Contact"/>
<syncfusion:DropDownMenuItem Header="Task"/>
</syncfusion:DropDownButton>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Delete" Width="130"  Header="Delete">
<syncfusion:RibbonButton Label="Ignore"/>
<syncfusion:SplitButton Label="Clean Up">
<syncfusion:DropDownMenuItem Header="Clean Up Folder"/>
<syncfusion:DropDownMenuItem Header="Clean Up Conversation"/>
<syncfusion:DropDownMenuItem Header="Clean Up Folder/SubFolder"/>
</syncfusion:SplitButton>
<syncfusion:SplitButton Label="Junk" Margin="0,0,12,0" Width="76"/>
<syncfusion:RibbonButton Label="Delete" SizeForm="Large"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Respond" Width="200" Header="Respond">
<syncfusion:RibbonButton Label="Reply" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Reply All" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Forward" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Meeting"/>
<syncfusion:SplitButton Label="IM" Margin="-2,0,6,0" Width="68"/>
<syncfusion:SplitButton Label="More" Margin="-2,0,6,0" Width="68"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Width="170" Name="QuickSteps" Header="Quick Steps">
<syncfusion:RibbonGallery Width="160"    VisualMode="InRibbon" ItemHeight="20" ItemWidth="70">
<syncfusion:RibbonGalleryItem  Content="Move to?"/>
<syncfusion:RibbonGalleryItem  Content="Team Email"/>
<syncfusion:RibbonGalleryItem  Content="ReplyDelete"/>
<syncfusion:RibbonGalleryItem  Content="To Manager"/>
<syncfusion:RibbonGalleryItem  Content="Done"/>
<syncfusion:RibbonGalleryItem  Content="Create New"/>
</syncfusion:RibbonGallery>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Width="170" Header="Find" Name="Find"  >
<syncfusion:RibbonComboBox Label="Filter Email" Width="160">
<ComboBoxItem>Person1@mail.com</ComboBoxItem>
<ComboBoxItem>Person2@mail.com</ComboBoxItem>
<ComboBoxItem>Person3@mail.com</ComboBoxItem>
</syncfusion:RibbonComboBox>
</syncfusion:RibbonBar>
</syncfusion:RibbonTab>
<syncfusion:RibbonTab Caption="SEND/RCEIVE"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="FOLDER"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="VIEW"  IsChecked="False"/>
<syncfusion:Ribbon.QuickAccessToolBar>
<syncfusion:QuickAccessToolBar/>
</syncfusion:Ribbon.QuickAccessToolBar>
</syncfusion:Ribbon>
</Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}

![WPF Ribbon displays Quick Access ToolBar](getting-started_images/wpf-ribbon-quick-access-toolbar.jpg)


### Add items to Quick Access toolbar	

`QATMenuItems` property of QuickAccessToolbar used to add items to Dropdown menu of QAT. 

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="RibbonControl.MainWindow"
xmlns:syncfusionskin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
syncfusionskin:SfSkinManager.VisualStyle="Office2013White" >
<Grid>
<syncfusion:Ribbon x:Name="_ribbon" VerticalAlignment="Top">
<syncfusion:RibbonTab Caption="HOME"  IsChecked="True">
<syncfusion:RibbonBar Name="New" Width="90"  Header="New">
<syncfusion:RibbonButton SizeForm="Large" Label="New Email"/>
<syncfusion:DropDownButton SizeForm="Large" Label="New Items">
<syncfusion:DropDownMenuItem Header="E-mail Message"/>
<syncfusion:DropDownMenuItem Header="Appointment"/>
<syncfusion:DropDownMenuItem Header="Meeting"/>
<syncfusion:DropDownMenuItem Header="Contact"/>
<syncfusion:DropDownMenuItem Header="Task"/>
</syncfusion:DropDownButton>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Delete" Width="130"  Header="Delete">
<syncfusion:RibbonButton Label="Ignore"/>
<syncfusion:SplitButton Label="Clean Up">
<syncfusion:DropDownMenuItem Header="Clean Up Folder"/>
<syncfusion:DropDownMenuItem Header="Clean Up Conversation"/>
<syncfusion:DropDownMenuItem Header="Clean Up Folder/SubFolder"/>
</syncfusion:SplitButton>
<syncfusion:SplitButton Label="Junk" Margin="0,0,12,0" Width="76"/>
<syncfusion:RibbonButton Label="Delete" SizeForm="Large"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Respond" Width="200" Header="Respond">
<syncfusion:RibbonButton Label="Reply" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Reply All" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Forward" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Meeting"/>
<syncfusion:SplitButton Label="IM" Margin="-2,0,6,0" Width="68"/>
<syncfusion:SplitButton Label="More" Margin="-2,0,6,0" Width="68"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Width="170" Name="QuickSteps" Header="Quick Steps">
<syncfusion:RibbonGallery Width="160"    VisualMode="InRibbon" ItemHeight="20" ItemWidth="70">
<syncfusion:RibbonGalleryItem  Content="Move to?"/>
<syncfusion:RibbonGalleryItem  Content="Team Email"/>
<syncfusion:RibbonGalleryItem  Content="ReplyDelete"/>
<syncfusion:RibbonGalleryItem  Content="To Manager"/>
<syncfusion:RibbonGalleryItem  Content="Done"/>
<syncfusion:RibbonGalleryItem  Content="Create New"/>
</syncfusion:RibbonGallery>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Width="170" Header="Find" Name="Find"  >
<syncfusion:RibbonComboBox Label="Filter Email" Width="160">
<ComboBoxItem>Person1@mail.com</ComboBoxItem>
<ComboBoxItem>Person2@mail.com</ComboBoxItem>
<ComboBoxItem>Person3@mail.com</ComboBoxItem>
</syncfusion:RibbonComboBox>
</syncfusion:RibbonBar>
</syncfusion:RibbonTab>
<syncfusion:RibbonTab Caption="SEND/RCEIVE"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="FOLDER"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="VIEW"  IsChecked="False"/>
<syncfusion:Ribbon.QuickAccessToolBar>
<syncfusion:QuickAccessToolBar>
<syncfusion:RibbonButton SizeForm="ExtraSmall"/>
<syncfusion:RibbonButton SizeForm="ExtraSmall"/>
<syncfusion:QuickAccessToolBar.QATMenuItems>
<syncfusion:RibbonButton Label="Send" />
<syncfusion:RibbonButton Label="Forward" />
<syncfusion:RibbonButton Label="ReplyAll" />
<syncfusion:RibbonButton Label="Delete" />
<syncfusion:RibbonButton Label="Print" />
</syncfusion:QuickAccessToolBar.QATMenuItems>
</syncfusion:QuickAccessToolBar>
</syncfusion:Ribbon.QuickAccessToolBar>
</syncfusion:Ribbon>
</Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}

![WPF Ribbon displays Items in Quick Access ToolBar](getting-started_images/wpf-ribbon-quick-access-toolbar-items.jpg)

## Add BackStage

BackStage can be added by using `BackStage` property of Ribbon. To show the BackStage by, click the `FILE` Menu in Ribbon like in Microsoft Outlook. 

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="RibbonControl.MainWindow"
xmlns:syncfusionskin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
syncfusionskin:SfSkinManager.VisualStyle="Office2013White" >
<Grid>
<syncfusion:Ribbon x:Name="_ribbon" VerticalAlignment="Top">
<syncfusion:RibbonTab Caption="HOME"  IsChecked="True">
<syncfusion:RibbonBar Name="New" Width="90"  Header="New">
<syncfusion:RibbonButton SizeForm="Large" Label="New Email"/>
<syncfusion:DropDownButton SizeForm="Large" Label="New Items">
<syncfusion:DropDownMenuItem Header="E-mail Message"/>
<syncfusion:DropDownMenuItem Header="Appointment"/>
<syncfusion:DropDownMenuItem Header="Meeting"/>
<syncfusion:DropDownMenuItem Header="Contact"/>
<syncfusion:DropDownMenuItem Header="Task"/>
</syncfusion:DropDownButton>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Delete" Width="130"  Header="Delete">
<syncfusion:RibbonButton Label="Ignore"/>
<syncfusion:SplitButton Label="Clean Up">
<syncfusion:DropDownMenuItem Header="Clean Up Folder"/>
<syncfusion:DropDownMenuItem Header="Clean Up Conversation"/>
<syncfusion:DropDownMenuItem Header="Clean Up Folder/SubFolder"/>
</syncfusion:SplitButton>
<syncfusion:SplitButton Label="Junk" Margin="0,0,12,0" Width="76"/>
<syncfusion:RibbonButton Label="Delete" SizeForm="Large"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Respond" Width="200" Header="Respond">
<syncfusion:RibbonButton Label="Reply" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Reply All" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Forward" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Meeting"/>
<syncfusion:SplitButton Label="IM" Margin="-2,0,6,0" Width="68"/>
<syncfusion:SplitButton Label="More" Margin="-2,0,6,0" Width="68"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Width="170" Name="QuickSteps" Header="Quick Steps">
<syncfusion:RibbonGallery Width="160"    VisualMode="InRibbon" ItemHeight="20" ItemWidth="70">
<syncfusion:RibbonGalleryItem  Content="Move to?"/>
<syncfusion:RibbonGalleryItem  Content="Team Email"/>
<syncfusion:RibbonGalleryItem  Content="ReplyDelete"/>
<syncfusion:RibbonGalleryItem  Content="To Manager"/>
<syncfusion:RibbonGalleryItem  Content="Done"/>
<syncfusion:RibbonGalleryItem  Content="Create New"/>
</syncfusion:RibbonGallery>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Width="170" Header="Find" Name="Find"  >
<syncfusion:RibbonComboBox Label="Filter Email" Width="160">
<ComboBoxItem>Person1@mail.com</ComboBoxItem>
<ComboBoxItem>Person2@mail.com</ComboBoxItem>
<ComboBoxItem>Person3@mail.com</ComboBoxItem>
</syncfusion:RibbonComboBox>
</syncfusion:RibbonBar>
</syncfusion:RibbonTab>
<syncfusion:RibbonTab Caption="SEND/RCEIVE"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="FOLDER"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="VIEW"  IsChecked="False"/>
<syncfusion:Ribbon.QuickAccessToolBar>
<syncfusion:QuickAccessToolBar>
<syncfusion:RibbonButton SizeForm="ExtraSmall"/>
<syncfusion:RibbonButton SizeForm="ExtraSmall" />          
<syncfusion:QuickAccessToolBar.QATMenuItems>
<syncfusion:RibbonButton Label="Send" />
<syncfusion:RibbonButton Label="Forward" />
<syncfusion:RibbonButton Label="ReplyAll" />
<syncfusion:RibbonButton Label="Delete" />
<syncfusion:RibbonButton Label="Print" />
</syncfusion:QuickAccessToolBar.QATMenuItems>
</syncfusion:QuickAccessToolBar>
</syncfusion:Ribbon.QuickAccessToolBar>
<syncfusion:Ribbon.BackStage>
<syncfusion:Backstage/>
</syncfusion:Ribbon.BackStage>
</syncfusion:Ribbon>
</Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}

![WPF Ribbon Displays Back Stage](getting-started_images/wpf-ribbon-back-stage.jpg)

## Add application menu

An Application Menu contains standard commands that are performed like in Microsoft Outlook 2003 UI. Using the `ApplicationMenu` property of the Ribbon, this Menu is viewed by added at the top-left corner of the window.

N>  Visual style is set to `Default` for RibbonWindow in SkinStorage. and BackStage is not applicable when `ApplicationMenu` is used in Ribbon.

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="RibbonControl.MainWindow"       
syncfusion:SkinStorage.VisualStyle="Default" >
<Grid>
<syncfusion:Ribbon x:Name="_ribbon" VerticalAlignment="Top">
<syncfusion:RibbonTab Caption="HOME"  IsChecked="True">
<syncfusion:RibbonBar Name="New" Width="90"  Header="New">
<syncfusion:RibbonButton SizeForm="Large" Label="New Email"/>
<syncfusion:DropDownButton SizeForm="Large" Label="New Items">
<syncfusion:DropDownMenuItem Header="E-mail Message"/>
<syncfusion:DropDownMenuItem Header="Appointment"/>
<syncfusion:DropDownMenuItem Header="Meeting"/>
<syncfusion:DropDownMenuItem Header="Contact"/>
<syncfusion:DropDownMenuItem Header="Task"/>
</syncfusion:DropDownButton>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Delete" Width="130"  Header="Delete">
<syncfusion:RibbonButton Label="Ignore"/>
<syncfusion:SplitButton Label="Clean Up">
<syncfusion:DropDownMenuItem Header="Clean Up Folder"/>
<syncfusion:DropDownMenuItem Header="Clean Up Conversation"/>
<syncfusion:DropDownMenuItem Header="Clean Up Folder/SubFolder"/>
</syncfusion:SplitButton>
<syncfusion:SplitButton Label="Junk" Margin="0,0,12,0" Width="76"/>
<syncfusion:RibbonButton Label="Delete" SizeForm="Large"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Respond" Width="200" Header="Respond">
<syncfusion:RibbonButton Label="Reply" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Reply All" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Forward" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Meeting"/>
<syncfusion:SplitButton Label="IM" Margin="-2,0,6,0" Width="68"/>
<syncfusion:SplitButton Label="More" Margin="-2,0,6,0" Width="68"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Width="170" Name="QuickSteps" Header="Quick Steps">
<syncfusion:RibbonGallery Width="160"    VisualMode="InRibbon" ItemHeight="30" ItemWidth="70">
<syncfusion:RibbonGalleryItem  Content="Move to?"/>
<syncfusion:RibbonGalleryItem  Content="Team Email"/>
<syncfusion:RibbonGalleryItem  Content="ReplyDelete"/>
<syncfusion:RibbonGalleryItem  Content="To Manager"/>
<syncfusion:RibbonGalleryItem  Content="Done"/>
<syncfusion:RibbonGalleryItem  Content="Create New"/>
</syncfusion:RibbonGallery>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Width="170" Header="Find" Name="Find"  >
<syncfusion:RibbonComboBox Label="Filter Email" Width="160">
<ComboBoxItem>Person1@mail.com</ComboBoxItem>
<ComboBoxItem>Person2@mail.com</ComboBoxItem>
<ComboBoxItem>Person3@mail.com</ComboBoxItem>
</syncfusion:RibbonComboBox>
</syncfusion:RibbonBar>
</syncfusion:RibbonTab>
<syncfusion:RibbonTab Caption="SEND/RCEIVE"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="FOLDER"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="VIEW"  IsChecked="False"/>
<syncfusion:Ribbon.QuickAccessToolBar>
<syncfusion:QuickAccessToolBar>
<syncfusion:RibbonButton SizeForm="ExtraSmall"/>
<syncfusion:RibbonButton SizeForm="ExtraSmall" />
<syncfusion:QuickAccessToolBar.QATMenuItems>
<syncfusion:RibbonButton Label="Send" />
<syncfusion:RibbonButton Label="Forward" />
<syncfusion:RibbonButton Label="ReplyAll" />
<syncfusion:RibbonButton Label="Delete" />
<syncfusion:RibbonButton Label="Print" />
</syncfusion:QuickAccessToolBar.QATMenuItems>
</syncfusion:QuickAccessToolBar>
</syncfusion:Ribbon.QuickAccessToolBar>
<syncfusion:Ribbon.ApplicationMenu>
<syncfusion:ApplicationMenu Name="_applicationMenu" Width="38" Height="38" syncfusion:Ribbon.KeyTip="F" IsPopupOpen="False" ApplicationButtonImage="syncfusion.png">
</syncfusion:ApplicationMenu>
</syncfusion:Ribbon.ApplicationMenu>
</syncfusion:Ribbon>
</Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}

![WPF Ribbon with Application Menu](getting-started_images/wpf-ribbon-with-application-menu.jpg)

### Add application items to the application menu

ApplicationItems are displayed in bottom of the Application menu. Different `ApplicationItems` are added to an application menu using its `ApplicationItems` property. Here two RibbonButton with its `Label` property as "Options" and "Exits" are added as ApplicationMenuItems.

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow
xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:syncfusion="http://schemas.syncfusion.com/wpf" x:Class="RibbonControl.MainWindow"       
syncfusion:SkinStorage.VisualStyle="Default"
>
<Grid>
<syncfusion:Ribbon x:Name="_ribbon" VerticalAlignment="Top">
<syncfusion:RibbonTab Caption="HOME"  IsChecked="True">
<syncfusion:RibbonBar Name="New" Width="90"  Header="New">
<syncfusion:RibbonButton SizeForm="Large" Label="New Email"/>
<syncfusion:DropDownButton SizeForm="Large" Label="New Items">
<syncfusion:DropDownMenuItem Header="E-mail Message"/>
<syncfusion:DropDownMenuItem Header="Appointment"/>
<syncfusion:DropDownMenuItem Header="Meeting"/>
<syncfusion:DropDownMenuItem Header="Contact"/>
<syncfusion:DropDownMenuItem Header="Task"/>
</syncfusion:DropDownButton>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Delete" Width="130"  Header="Delete">
<syncfusion:RibbonButton Label="Ignore"/>
<syncfusion:SplitButton Label="Clean Up">
<syncfusion:DropDownMenuItem Header="Clean Up Folder"/>
<syncfusion:DropDownMenuItem Header="Clean Up Conversation"/>
<syncfusion:DropDownMenuItem Header="Clean Up Folder/SubFolder"/>
</syncfusion:SplitButton>
<syncfusion:SplitButton Label="Junk" Margin="0,0,12,0" Width="76"/>
<syncfusion:RibbonButton Label="Delete" SizeForm="Large"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Name="Respond" Width="200" Header="Respond">
<syncfusion:RibbonButton Label="Reply" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Reply All" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Forward" SizeForm="Large"/>
<syncfusion:RibbonButton Label="Meeting"/>
<syncfusion:SplitButton Label="IM" Margin="-2,0,6,0" Width="68"/>
<syncfusion:SplitButton Label="More" Margin="-2,0,6,0" Width="68"/>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Width="170" Name="QuickSteps" Header="Quick Steps">
<syncfusion:RibbonGallery Width="160"    VisualMode="InRibbon" ItemHeight="30" ItemWidth="70">
<syncfusion:RibbonGalleryItem  Content="Move to?"/>
<syncfusion:RibbonGalleryItem  Content="Team Email"/>
<syncfusion:RibbonGalleryItem  Content="ReplyDelete"/>
<syncfusion:RibbonGalleryItem  Content="To Manager"/>
<syncfusion:RibbonGalleryItem  Content="Done"/>
<syncfusion:RibbonGalleryItem  Content="Create New"/>
</syncfusion:RibbonGallery>
</syncfusion:RibbonBar>
<syncfusion:RibbonBar Width="170" Header="Find" Name="Find"  >
<syncfusion:RibbonComboBox Label="Filter Email" Width="160">
<ComboBoxItem>Person1@mail.com</ComboBoxItem>
<ComboBoxItem>Person2@mail.com</ComboBoxItem>
<ComboBoxItem>Person3@mail.com</ComboBoxItem>
</syncfusion:RibbonComboBox>
</syncfusion:RibbonBar>
</syncfusion:RibbonTab>
<syncfusion:RibbonTab Caption="SEND/RCEIVE"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="FOLDER"  IsChecked="False"/>
<syncfusion:RibbonTab Caption="VIEW"  IsChecked="False"/>
<syncfusion:Ribbon.QuickAccessToolBar>
<syncfusion:QuickAccessToolBar>
<syncfusion:RibbonButton SizeForm="ExtraSmall"/>
<syncfusion:RibbonButton SizeForm="ExtraSmall" />
<syncfusion:QuickAccessToolBar.QATMenuItems>
<syncfusion:RibbonButton Label="Send" />
<syncfusion:RibbonButton Label="Forward" />
<syncfusion:RibbonButton Label="ReplyAll" />
<syncfusion:RibbonButton Label="Delete" />
<syncfusion:RibbonButton Label="Print" />
</syncfusion:QuickAccessToolBar.QATMenuItems>
</syncfusion:QuickAccessToolBar>
</syncfusion:Ribbon.QuickAccessToolBar>
<syncfusion:Ribbon.ApplicationMenu>
<syncfusion:ApplicationMenu Name="_applicationMenu" Width="38" Height="38" syncfusion:Ribbon.KeyTip="F" IsPopupOpen="False" ApplicationButtonImage="syncfusion.png">
<syncfusion:SimpleMenuButton Label="File" Icon="Document32.png"/>
<syncfusion:ApplicationMenu.MenuItems>
<syncfusion:SimpleMenuButton Label="New" Icon="Document32.png"/>
<syncfusion:SimpleMenuButton Label="Open" Icon="Open32.png" />
</syncfusion:ApplicationMenu.MenuItems>
<syncfusion:ApplicationMenu.ApplicationItems>
<syncfusion:RibbonButton SizeForm = "Small" Label="Options" SmallIcon="Options.png"/>
<syncfusion:RibbonButton SizeForm = "Small" Label="Exit"  SmallIcon="Exit.png"/>
</syncfusion:ApplicationMenu.ApplicationItems>
</syncfusion:ApplicationMenu>
</syncfusion:Ribbon.ApplicationMenu>
</syncfusion:Ribbon>
</Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}

![WPF Ribbon displays Appication Menu with Application Items](getting-started_images/wpf-ribbon-application-menu-items.jpg)

## Adding custom controls to the title bar

The RibbonWindow allows to load any custom controls into the right side of the title bar by using both [`HeaderItems`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonWindow.html#Syncfusion_Windows_Tools_Controls_RibbonWindow_HeaderItems) and [`HeaderItemsSource`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonWindow.html#Syncfusion_Windows_Tools_Controls_RibbonWindow_HeaderItemsSource) property.

### Adding items using HeaderItems

The [`HeaderItems`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonWindow.html#Syncfusion_Windows_Tools_Controls_RibbonWindow_HeaderItems) property of the RibbonWindow allows you to load any controls directly into the title bar.

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow  x:Class="CustomControl.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:CustomControl"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        xmlns:skin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
        skin:SfSkinManager.Theme="{skin:SkinManagerExtension ThemeName=FluentLight}"
        mc:Ignorable="d"
        Title="CustomControl in the TitleBar" 
        Height="450" Width="800"
        IsGlassActive="False"
        WindowStartupLocation="CenterScreen"
        WindowState="Normal">

        <syncfusion:RibbonWindow.Resources>
            <DataTemplate x:Key="icontemplate">
                <Grid>
                    <Path Data="M26.199951,12.300006L28.399963,12.300006 28.399963,15.899998 32,15.899998 32,18.000004 28.399963,18.000004 28.399963,21.600012 26.199951,21.600012 26.199951,18.000004 22.599976,18.000004 22.599976,15.800007 26.199951,15.800007z M14.799988,0C18.599976,-7.6615834E-08 21.699951,3.8000038 21.699951,8.6000081 21.699951,12.500003 19.699951,15.399998 17,16.800007 16.599976,16.899998 16,17.399998 16,18.000004 16,18.500004 16.599976,19.000004 16.899963,19.10001 22.599976,21.100012 27.5,23.9 29.5,29.400002L0,29.400002C2,23.800009 6.8999634,21.300009 12.599976,19.10001 12.899963,19.000004 13.399963,18.500004 13.399963,18.000004 13.399963,17.500004 12.899963,17.000004 12.599976,16.899998 9.7999878,15.399998 7.8999634,12.600009 7.8999634,8.6000081 7.7999878,3.8000038 10.899963,-7.6615834E-08 14.799988,0z" Stretch="Uniform" Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}" Width="16" Height="16" Margin="0,0,0,0" RenderTransformOrigin="0.5,0.5">
                      <Path.RenderTransform>
                          <TransformGroup>
                              <TransformGroup.Children>
                                  <RotateTransform Angle="0" />
                                  <ScaleTransform ScaleX="1" ScaleY="1" />
                              </TransformGroup.Children>
                          </TransformGroup>
                      </Path.RenderTransform>
                    </Path>
                </Grid>
            </DataTemplate>
        </syncfusion:RibbonWindow.Resources>

        <syncfusion:RibbonWindow.HeaderItems>
            <syncfusion:ButtonAdv x:Name="headerItem" Height="25" Label="Sign-In" SizeMode="Normal" IconTemplate="{StaticResource icontemplate}" />
        </syncfusion:RibbonWindow.HeaderItems>
    
        <Grid>
            <syncfusion:Ribbon x:Name="ribbon" VerticalAlignment="Top">
                <syncfusion:RibbonTab Caption="HOME"  IsChecked="True"/>
                <syncfusion:RibbonTab Caption="SEND/RCEIVE"  IsChecked="False"/>
                <syncfusion:RibbonTab Caption="FOLDER"  IsChecked="False"/>
            </syncfusion:Ribbon>
        </Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}

![WPF Ribbon Adding items using headeritems](getting-started_images/wpf-ribbon-adding-items-using-header-items.jpg)

### Adding items using HeaderItemsSource

The [`HeaderItemsSource`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonWindow.html#Syncfusion_Windows_Tools_Controls_RibbonWindow_HeaderItemsSource) property of the RibbonWindow allows you to bind a collection of objects which used to load custom controls into the right side of the title bar. 

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow  x:Class="CustomControl.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:CustomControl"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
        xmlns:skin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
        skin:SfSkinManager.Theme="{skin:SkinManagerExtension ThemeName=FluentLight}"
        xmlns:listCollection="clr-namespace:System.Collections;assembly=mscorlib"
        mc:Ignorable="d"
        Title="RibbonWindow" 
        Height="450" Width="800"
        IsGlassActive="False"
        WindowStartupLocation="CenterScreen"
        WindowState="Normal">

        <syncfusion:RibbonWindow.Resources>
            <DataTemplate x:Key="icontemplate">
                <Grid>
                    <Path Data="M26.199951,12.300006L28.399963,12.300006 28.399963,15.899998 32,15.899998 32,18.000004 28.399963,18.000004 28.399963,21.600012 26.199951,21.600012 26.199951,18.000004 22.599976,18.000004 22.599976,15.800007 26.199951,15.800007z M14.799988,0C18.599976,-7.6615834E-08 21.699951,3.8000038 21.699951,8.6000081 21.699951,12.500003 19.699951,15.399998 17,16.800007 16.599976,16.899998 16,17.399998 16,18.000004 16,18.500004 16.599976,19.000004 16.899963,19.10001 22.599976,21.100012 27.5,23.9 29.5,29.400002L0,29.400002C2,23.800009 6.8999634,21.300009 12.599976,19.10001 12.899963,19.000004 13.399963,18.500004 13.399963,18.000004 13.399963,17.500004 12.899963,17.000004 12.599976,16.899998 9.7999878,15.399998 7.8999634,12.600009 7.8999634,8.6000081 7.7999878,3.8000038 10.899963,-7.6615834E-08 14.799988,0z" Stretch="Uniform" Fill="{Binding RelativeSource={RelativeSource Mode=Self}, Path=(TextBlock.Foreground)}" Width="16" Height="16" Margin="0,0,0,0" RenderTransformOrigin="0.5,0.5">
                        <Path.RenderTransform>
                            <TransformGroup>
                                <TransformGroup.Children>
                                    <RotateTransform Angle="0" />
                                    <ScaleTransform ScaleX="1" ScaleY="1" />
                                </TransformGroup.Children>
                            </TransformGroup>
                        </Path.RenderTransform>
                    </Path>
                </Grid>
            </DataTemplate>
        </syncfusion:RibbonWindow.Resources>

        <syncfusion:RibbonWindow.HeaderItemsSource>
            <listCollection:ArrayList>
                <TextBox x:Name="textBox" Text="Search" Width="100"/>
                <syncfusion:ButtonAdv x:Name="headerItem" Height="25" Margin="25,0,0,0" Label="Sign-In" SizeMode="Normal" IconTemplate="{StaticResource icontemplate}" />
            </listCollection:ArrayList>
        </syncfusion:RibbonWindow.HeaderItemsSource>

        <Grid>
            <syncfusion:Ribbon x:Name="ribbon" VerticalAlignment="Top">
                <syncfusion:RibbonTab Caption="HOME"  IsChecked="True"/>
                <syncfusion:RibbonTab Caption="SEND/RCEIVE"  IsChecked="False"/>
                <syncfusion:RibbonTab Caption="FOLDER"  IsChecked="False"/>
            </syncfusion:Ribbon>
        </Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}

![WPF Ribbon Adding Items Using Header Items Source](getting-started_images/wpf-ribbon-adding-items-using-header-items-source.jpg)

### Setting HeaderItemTemplate

The RibbonWindow allows you to customize the visual appearance of the custom items stored in the [`HeaderItemsSource`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonWindow.html#Syncfusion_Windows_Tools_Controls_RibbonWindow_HeaderItemsSource) using [`HeaderItemTemplate`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonWindow.html#Syncfusion_Windows_Tools_Controls_RibbonWindow_HeaderItemTemplate) property.

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow  x:Class="CustomControl.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:CustomControl"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
        xmlns:skin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
        skin:SfSkinManager.Theme="{skin:SkinManagerExtension ThemeName=FluentLight}"
        xmlns:listCollection="clr-namespace:System.Collections;assembly=mscorlib"
        xmlns:system="clr-namespace:System;assembly=mscorlib"
        mc:Ignorable="d"
        Title="RibbonWindow" 
        Height="450" Width="800"
        IsGlassActive="False"
        WindowStartupLocation="CenterScreen"
        WindowState="Normal">

        <syncfusion:RibbonWindow.HeaderItemTemplate>
            <DataTemplate>
                <Grid>
                    <Border Margin="1" Width="60" Height="22" Background="Blue">
                        <TextBlock Foreground="Yellow" Text="{Binding}" TextAlignment="Center" />
                    </Border>
                </Grid>
            </DataTemplate>
        </syncfusion:RibbonWindow.HeaderItemTemplate>

        <syncfusion:RibbonWindow.HeaderItemsSource>
            <listCollection:ArrayList>
                <system:String>Search</system:String>
                <system:String>Sign-In</system:String>
            </listCollection:ArrayList>
        </syncfusion:RibbonWindow.HeaderItemsSource>

        <Grid>
            <syncfusion:Ribbon x:Name="ribbon" VerticalAlignment="Top">
                <syncfusion:RibbonTab Caption="HOME"  IsChecked="True"/>
                <syncfusion:RibbonTab Caption="SEND/RCEIVE"  IsChecked="False"/>
                <syncfusion:RibbonTab Caption="FOLDER"  IsChecked="False"/>
            </syncfusion:Ribbon>
        </Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% endtabs %}

![WPF Ribbon Setting Header Item Template](getting-started_images/wpf-ribbon-setting-header-item-template.jpg)

### Setting HeaderItemTemplateSelector

The RibbonWindow allows you to customize the visual appearance of each item with different templates based on specific constraints by using the [`HeaderItemTemplateSelector`](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Tools.Controls.RibbonWindow.html#Syncfusion_Windows_Tools_Controls_RibbonWindow_HeaderItemTemplateSelector).

{% tabs %}

{% highlight XAML %}

<syncfusion:RibbonWindow  x:Class="CustomControl.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:CustomControl"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf" 
        xmlns:skin="clr-namespace:Syncfusion.SfSkinManager;assembly=Syncfusion.SfSkinManager.WPF"
        skin:SfSkinManager.Theme="{skin:SkinManagerExtension ThemeName=FluentLight}"
        xmlns:listCollection="clr-namespace:System.Collections;assembly=mscorlib"
        xmlns:system="clr-namespace:System;assembly=mscorlib"
        mc:Ignorable="d"
        Title="RibbonWindow" 
        Height="450" Width="800"
        IsGlassActive="False"
        WindowStartupLocation="CenterScreen"
        WindowState="Normal">

        <syncfusion:RibbonWindow.Resources>
            <DataTemplate x:Key="BlueBorderTemplate" >
                <Border Margin="1" Width="60" Height="22" Background="Blue">
                    <TextBlock Foreground="Yellow" Text="{Binding}" TextAlignment="Center" />
                </Border>
            </DataTemplate>
            <DataTemplate x:Key="OrangeBorderTemplate">
                <Border Margin="1" Width="60" Height="22" Background="Orange">
                    <TextBlock Foreground="Green" Text="{Binding}" TextAlignment="Center" />
                </Border>
            </DataTemplate>
        </syncfusion:RibbonWindow.Resources>
    
        <syncfusion:RibbonWindow.HeaderItemTemplateSelector>
            <local:ItemTemplateSelector/>
        </syncfusion:RibbonWindow.HeaderItemTemplateSelector>

        <syncfusion:RibbonWindow.HeaderItemsSource>
            <listCollection:ArrayList>
                <system:String>Search</system:String>
                <system:String>Sign-In</system:String>
            </listCollection:ArrayList>
        </syncfusion:RibbonWindow.HeaderItemsSource>

        <Grid>
            <syncfusion:Ribbon x:Name="ribbon" VerticalAlignment="Top">
                <syncfusion:RibbonTab Caption="HOME"  IsChecked="True"/>
                <syncfusion:RibbonTab Caption="SEND/RCEIVE"  IsChecked="False"/>
                <syncfusion:RibbonTab Caption="FOLDER"  IsChecked="False"/>
            </syncfusion:Ribbon>
        </Grid>
</syncfusion:RibbonWindow>

{% endhighlight %}

{% highlight C# %}

public class ItemTemplateSelector : DataTemplateSelector
{
    public override DataTemplate SelectTemplate(object item, DependencyObject container)
    {
        if (item.ToString() == "Search")
        {
            return (container as FrameworkElement).TryFindResource("BlueBorderTemplate") as DataTemplate;
        }
        if (item.ToString() == "Sign-In")
        {
            return (container as FrameworkElement).TryFindResource("OrangeBorderTemplate") as DataTemplate;
        }
        return base.SelectTemplate(item, container);
    }
}

{% endhighlight %}

{% endtabs %}

![WPF Ribbon Setting Header Item Template Selector](getting-started_images/wpf-ribbon-setting-header-item-template-selector.jpg)

N> [View sample in GitHub](https://github.com/SyncfusionExamples/syncfusion-wpf-ribbon-examples/tree/main/Samples/Adding-custom-control-to-the-titlebar)

## Set simplified layout

The simplified layout is designed to display the most commonly used Ribbon commands in a single line interface, allowing more screen space for compact content viewing, while other commands are placed inside the overflow menu. To know more about the simplified layout, refer [here](https://help.syncfusion.com/wpf/ribbon/simplifiedlayout).

## Theme

Ribbon supports various built-in themes. Refer to the below links to apply themes for the Ribbon,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Applying Theme to WPF Ribbon](getting-started_images/wpf-ribbon-theme.png)