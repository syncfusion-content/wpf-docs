---
layout: post
title: Getting Started with WPF Tree Navigator | Syncfusion®
description: Learn how to get started with the Syncfusion® WPF Tree Navigator control. Explore setup, features, examples, and customization options.
platform: wpf
control: Tree Navigator
documentation: ug
---

# Getting Started with WPF Tree Navigator

This section explains the steps required to add the WPF [Tree Navigator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Navigation.SfTreeNavigator.html) control with its basic features.

**Namespace:** `Syncfusion.Windows.Controls.Navigation`

**Assembly:** `Syncfusion.SfTreeNavigator.WPF.dll`

## Adding WPF Tree Navigator via XAML

1. Create a [WPF desktop app for C#](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/get-started/create-app-visual-studio).
2. Add a reference to the [Syncfusion.SfTreeNavigator.Wpf](https://www.nuget.org/packages/Syncfusion.SfTreeNavigator.Wpf) NuGet package.
3. Import the namespace `Syncfusion.Windows.Controls.Navigation` in XAML or C# code.
4. Add an [Tree Navigator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Navigation.SfTreeNavigator.html) instance to your view (for example, inside `MainWindow.xaml`).

{% tabs %}

{% highlight xaml %}

<Window
    x:Class="GettingStarted.MainWindow"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:navigation="clr-namespace:Syncfusion.Windows.Controls.Navigation;assembly=Syncfusion.SfTreeNavigator.WPF"
    mc:Ignorable="d"
    Title="Getting Started" Height="450" Width="800">
    <Grid>
        <navigation:SfTreeNavigator Header="Enterprise Toolkit">
            <navigation:SfTreeNavigatorItem Header="WinRT (XAML)">
                <navigation:SfTreeNavigatorItem Header="Chart" />
                <navigation:SfTreeNavigatorItem Header="Tools" />
            </navigation:SfTreeNavigatorItem>
            <navigation:SfTreeNavigatorItem Header="Metro Studio" />
        </navigation:SfTreeNavigator>
    </Grid>
</Window>

{% endhighlight %}

{% endtabs %}

## Adding WPF Tree Navigator via C#

1. Create a [WPF desktop app for C# and .NET 6](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/get-started/create-app-visual-studio?view=netdesktop-6.0).
2. Add a reference to the [Syncfusion.SfTreeNavigator.Wpf](https://www.nuget.org/packages/Syncfusion.SfTreeNavigator.Wpf) NuGet package.
3. Import the namespace `Syncfusion.Windows.Controls.Navigation` in XAML or C# code.
4. Add an [Tree Navigator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Navigation.SfTreeNavigator.html) instance to your window's content.

{% tabs %}

{% highlight C# %}

using System.Windows;
using Syncfusion.Windows.Controls.Navigation;

namespace GettingStarted
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            this.InitializeComponent();
            // Creating an instance of the SfTreeNavigator control
            SfTreeNavigator sfToolkit = new SfTreeNavigator() { Header = "Enterprise Toolkit" };
            SfTreeNavigatorItem winrt = new SfTreeNavigatorItem() { Header = "WinRT (XAML)" };
            SfTreeNavigatorItem metroStudio = new SfTreeNavigatorItem() { Header = "Metro Studio" };
            SfTreeNavigatorItem winrtChart = new SfTreeNavigatorItem() { Header = "Chart" };
            SfTreeNavigatorItem winrtTools = new SfTreeNavigatorItem() { Header = "Tools" };

            winrt.Items.Add(winrtChart);
            winrt.Items.Add(winrtTools);

            sfToolkit.Items.Add(winrt);
            sfToolkit.Items.Add(metroStudio);

            this.Content = sfToolkit;
        }
    }
}

{% endhighlight %}

{% endtabs %}

N> You can refer the Tree Navigator demo in the Essential Studio WPF [SampleBrowser](https://github.com/syncfusion/wpf-demos/tree/master/navigation) to view its features.

## Theme

Tree Navigator supports various built-in themes. Refer to the below links to apply themes for the Tree Navigator,

  * [Apply theme using SfSkinManager](https://help.syncfusion.com/wpf/themes/skin-manager)
	
  * [Create a custom theme using ThemeStudio](https://help.syncfusion.com/wpf/themes/theme-studio#creating-custom-theme)

  ![Setting theme to WPF Tree Navigator](Populating-Items_images/Theme.png)
