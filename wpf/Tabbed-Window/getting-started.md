---
layout: post
title: Getting Started with WPF Tabbed Window | Syncfusion
description: Learn how to create and use WPF Tabbed Window by combining SfChromelessWindow with SfTabControl for document management applications.
platform: wpf
control: TabbedWindow
documentation: ug
---

# Getting Started with WPF TabbedWindow

This section explains how to create a tabbed window interface using the SfChromelessWindow and SfTabControl controls. The TabbedWindow provides a browser-style, document-based user interface that integrates tabs directly into the window chrome, similar to modern IDEs and web browsers.

## Assembly Deployment

To integrate the TabbedWindow in you WPF application, add the following required assemblies or NuGet packages:

- Syncfusion.SfChromelessWindow.WPF
- Syncfusion.Shared.WPF

## Adding TabbedWindow via XAML

To add the TabbedWindow manually in XAML, follow these steps:

1. Create a new WPF project in Visual Studio  with required .NET Framework or .NET Core version.

2. Add the required assembly references or NuGet packages mentioned in the Assembly Deployment section.

3. Import the Syncfusion WPF schema in your XAML file:

```XML
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
```

4. Create a window that uses `SfChromelessWindow` and set its `WindowType` property to `Tabbed`, and include an `SfTabControl` with the required tab items.

{% tabs %}

{% highlight XAML %}

<syncfusion:SfChromelessWindow
    x:Class="TabbedWindowDemo.MainWindow"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:syncfusion="http://schemas.syncfusion.com/wpf"
    WindowType="Tabbed"
    Height="450"
    Width="800">

    <syncfusion:SfTabControl>
        <syncfusion:SfTabItem Header="Home" Content="Welcome to Home Tab"/>
        <syncfusion:SfTabItem Header="File" Content="Welcome to File Tab"/>
        <syncfusion:SfTabItem Header="Edit" Content="Welcome to Edit Tab"/>
        <syncfusion:SfTabItem Header="Tools" Content="Welcome to Tools Tab"/>
    </syncfusion:SfTabControl>

</syncfusion:SfChromelessWindow>

{% endhighlight %}

{% endtabs %}

## Adding WPF TabbedWindow via C#

To add the TabbedWindow control manually in C#, follow these steps:

1. Create a new WPF project in Visual Studio with the required .NET Framework or .NET Core version.

2. Add the required assembly references or NuGet packages mentioned in the Assembly Deployment section.

3. Include the required namespace, create a window that inherits from `SfChromelessWindow`, set its `WindowType` to `Tabbed`, and include an `SfTabControl` with the required tab items.

{% tabs %}

{% highlight C# %}

using Syncfusion.Windows.Controls;

public partial class MainWindow : SfChromelessWindow
{
    public MainWindow()
    {
        InitializeComponent();
        WindowType = WindowType.Tabbed;

        var tabControl = new SfTabControl();

        tabControl.Items.Add(new SfTabItem
        {
            Header = "Document 1",
            Content = new TextBlock { Text = "Document 1 Content" }
        });

        tabControl.Items.Add(new SfTabItem
        {
            Header = "Document 2",
            Content = new TextBlock { Text = "Document 2 Content" }
        });

        Content = tabControl;
    }
}

{% endhighlight %}

{% endtabs %}

![WPF Tabbed Window](getting-started_images/wpf_tabbedwindow.png)
