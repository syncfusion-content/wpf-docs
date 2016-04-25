---
title: Commands
description: commands
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: commands
---
# Commands

Commands are a way to handle user interface (UI) actions. They are a loosely coupled way to bind the UI to the logic that performs the action. The SfRichTextBoxAdv supports commands for mostly used operations which are classified below.
* Character Formatting – Bold, Italic, Underline, Strike through, Baseline alignment, Font family, Font size, Font color and Highlight color.

* Paragraph Formatting – Left indent, Right indent, First line indent, Text alignment, Before spacing, After spacing, Line spacing, Line spacing type, Increase indent, Decrease indent and Change list type.

* Clipboard – Cut, Copy and Paste.

* History – Undo and Redo.

* Import and Export – Open document, Save document and New document.

* Comments – New comment, Delete comment, Delete all comments, Previous comment, Next comment and Show comments.

* Table – Insert table, Insert row, Insert column, Delete table, Delete row, Delete column and Merge selected cells.

* UI options – Show hyperlink dialog, Show options pane and Layout type.

* Insert – Insert picture and Insert hyperlink.

## UI Command to access character formatting


The following code example demonstrates how to bind commands for applying character format.
{% tabs %}
{% highlight xml %}
<!-- Binds button to the BoldCommand -->
<Button Content="Bold" Command="RichTextBoxAdv:SfRichTextBoxAdv.BoldCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}"/>
<!-- Binds button to the ItalicCommand -->
<Button Content="Italic" Command="RichTextBoxAdv:SfRichTextBoxAdv.ItalicCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}"/>


{% endhighlight %}

{% endtabs %}
