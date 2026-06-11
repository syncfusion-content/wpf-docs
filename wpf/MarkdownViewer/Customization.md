---
layout: post
title: Customize WPF MarkdownViewer Appearance | Syncfusion
description: Learn how to customize the appearance and behavior of the Syncfusion® WPF SfMarkdownViewer control, including styling elements and modifying themes.
platform: wpf
control: SfMarkdownViewer
documentation: ug
---

# Customize Appearance in WPF SfMarkdownViewer

The `SfMarkdownViewer` control in Wpf provides a flexible styling system through the `MarkdownStyleSettings` class. This allows developers to customize the appearance of Markdown elements such as headings, paragraphs, lists, and more to match application themes and branding.

## Style settings for SfMarkdownViewer

The `MarkdownStyleSettings` class provides style customization for different Markdown elements through the following properties:

- `ParagraphStyle` – Defines the style for paragraph text.  
- `H1Style` to `H6Style` – Defines styles for heading levels.  
- `ListStyle` – Applies to ordered and unordered lists.  
- `TableStyle` – Applies to tables, including headers and rows.  
- `BlockQuoteStyle` – Used for block-level quotes.  
- `InlineQuoteStyle` – Used for inline quoted text.  
- `ThematicStyle` – Used for horizontal rules.  
- `LinkStyle` – Defines hyperlink appearance.  
- `CodeBlockStyle` – Applies to code blocks.  
- `MermaidStyle` – Applies to Mermaid diagram rendering.  

You can apply these custom styles by assigning a `MarkdownStyleSettings` instance to the `Settings` property of `SfMarkdownViewer`, as shown in the following code example.

{% tabs %} 
{% highlight xaml %}

<Grid>
    <syncfusion:SfMarkdownViewer x:Name="markdownviewer">
        <syncfusion:SfMarkdownViewer.Source>
            <x:String xml:space="preserve">
              <![CDATA[

# What is the Markdown Viewer ?
                        
The Markdown Viewer is a UI control in Wpf that allows developers to render Markdown content with full formatting support. It was designed to work efficiently on both mobile and desktop platforms. The viewer supports headings, bold and italic text, lists, tables, images, code blocks and more.                        

# Header 1
                        
Used for the Main title or top-level heading in a Markdown document.

## Header 2
                        
Used to define major sections within your Markdown content. 

![Syncfusion Wpf Markdown Viewer](Images/wpf-markdown-viewer-customization.WEBP)

              ]]>
            </x:String>
        </syncfusion:SfMarkdownViewer.Source>
        <markdown:SfMarkdownViewer.Settings>
            <markdown:MarkdownStyleSettings>
                <markdown:MarkdownStyleSettings.H1Style>
                    <markdown:HeaderSettings FontStyle="Normal" FontSize="50" Foreground="MediumPurple" />
                </markdown:MarkdownStyleSettings.H1Style>
                <markdown:MarkdownStyleSettings.H2Style>
                    <markdown:HeaderSettings FontStyle="Normal" FontSize="50" Foreground="MediumPurple" />
                </markdown:MarkdownStyleSettings.H2Style>
                <markdown:MarkdownStyleSettings.ParagraphStyle>
                    <markdown:ParagraphSettings FontStyle="Italic" FontSize="15" />
                </markdown:MarkdownStyleSettings.ParagraphStyle>
            </markdown:MarkdownStyleSettings>
        </markdown:SfMarkdownViewer.Settings>
    </syncfusion:SfMarkdownViewer>
</Grid>

{% endhighlight %}

{% highlight C# %}

    public sealed partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
            SfMarkdownViewer markdownViewer = new SfMarkdownViewer();
            markdownViewer.Source =
@"
# What is the Markdown Viewer ?
                        
The Markdown Viewer is a UI control in Wpf that allows developers to render Markdown content with full formatting support. It was designed to work efficiently on both mobile and desktop platforms. The viewer supports headings, bold and italic text, lists, tables, images, code blocks and more.                        

# Header 1
                        
Used for the Main title or top-level heading in a Markdown document.

## Header 2
                        
Used to define major sections within your Markdown content. 

![Syncfusion Wpf Markdown Viewer](Images/wpf-markdown-viewer-customization.WEBP)

            markdownViewer.Settings = new MarkdownStyleSettings
            {
                H1Style = new HeaderSettings
                {
                    FontSize = 50,
                    Foreground = new SolidColorBrush(Microsoft.UI.Colors.MediumPurple),
                    FontStyle = FontStyle.Normal,
                },
                H2Style = new HeaderSettings
                {
                    FontSize = 50,
                    Foreground = new SolidColorBrush(Microsoft.UI.Colors.MediumPurple),
                    FontStyle = FontStyle.Normal,
                },
                ParagraphStyle = new ParagraphSettings
                {
                    FontStyle = FontStyle.Italic,
                    FontSize = 15,
                },
            };
            Content = markdownViewer;
        }
    }

{% endhighlight %}
{% endtabs %}

The following image shows the rendered output with customized heading and paragraph styles:
![Syncfusion Wpf Markdown Viewer](Images/wpf-markdown-viewer-customization.WEBP)

N> Changing values dynamically in Theme studio settings isn't supported.
