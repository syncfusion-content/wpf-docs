---
layout: post
title: Getting Started with WPF Tree Navigator control | Syncfusion
description: Learn here about getting started with Syncfusion WPF Tree Navigator (SfTreeNavigator) control, its elements and more.
platform: wpf
control: SfTreeNavigator 
documentation: ug
---

# Getting Started with WPF Tree Navigator (SfTreeNavigator)

This section explains the steps required to add the Wpf [SfTreeNavigator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Navigation.SfTreeNavigator.html) control with its basic features.

Namespace : Syncfusion.Windows.Controls.Navigation 

Assembly : Syncfusion.SfTreeNavigator.WPF (in Syncfusion.SfTreeNavigator.WPF.dll) 

## Adding WPF SfTreeNavigator via xaml

1. Create a [Wpf desktop app for C# and .NET 6](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/get-started/create-app-visual-studio?view=netdesktop-9.0).
2. Add reference to [Syncfusion.SfTreeNavigator.Wpf](https://www.nuget.org/packages/Syncfusion.SfTreeNavigator.Wpf) NuGet. 
3. Import the control namespace `Syncfusion.Windows.Controls.Navigation` in XAML or C# code.
4. Initialize the [SfTreeNavigator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Navigation.SfTreeNavigator.html) control.

{%tabs%}

{% highlight xaml %}

<Page
    x:Class="GettingStarted.MainPage"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:GettingStarted"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:syncfusion="using:Syncfusion.UI.Xaml.Chat"
    mc:Ignorable="d"
    Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">
    <Grid>
      <navigation:SfTreeNavigator Header="Enterprise Toolkit" >
          <navigation:SfTreeNavigatorItem Header="WinRT (XAML)">
          <navigation:SfTreeNavigatorItem Header="Chart"/>
          <navigation:SfTreeNavigatorItem Header="Tools"/>
          </navigation:SfTreeNavigatorItem>
          <navigation:SfTreeNavigatorItem Header="Metro Studio"/>
      </navigation:SfTreeNavigator>
    </Grid>
</Page>

{% endhighlight %}

{% endtabs %}

## Adding WPF SfTreeNavigator via C#

1. Create a [Wpf desktop app for C# and .NET 6](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/get-started/create-app-visual-studio?view=netdesktop-9.0).
2. Add reference to [Syncfusion.SfTreeNavigator.Wpf](https://www.nuget.org/packages/Syncfusion.SfTreeNavigator.Wpf) NuGet. 
3. Import the control namespace `Syncfusion.Windows.Controls.Navigation` in XAML or C# code.
4. Initialize the [SfTreeNavigator](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.Navigation.SfTreeNavigator.html) control.

{% tabs %}

{% highlight C# %}

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
            SfTreeNavigator sfToolkit = new SfTreeNavigator();
            SfTreeNavigatorItem winrt = new SfTreeNavigatorItem() {Header = "WinRT (XAML)"};
            SfTreeNavigatorItem metroStudio = new SfTreeNavigatorItem() {Header = "Metro Studio"};
            SfTreeNavigatorItem winrt_chart = new SfTreeNavigatorItem() {Header = "Chart"};
            SfTreeNavigatorItem winrt_tools = new SfTreeNavigatorItem() {Header = "Tools"};

            winrt.Items.Add(winrt_chart);
            winrt.Items.Add(winrt_tools);

            sfToolkit.Items.Add(winrt);
            sfToolkit.Items.Add(metroStudio);
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