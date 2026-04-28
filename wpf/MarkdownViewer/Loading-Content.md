---
layout: post
title: Load Markdown Content in WPF Markdown Viewer | Syncfusion
description: Learn how to load Markdown content from various sources (strings, local files, URLs) in the Syncfusion WPF SfMarkdownViewer control.
platform: wpf
control: SfMarkdownViewer
documentation: ug
---

# Loading Markdown Content in WPF Markdown Viewer

The SfMarkdownViewer control provides flexible options for loading Markdown content from multiple sources. The `Source` property intelligently detects the input type and handles content loading automatically, supporting raw Markdown strings, local file paths, and HTTP/HTTPS URLs.

## Loading from Raw Markdown String

Assign a Markdown-formatted string to the Source property of the SfMarkdownViewer control to render markdown content directly within your application.

{% tabs %} 
{% highlight xaml %}

<Grid>
    <markdown:SfMarkdownViewer>
        <markdown:SfMarkdownViewer.Source>
            <system:String xml:space="preserve">
                <![CDATA[
    # What is the Markdown Viewer?  
    The Markdown Viewer control is used to render and preview Markdown files. It converts markdown syntax into a clean, readable format and supports elements such as headings, lists, code blocks, tables, and other common markdown structures.

    # Header 1  
    Used for the main title or top-level heading in a Markdown document. 

    ## Header 2  
    Used to define major sections within your Markdown content.
                ]]>
            </system:String>
        </markdown:SfMarkdownViewer.Source>
    </markdown:SfMarkdownViewer>
</Grid>

{% endhighlight %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Markdown;

namespace MarkdownViewerGettingStarted
{
    public partial class MainWindow : Window
    {
        private const string markdownContent = @"
# What is the Markdown Viewer?  
The Markdown Viewer control is used to render and preview Markdown files. It converts markdown syntax into a clean, readable format and supports elements such as headings, lists, code blocks, tables, and other common markdown structures.

# Header 1  
Used for the main title or top-level heading in a Markdown document. 

## Header 2  
Used to define major sections within your Markdown content.";
        
        public MainWindow()
        {
            InitializeComponent();  
            SfMarkdownViewer markdownViewer = new SfMarkdownViewer();
            markdownViewer.Source = markdownContent;
            this.Content = markdownViewer;      
        }
    }   
}

{% endhighlight %}
{% endtabs %}

## Loading from Local File

To load Markdown content from a local markdown file, simply assign the file path to the Source property. The control automatically detects valid file paths and reads the file contents.

**C#**

{% highlight C# %}

public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
        SfMarkdownViewer markdownViewer = new SfMarkdownViewer();
        string filePath = @"D:\MAUI\MarkdownViewer\Files\MarkdownContent.md";
        string markdownContent = File.ReadAllText(filePath);
        markdownViewer.Source = markdownContent;
        this.Content = markdownViewer;  
    }
}

{% endhighlight %}

## Loading from URL

The `SfMarkdownViewer` can load Markdown content directly from publicly accessible URLs. This is particularly useful for displaying remote documentation, release notes, or any Markdown content hosted online.

{% tabs %}
{% highlight xaml %}

<Window>
    <markdown:SfMarkdownViewer Source="https://raw.githubusercontent.com/SyncfusionExamples/wpf-tabsplitter-example/refs/heads/master/README.md">
    </markdown:SfMarkdownViewer>
</Window>

{% endhighlight %}

{% highlight C# %}

public partial class MainWindow : Window
{ 
    public MainWindow()
    {
        InitializeComponent();  
        SfMarkdownViewer markdownViewer = new SfMarkdownViewer();
        markdownViewer.Source = "https://raw.githubusercontent.com/SyncfusionExamples/wpf-tabsplitter-example/refs/heads/master/README.md";
        this.Content = markdownViewer;       
    }
} 

{% endhighlight %}
{% endtabs %}
