---
title: Clipboard in WPF RichTextBox control | Syncfusion
description: Learn here all about Clipboard support in Syncfusion WPF RichTextBox (SfRichTextBoxAdv) control and more.
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: clipboard
---
# Clipboard in WPF RichTextBox (SfRichTextBoxAdv)

The SfRichTextBoxAdv takes advantage of the clipboard support and allows you to copy or paste contents to and from the clipboard in the following formats.

* Rich text format.

* Text.

* Image.

## UI Command to access clipboard operations


The following code example demonstrates how to bind commands for accessing clipboard operations.
{% tabs %}
{% highlight xaml %}
<!-- Binds button to the CutCommand -->
<Button Content="Cut" Command="RichTextBoxAdv:SfRichTextBoxAdv.CutCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the CopyCommand -->
<Button Content="Copy" Command="RichTextBoxAdv:SfRichTextBoxAdv.CopyCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the PasteCommand -->
<Button Content="Paste" Command="RichTextBoxAdv:SfRichTextBoxAdv.PasteCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />


{% endhighlight %}

{% endtabs %}
N> In order to cut, copy or paste, the standard keyboard shortcuts such as CTRL + X, CTRL + C, CTRL + V can also be used.
You can refer to our [WPF RichTextBox](https://www.syncfusion.com/wpf-controls/richtextbox) feature tour page for its groundbreaking feature representations.You can also explore our [WPF RichTextBox example](https://github.com/syncfusion/wpf-demos/tree/master/richtextbox) to knows how to render and configure the editing tools.
