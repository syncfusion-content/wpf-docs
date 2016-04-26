---
title: Dialogs
description: dialogs
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: dialogs
---
# Dialogs

The SfRichTextBoxAdv provides support for the following built-in dialogs similar to Microsoft Word application.

* Font Dialog

* Paragraph Dialog

* List Dialog

* Insert Table Dialog

* Insert Hyperlink Dialog

* Find and Replace Dialog

* Password Dialog


## UI Commands for accessing dialogs

The following code example demonstrates how to show the built-in dialogs in SfRichTextBoxAdv through command binding.
{% tabs %}
{% highlight xaml %}
<!-- Binds button to the ShowFontDialogCommand -->
<Button Content="Font" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowFontDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the ShowParagraphDialogCommand -->
<Button Content="Paragraph" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowParagraphDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the ShowListDialogCommand -->
<Button Content="List" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowListDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the ShowInsertTableDialogCommand -->
<Button Content="Insert Table" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowInsertTableDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the ShowHyperlinkDialogCommand -->
<Button Content="Hyperlink" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowHyperlinkDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the ShowFindAndReplaceDialogCommand -->
<Button Content="Find and Replace" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowFindAndReplaceDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the ShowEncryptDocumentDialogCommand -->
<Button Content="Encrypt Document" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowEncryptDocumentDialogCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />


{% endhighlight %}

{% endtabs %}
