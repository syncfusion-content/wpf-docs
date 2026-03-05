---
layout: post
title: Markdown Content Sources in .NET WPF MarkdownViewer | Syncfusion
description: Learn how to load Markdown content from strings, local files, embedded resources, and URLs in the Syncfusion .NET WPF MarkdownViewer control.
platform: wpf
control: SfMarkdownViewer
documentation: ug
---

# Loading Markdown Content in .NET WPF MarkdownViewer

The SfMarkdownViewer control supports flexible input sources, allowing developers to load Markdown content from strings, local files, embedded resources, and external URLs.

## From String

Assign a Markdown-formatted string to the Source property of the SfMarkdownViewer control to render markdown content directly within your application.

{% tabs %} 
{% highlight xaml %}

<Grid>
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
The MarkdownViewer control is used to render and preview Markdown files. It converts markdown syntax into a clean, readable format and supports elements such as headings, lists, code blocks, tables, and other common markdown structures.

# Header 1  
Used for the main title or top-level heading in a Markdown document. 

## Header 2  
Used to define major sections within your Markdown content.";
        
        public MainWindow()
        {
            InitializeComponent();  
            SfMarkdownViewer markdownViewer = new SfMarkdownViewer();
            markdownViewer.Source = markdownContent;
            HomeGrid.Children.Add(markdownViewer);      
        }
    }   
}

{% endhighlight %}
{% endtabs %}

## From Local File

To load Markdown content from a local `.md` file, you can directly specify the file path and read its contents using standard file I/O and assign its content to the Source property of the SfMarkdownViewer.

Use the following code-behind to read the file and assign its content to the Markdown Viewer:

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
        HomeGrid.Children.Add(markdownViewer);  
    }
}

{% endhighlight %}

## From Embedded Resource

1. To load Markdown content from an embedded resource, place the `.md` file inside the `Resources` folder of your .NET MAUI project. 
2. Use asynchronous file access to read and assign the content to the [Source](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.MarkdownViewer.SfMarkdownViewer.html#Syncfusion_Maui_MarkdownViewer_SfMarkdownViewer_Source) property of the [SfMarkdownViewer](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.MarkdownViewer.SfMarkdownViewer.html) control.

Refer to the following code-behind to read the embedded resource and assign its content to the Markdown Viewer:

**C#**

{% highlight C# %}

public partial class MainWindow : Window
{
    SfMarkdownViewer markdownViewer;
    public MainWindow()
    {
        InitializeComponent();
        markdownViewer = new SfMarkdownViewer();
        _ = LoadMarkdownAsync();
        HomeGrid.Children.Add(markdownViewer);
    }
    private async Task LoadMarkdownAsync()
    {
        Stream stream = null;
        StreamReader reader = null;
        try
        {
            // Adjust the path as needed (see loading options below)
            // or for file on disk:
            stream = File.OpenRead("D:\\SB\\markdownViewer Sample\\MarkdownContent.md");

            if (stream == null)
            {
                // Handle missing file
                return;
            }

            reader = new StreamReader(stream, Encoding.UTF8);
            string markdownContent = await reader.ReadToEndAsync();

            markdownViewer.Source = markdownContent;
        }
        finally
        {
            reader?.Dispose();
            stream?.Dispose();
        }
    }
}

{% endhighlight %}

## From URL

Markdown content can be loaded directly from a publicly accessible URL. This is useful for displaying remote documentation, release notes, or any Markdown file hosted online.

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
        HomeGrid.Children.Add(markdownViewer);       
    }
} 

{% endhighlight %}
{% endtabs %}
