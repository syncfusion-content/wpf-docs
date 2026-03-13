---
layout: post
title: Mermaid Diagrams in WPF Markdown Viewer (SfMarkdownViewer) | Syncfusion
description: Learn here all about Mermaid Diagrams in Syncfusion MarkdownViewer control, its elements and more details.
platform: wpf
control: SfMarkdownViewer
documentation: ug
---

## Mermaid Diagrams in WPF Markdown Viewer
 
The SfMarkdownViewer control provides built-in support for rendering Mermaid diagrams and flowcharts within Markdown content. Mermaid is a JavaScript-based diagramming and charting tool that uses text-based definitions to create and modify diagrams dynamically.
 
## MermaidBlockTemplate Property
 
The `MermaidBlockTemplate` property accepts a `DataTemplate` that defines how Mermaid code blocks should be rendered. When a code block with the language identifier `mermaid` is encountered, the control uses this template instead of the default code block rendering.

{% tabs %} 
{% highlight xaml %}

    <Grid>
        <Grid.Resources>
            <DataTemplate x:Key="MermaidBlockTemplate">
                <StackPanel>
                    <syncDiagram:SfDiagram x:Name="mermaidDiagram" Foreground="Black"
                                 Height="600" Width="1000" Focusable="False"
                                 HorizontalAlignment="Left" 
                                 HorizontalContentAlignment="Left"
                                 Loaded="mermaidDiagram_Loaded">
                    </syncDiagram:SfDiagram>

                </StackPanel>

            </DataTemplate>
        </Grid.Resources>

        <syncfusion:SfMarkdownViewer MermaidBlockTemplate="{StaticResource MermaidBlockTemplate}">
            <syncfusion:SfMarkdownViewer.Source>
                <system:String xml:space="preserve">
                    <![CDATA[

# 📘 What is MarkdownViewer?

MarkdownViewer is a UI component that displays **Markdown (.md) content** inside an application.
It converts Markdown syntax into formatted text, headings, tables, code blocks, diagrams, and more.

MarkdownViewer is commonly used in:
- Documentation panels  
- Help/Info screens  
- Developer tools  
- In‑app editors  
- Sample or demo UI screens  

It provides a clean and readable way to show technical or formatted content without HTML.

---

# MarkdownViewer – Advanced Features Demo

This sample shows advanced formatting features often supported in enhanced MarkdownViewer controls.

---

## 1) Superscript

Superscript is commonly used for math, chemistry, and footnotes.

Example:

- E = mc<sup>2</sup> 
- X<sup>10</sup> + Y<sup>2</sup>  
- Trademark™ can be written as TM<sup>®</sup>

## 2) Subscript

Subscript is used in scientific formulas, chemical expressions, and indexing.

Examples:

- H<sub>2</sub>O (Water)  
- CO<sub>2</sub> (Carbon dioxide)  
- Variable a<sub>2</sub>, a<sub>2</sub>, a<sub>3</sub> for indexing
                        
---

## 3) Blockquotes

Blockquotes visually highlight notes, messages, or documentation hints.

###### Example:
> This is a standard blockquote.  
> Useful for warnings, info notes, and documentation messages.

###### Nested blockquote:
> This is level1 blockquote.  
>> This is level2 blockquote.
>>> This is level3 blockquote.

---

## 4) Code Blocks (Fenced)

Code blocks are used for samples, configuration, and developer snippets.

Example (C++):

```
#include <iostream>
#include <string>

int main() {
    std::string user = "MarkdownViewer";
    std::cout << "Hello from " << user << "! Rendering works perfectly." << std::endl;

    // Demonstrate a small loop
    for (int i = 1; i <= 3; ++i) {
        std::cout << "Test run #" << i << " OK" << std::endl;
    }

    return 0;
}
```
<br>

### ✔ Mermaid Diagrams
Allows embedding diagrams such as flowcharts, sequence diagrams, and org charts.

---

# 🐬 What is Mermaid?

**Mermaid** is a text‑based diagramming language that allows you to create charts and diagrams directly inside Markdown.

It is widely used for:
- Flowcharts  
- Sequence diagrams  
- Gantt charts  
- Class diagrams  
- State diagrams  
- Pie charts  
- Entity‑relationship diagrams  

You define diagrams using simple text, and the renderer draws them.

# 🔁 Mermaid Flowchart Example

Below is a Mermaid flowchart you can use to test your MarkdownViewer:

```mermaid
flowchart TD
    A[User Opens App] --> B[MarkdownViewer Loads]
    B --> C{Contains Mermaid?}
    C -->|Yes| D[Render Diagram]
    C -->|No| E[Render Plain Markdown]
    D --> F[Display Enhanced Output]
    E --> F
            ]]>
                </system:String>
            </syncfusion:SfMarkdownViewer.Source>
        </syncfusion:SfMarkdownViewer>

    </Grid>

{% endhighlight %}

{% highlight C# %}

namespace MarkdownViewerGettingStarted
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }

        private void mermaidDiagram_Loaded(object sender, RoutedEventArgs e)
        {
            if (sender is Syncfusion.UI.Xaml.Diagram.SfDiagram diagram)
            {
                diagram.PageSettings = null;
                diagram.ScrollSettings.ScrollLimit = ScrollLimit.Limited;
                var mermaidText = diagram.DataContext as string;
                diagram.LayoutManager = new LayoutManager
                {
                    Layout = new FlowchartLayout
                    {
                        Orientation = FlowchartOrientation.TopToBottom,
                        HorizontalSpacing = 80,
                        VerticalSpacing = 60,
                        Margin = new Thickness(-200, 50, 0, 0),
                    }
                };

                diagram.LoadDiagramFromMermaid(mermaidText);
            }
        }
    }
}

{% endhighlight %}
{% endtabs %}

![Mermaid Diagrams in WPF Markdown Viewer](Images/wpf-markdown-mermaid-block.gif)
