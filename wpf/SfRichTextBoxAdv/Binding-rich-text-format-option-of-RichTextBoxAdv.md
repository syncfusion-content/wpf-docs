---
layout: post
title: Binding-rich-text-format-option-of-RichTextBoxAdv
description: binding rich text format option of richtextboxadv 
platform: wpf
control: RichTextBoxAdv
documentation: ug
---

# Binding rich text format option of RichTextBoxAdv 

The RichTextBoxAdv provides support to bind the rich-text format options of selection content. The following rich-text formats binding are supported by RichTextBoxAdv control: 

* CharacterFormat-bold, italic, font size, font family, font color, highlight color, underline, strikethrough, subscript, and superscript.
* ParagraphFormat-before and after spacing, first line, left and right indenting, text justification, line spacing, and multilevel list.

The following code sample demonstrates how to bind the bold format option of RichTextBoxAdv. 

{% highlight html %}

<ToggleButton x:Name="toggleButton" Content="Bold" IsChecked="{Binding Path=Selection.CharacterFormat.Bold, Mode=TwoWay, ElementName=richTextBoxAdv}" />

{% endhighlight %}


{% highlight c# %}

//Initializes the new binding for toggle bold.

Binding binding = new Binding(){ Source = richTextBoxAdv, Path = new PropertyPath("Selection.CharacterFormat.Bold"), Mode = BindingMode.TwoWay };

//Binds the IsChecked property to Selection.CharacterFormat.Bold property of RichTextBoxAdv.

toggleButton.SetBinding(ToggleButton.IsCheckedProperty, binding);

{% endhighlight %}