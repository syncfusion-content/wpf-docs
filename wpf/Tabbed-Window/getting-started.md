---
layout: post
title: Getting Started with WPF Tabbed Window | Syncfusion
description: Learn how to create and use WPF Tabbed Window by combining SfChromelessWindow with SfTabControl for document management applications.
platform: wpf
control: TabbedWindow
documentation: ug
---

# Getting Started with WPF TabbedWindow

This section explains how to create a TabbedWindow in a WPF application and provides an overview of its basic functionalities.

## Assembly Deployment

Add the following required Syncfusion assemblies to your project:

- Syncfusion.SfChromelessWindow.WPF
- Syncfusion.Shared.WPF

## Adding WPF TabbedWindow via XAML

Create a window that inherits from `SfChromelessWindow` and set the `WindowType` as `Tabbed`.

{% tabs %}

{% highlight XAML %}

<syncfusion:SfChromelessWindow xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
                               WindowType="Tabbed"
                               Height="450"
                               Width="800">
    <syncfusion:SfTabControl x:Name="MainTabControl">
        <syncfusion:SfTabItem Header="Home" Content="Welcome to Home Tab"/>
        <syncfusion:SfTabItem Header="File" Content="Welcome to File Tab"/>
        <syncfusion:SfTabItem Header="Edit" Content="Welcome to Edit Tab"/>
        <syncfusion:SfTabItem Header="Tools" Content="Welcome to Tools Tab"/>
    </syncfusion:SfTabControl>
</syncfusion:SfChromelessWindow>

{% endhighlight %}

{% endtabs %}

## Adding WPF TabbedWindow via C#

Create the code-behind file as shown below.

{% tabs %}

{% highlight C# %}

using Syncfusion.Windows.Controls;

public partial class MainWindow : SfChromelessWindow
{
    public MainWindow()
    {
        InitializeComponent();

        this.WindowType = WindowType.Tabbed;

        var tabControl = new SfTabControl();
        var tab = new SfTabItem
        {
            Header = "Document 1",
            Content = new TextBlock { Text = "Doc 1" }
        };

        tabControl.Items.Add(tab);
        this.Content = tabControl;
    }
}

{% endhighlight %}

{% endtabs %}

## Populating tabs using SfTabItem

You can populate tabs by adding `SfTabItem` elements inside the `SfTabControl`.

{% tabs %}

{% highlight XAML %}

<syncfusion:SfChromelessWindow xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
                               WindowType="Tabbed"
                               Height="450"
                               Width="800">
    <syncfusion:SfTabControl x:Name="MainTabControl">
        <syncfusion:SfTabItem Header="Home" Content="Welcome to Home Tab"/>
        <syncfusion:SfTabItem Header="File" Content="Welcome to File Tab"/>
        <syncfusion:SfTabItem Header="Edit" Content="Welcome to Edit Tab"/>
        <syncfusion:SfTabItem Header="Tools" Content="Welcome to Tools Tab"/>
    </syncfusion:SfTabControl>
</syncfusion:SfChromelessWindow>

{% endhighlight %}

{% endtabs %}

![WPF Tabbed Window](getting-started_images/wpf_tabbedwindow.png)

## Configuring the Window Types

The SfTabControl supports two distinct window modes that control how tabs are displayed in the application.

### Tabbed Mode

In Tabbed mode, tabs are integrated into the window chrome area, similar to modern web browsers. This creates a unified interface where the title bar and tab strip appear together.

{% tabs %}

{% highlight XAML %}

<syncfusion:SfChromelessWindow
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
    x:Class="TabbedWindowApp.MainWindow"
    WindowType="Tabbed"
    Height="600"
    Width="900">
    <syncfusion:SfTabControl AllowDragDrop="True" EnableNewTabButton="True">
        <syncfusion:SfTabItem Header="Document 1"
                              CloseButtonVisibility="Visible"
                              Content="Tabs are integrated into window chrome"/>
        <syncfusion:SfTabItem Header="Document 2"
                              CloseButtonVisibility="Visible"
                              Content="Similar to browser interface"/>
    </syncfusion:SfTabControl>
</syncfusion:SfChromelessWindow>

{% endhighlight %}

{% endtabs %}

![WPF Tabbed Window](getting-started_images/tabbedwindow.png)

### Normal Mode

In Normal mode, the `SfTabControl` is displayed as regular content within the window. This provides a traditional tabbed layout where the tabs are shown inside the content area instead of the chrome area.

{% tabs %}

{% highlight XAML %}

<syncfusion:SfChromelessWindow
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
    x:Class="TabbedWindowApp.MainWindow"
    Title="View Manager"
    WindowType="Normal"
    Height="600"
    Width="900">
    <Grid>
        <syncfusion:SfTabControl AllowDragDrop="True">
            <syncfusion:SfTabItem Header="View 1" Content="Tab control is regular content"/>
            <syncfusion:SfTabItem Header="View 2" Content="Not integrated into chrome"/>
        </syncfusion:SfTabControl>
    </Grid>
</syncfusion:SfChromelessWindow>

{% endhighlight %}

{% endtabs %}

![Normal mode](getting-started_images/wpf_normalwindow.png)
