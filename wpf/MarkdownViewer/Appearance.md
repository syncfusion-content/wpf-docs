---
layout: post
title: Customize Appearance in .NET WPF MarkdownViewer | Syncfusion
description: Learn how to style and customize the appearance of Markdown content using the MarkdownStyleSettings class in the Syncfusion .NET WPF MarkdownViewer control.
platform: wpf
control: SfMarkdownViewer
documentation: ug
---

# Customize Appearance in .NET WPF SfMarkdownViewer

The SfMarkdownViewer control in .NET WPF provides a powerful styling system through the MarkdownStyleSettings class. This allows developers to customize the visual presentation of Markdown content with precision and flexibility.

## Key Feature

- **Granular Styling**: Customize font sizes and colors for headings, body text, and tables.

## Use Cases

- Match Markdown content appearance with your app’s theme.
- Improve readability with tailored font sizes and spacing.
- Highlight specific Markdown elements like tables or code blocks.

## Customization with MarkdownStyleSettings

The appearance of headings and body content in SfMarkdownViewer can be customized using the MarkdownStyleSettings class.

- H1FontSize, H2FontSize, H3FontSize – Gets or sets the font size for H1, H2, and H3 heading elements respectively.  
- H1Foreground, H2Foreground, H3Foreground – Gets or sets the text color for H1, H2, and H3 heading elements respectively.  
- ParagraphFontSize – Gets or sets the font size for regular paragraph text. 
- ParagraphForeground – Gets or sets the text color for paragraph content.
- TableBackground – Gets or sets the background color for the entire table area.

{% highlight xaml %}

    <Window>
        . . .
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
                

### Table
                    
                    
 |              | Column 1 | Column 2 | Column 3 |
|--------------|----------|----------|----------|
| Row 1        | Content  | Content  | Content  |
| Row 2        | Content  | Content  | Content  |
| Row 3        | Content  | Content  | Content  |
 
---
            ]]>

                </system:String>
            </markdown:SfMarkdownViewer.Source>
            <markdown:SfMarkdownViewer.Settings>
                <markdown:MarkdownStyleSettings>
                    <markdown:MarkdownStyleSettings.ParagraphStyle>
                        <markdown:ParagraphSettings FontStyle="Italic" FontSize="16" Foreground="#2C3E50"/>
                    </markdown:MarkdownStyleSettings.ParagraphStyle>
                    <markdown:MarkdownStyleSettings.H1Style>
                        <markdown:HeaderSettings FontStyle="Normal" Foreground="#8352FB" FontSize="32"></markdown:HeaderSettings>
                    </markdown:MarkdownStyleSettings.H1Style>
                    <markdown:MarkdownStyleSettings.H2Style>
                        <markdown:HeaderSettings FontStyle="Normal" Foreground="#9971FB"></markdown:HeaderSettings>
                    </markdown:MarkdownStyleSettings.H2Style>
                    <markdown:MarkdownStyleSettings.H3Style>
                        <markdown:HeaderSettings FontStyle="Normal" Foreground="#A98AF7"></markdown:HeaderSettings>
                    </markdown:MarkdownStyleSettings.H3Style>
                    <markdown:MarkdownStyleSettings.TableStyle>
                        <markdown:TableSettings Background="#FFE2ED" />
                    </markdown:MarkdownStyleSettings.TableStyle>
                </markdown:MarkdownStyleSettings>
            </markdown:SfMarkdownViewer.Settings>
        </markdown:SfMarkdownViewer>
        . . .
    </Window>

{% endhighlight %}

The following output shows how these style settings enhance the appearance of rendered Markdown content:

![Sample markdown content appearance customization](images/wpf-markdown-viewer-appearance.png)

With MarkdownStyleSettings, you gain full control over how Markdown content looks in your .NET WPF app, whether you're building a documentation viewer, a note-taking app, or a styled content portal.
