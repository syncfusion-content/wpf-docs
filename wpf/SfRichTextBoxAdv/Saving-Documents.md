---
layout: Post
title: Saving-Documents
description: saving documents
platform: wpf
control: RichTextBoxAdv
documentation: ug
---
### Save Documents

The **RichTextBoxAdv** control supports to save rich-text content to rich-text format (.rtf) files, Word documents (.doc, .docx), Html documents (.htm, .html), Xaml files (.xaml) and text files (.txt). The following code example demonstrates how to save the contents of the **RichTextBoxAdv** control.

{% highlight c# %}
//Initializes the new SfRichTextBoxAdv control.

SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();

//Saves the file to the specified location in Synchronous mode.

string filePath = "D:/SampleDocument.docx";

richTextBoxAdv.Save(filePath);

//Saves the stream in Synchronous mode.

richTextBoxAdv.Save(stream, formatType);

//Saves the file to the specified location in Asynchronous mode.

Task<bool> saveTask = richTextBoxAdv.SaveAsync(filePath);

//Saves the stream in Asynchronous mode.

Task<bool> saveTask = richTextBoxAdv.SaveAsync(stream, formatType);



{% endhighlight %}


<table>
<tr>
<th>
**Overload** **methods******<br/><br/></th><th>
**Return** **Type******<br/><br/></th><th>
**Description** ****<br/><br/></th></tr>
<tr>
<th>
Save(string filePath)<br/><br/></th><th>
void<br/><br/></th><th>
Saves the content of the **RichTextBoxAdv** control as rich-text format (.rtf) files, Word documents (.doc, .docx) , Html documents (.htm, .html), Xaml files (.xaml) and text files (.txt) into a StorageFile in synchronous mode.<br/><br/></th></tr>
<tr>
<th>
Save(Stream stream, FormatType formatType)<br/><br/></th><th>
void<br/><br/></th><th>
Saves the content of the **RichTextBoxAdv** as rich-text format (.rtf) files, Word documents (.doc, .docx) , Html documents (.htm, .html), Xaml files (.xaml) and text files (.txt) into a Stream in synchronous mode.<br/><br/></th></tr>
<tr>
<th>
SaveAsync(string filePath)<br/><br/></th><th>
Task<bool><br/><br/></th><th>
Saves the content of the **RichTextBoxAdv** as rich-text format (.rtf) files, Word documents (.doc, .docx) , Html documents (.htm, .html), Xaml files (.xaml) and text files (.txt) into a file in the specified location in asynchronous mode. It also keeps the UI responsive during saving.<br/><br/></th></tr>
<tr>
<th>
SaveAsync(Stream stream, FormatType formatType)<br/><br/></th><th>
Task<bool><br/><br/></th><th>
Saves the content of the **RichTextBoxAdv** as rich-text format (.rtf) files, Word documents (.doc, .docx) , Html documents (.htm, .html), Xaml files (.xaml) and text files (.txt) into a Stream in asynchronous mode. It also keeps the UI responsive during saving.<br/><br/></th></tr>
</table>