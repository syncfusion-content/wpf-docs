---
layout: post
title: Getting started with WPF Markdown Viewer control | Syncfusion
description: Learn how to get started with Syncfusion® WPF SfMarkdownViewer control and explore its capabilities for rendering Markdown content.
platform: wpf
control: SfMarkdownViewer
documentation: ug
keywords: wpf markdownviewer, syncfusion markdownviewer wpf, markdown viewer wpf, wpf markdown rendering, sfmarkdownviewer wpf, wpf markdown control, markdown rendering wpf, wpf markdown getting started
---

# Getting Started with WPF Markdown Viewer (SfMarkdownViewer)

This section provides a step-by-step guide to integrate and use the [SfMarkdownViewer] (https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Markdown.SfMarkdownViewer.html) control in your WPF applications.

## Assembly deployment

Refer to the [Control Dependencies](https://help.syncfusion.com/wpf/control-dependencies#sfbadge) section to get the list of assemblies or NuGet package that needs to be added as a reference to use the control in any application.

Refer to this [documentation](https://help.syncfusion.com/wpf/visual-studio-integration/nuget-packages) to find more details about installing nuget packages in a WPF application.

## Step 1: Create a New WPF Project

1. Go to **File > New > Project** and choose the **WPF App** template.
2. Name the project and choose a location. Then click **Next**.
3. Select the .NET framework version and click **Create**.

## Step 2: Install the Syncfusion<sup>&reg;</sup> WPF MarkdownViewer NuGet Package

1. In **Solution Explorer,** right-click the project and choose **Manage NuGet Packages.**
2. Search for [Syncfusion.SfMarkdownViewer.Wpf](https://help.syncfusion.com/cr/wpf/Syncfusion.SfMarkdownViewer.Wpf.html) and install the latest version.
3. Ensure the necessary dependencies are installed correctly, and the project is restored.

## Adding WPF SfMarkdownViewer via XAML

To add the `SfMarkdownViewer` manually in XAML, follow these steps:

1. Create a new WPF project in Visual Studio.

2. Add the following required assembly references to the project:

    * Syncfusion.SfMarkdownViewer.WPF
    * Syncfusion.Markdown
    * Syncfusion.Shared.WPF

3. Import the control namespace `Syncfusion.UI.Xaml.Markdown` in XAML, and declare the `SfMarkdownViewer` in XAML page.

{% tabs %}
{% highlight xaml %}

<Window
    x:Class="GettingStarted.MainWindow"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    xmlns:markdown="clr-namespace:Syncfusion.UI.Xaml.Markdown;assembly=Syncfusion.SfMarkdownViewer.WPF"
    xmlns:system="clr-namespace:System;assembly=mscorlib">
    <Grid>
        <markdown:SfMarkdownViewer />
    </Grid>
</Window>
 
{% endhighlight %}
{% endtabs %}

## Adding WPF SfMarkdownViewer via C#

To add the `SfMarkdownViewer` manually in C#, follow these steps:

1. Create a new WPF project in Visual Studio.

2. Add the following required assembly references to the project:

    * Syncfusion.SfMarkdownViewer.WPF
    * Syncfusion.Markdown
    * Syncfusion.Shared.WPF

3. Import the control namespace `Syncfusion.UI.Xaml.Markdown` in C#, and add the `SfMarkdownViewer` in C# page.

{% tabs %}
{% highlight C# %}

using Syncfusion.UI.Xaml.Markdown;

namespace MarkdownViewerGettingStarted
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            // Creating an instance of the SfMarkdownViewer control
            SfMarkdownViewer markdownViewer = new SfMarkdownViewer();
            this.Content = markdownViewer;

        }
    }
}

{% endhighlight %}
{% endtabs %}

## Add Source to the SfMarkdownViewer

The `Source` property is used to provide Markdown content to the control. The Source accepts raw Markdown text, file paths, or HTTP/HTTPS URLs.

{% tabs %} 
{% highlight xaml %}

<markdown:SfMarkdownViewer>
    <markdown:SfMarkdownViewer.Source>
        <system:String xml:space="preserve">
            <![CDATA[
# What is the Markdown Viewer?  
The MarkdownViewer control is used to render and preview Markdown files. It converts markdown syntax into a clean, readable format and supports elements such as headings, lists, code blocks, tables, and other common markdown structures.

# Header 1  
Used for the main title or top-level heading in a Markdown document. 

## Header 2  
Used to define major sections within your Markdown content.

![WPF SfMarkdownViewer](Images/wpf-markdown-viewer-gettingstarted.png)
            ]]>
        </system:String>
    </markdown:SfMarkdownViewer.Source>
</markdown:SfMarkdownViewer>

{% endhighlight %}

{% highlight C# %}

public partial class MainWindow : Window
{
        private const string markdownContent = @"
# What is the Markdown Viewer?  
The MarkdownViewer control is used to render and preview Markdown files. It converts markdown syntax into a clean, readable format and supports elements such as headings, lists, code blocks, tables, and other common markdown structures.

# Header 1  
Used for the main title or top-level heading in a Markdown document. 

## Header 2  
Used to define major sections within your Markdown content.

![WPF SfMarkdownViewer](Images/wpf-markdown-viewer-gettingstarted.png)";

    public MainWindow()
    {
        InitializeComponent();  
        SfMarkdownViewer markdownViewer = new SfMarkdownViewer();
        markdownViewer.Source = markdownContent;
        this.Content = markdownViewer;
    }
}  

{% endhighlight %}
{% endtabs %}

![WPF SfMarkdownViewer](Images/wpf-markdown-viewer-gettingstarted.png)