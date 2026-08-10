---
layout: post
title: Getting Started with WPF TaskBar control | Syncfusion
description: Learn here about getting started with Syncfusion Essential Studio WPF TaskBar control, its elements and more.
platform: wpf
control: TaskBar
documentation: ug
---

# Getting Started with WPF TaskBar

This section guides you on getting started with the TaskBar control. It covers the following topics:

## Overview of the TaskBar control

The TaskBar control provides a UI similar to the Windows Explorer taskbar. It provides a consistent UI for placing commonly used functionalities as grouped items. You can place any container panel control inside the TaskBar. For example, when a customized `Grid` with other controls is placed inside a `TaskBarItem`, they are automatically arranged within the `TaskBar.Items` collection. The TaskBar supports the following built-in visual styles: Office2007Blue, Office2007Black, Office2007Silver, Office2003, and Blend.

![Displaying TaskBar control](Getting-Started_images/Getting-Started_img1.jpeg)

## Why choose the TaskBar control

Here are some highlights of the TaskBar control.

* Windows Explorer taskbar appearance can be achieved
* Horizontal and vertical layouts for TaskBar boxes
* Provides support to customize the background, header size, and collapse/expand the TaskBar header
* Keyboard navigation support
* Ability to specify custom group margin and padding
* Supports built-in visual styles - Default, Win XP, Zune, Aero, Office2007Blue, Office2007Black, Office2007Silver, Office2003, Blend, LunaRoyale, LunaHomestead, and LunaMetallic

## Creating the TaskBar

There are two possible ways to create a simple TaskBar control.

### Through the designer

To create the TaskBar control through the designer, do the following steps:

1. Drag the TaskBar control from the toolbox onto your WPF application.

     ![Adding TaskBar control via designer](Getting-Started_images/Getting-Started_img2.jpeg)

2. Set the properties for the TaskBar in design mode by using the Smart Tag feature (for example, set `Name`, `Orientation`, and add `TaskBarItem` children).

### Programmatically

The TaskBar control is created by using either XAML or C# code. Before using the control, install the required NuGet package and reference the necessary assemblies/namespaces:

* **NuGet package:** `Syncfusion.Tools.WPF` (install with `Install-Package Syncfusion.Tools.WPF`)
* **Assemblies added by the package:**
  * `Syncfusion.Tools.WPF`
  * `Syncfusion.Shared.WPF`
* **Namespaces to register:**
  * XAML: `xmlns:syncfusion="http://schemas.syncfusion.com/wpf"` on the root element
  * C#: `using Syncfusion.Windows.Tools.Controls;`

{%tabs%}
{% highlight xaml %}
<!-- Adding TaskBar -->
<Window x:Class="TaskBarSample.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:TaskBarSample"
        xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Grid x:Name="grid">
        <syncfusion:TaskBar Name="taskBar" />
    </Grid>
</Window>
{% endhighlight %}

{% highlight c# %}
using System.Windows;
using Syncfusion.Windows.Tools.Controls;

public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();

        // Creating an instance of TaskBar
        TaskBar taskBar = new TaskBar();

        // Adding the TaskBar as a child of the grid in the window
        grid.Children.Add(taskBar);
    }
}
{% endhighlight %}
{%endtabs%}

The following screenshot shows the TaskBar control.

![Programmatically adding TaskBar control](Getting-Started_images/Getting-Started_img3.jpeg)

## Theme

The TaskBar supports various built-in themes. Refer to the following links to apply themes to the TaskBar:

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF TaskBar control](Getting-Started_images/Theme.png)