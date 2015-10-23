---
layout: post
title: Binding-rich-text-format-option-of-RichTextBoxAdv
description: binding rich text format option of richtextboxadv 
platform: wpf
control: RichTextBoxAdv
documentation: ug
---

# Bind rich text format option of the RichTextBoxAdv 

The **RichTextBoxAdv** provides support to bind the rich-text format options of the selected content. The following rich-text format binding are supported by the **RichTextBoxAdv** control: 

* CharacterFormat - bold, italic, font size, font family, font color, highlight color, underline, strikethrough, subscript, and superscript.
* ParagraphFormat - before and after spacing, first line, left and right indenting, text justification, line spacing, and multilevel list.

The following code example demonstrates how to bind the bold format option of the **RichTextBoxAdv**. 

{% highlight html %}

<ToggleButton x:Name="toggleButton" Content="Bold" IsChecked="{Binding Path=Selection.CharacterFormat.Bold, Mode=TwoWay, ElementName=richTextBoxAdv}" />

{% endhighlight %}


{% highlight c# %}

//Initializes the new binding for the toggle bold.

Binding binding = new Binding(){ Source = richTextBoxAdv, Path = new PropertyPath("Selection.CharacterFormat.Bold"), Mode = BindingMode.TwoWay };

//Binds the IsChecked property to Selection.CharacterFormat.Bold property of the RichTextBoxAdv.

toggleButton.SetBinding(ToggleButton.IsCheckedProperty, binding);

{% endhighlight %}