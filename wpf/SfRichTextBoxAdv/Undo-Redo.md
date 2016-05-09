---
title: Undo Redo
description: undo-redo
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: undo-redo
---
# Undo Redo

The SfRichTextBoxAdv provides history preservation support, which means each editing operation performed against its document content will be preserved in history. You can easily undo any editing action with ease. The undone actions will also be preserved in a separate stack enabling you to redo the action again.

N> Currently, the number of actions that can be preserved in both undo and redo stacks is limited to 500.

## UI Command to perform undo/redo operations

The following code example demonstrates how to bind commands for performing undo and redo operations.
{% tabs %}
{% highlight xaml %}
<!-- Binds button to the UndoCommand -->
<Button Content="Undo" Command="RichTextBoxAdv:SfRichTextBoxAdv.UndoCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the RedoCommand -->
<Button Content="Redo" Command="RichTextBoxAdv:SfRichTextBoxAdv.RedoCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />


{% endhighlight %}

{% endtabs %}

N> In order to perform undo/redo, the standard keyboard shortcuts such as CTRL + Z, CTRL + Y can also be used.
