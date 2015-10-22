---
layout: Post
title: Loading-Documents
description: loading documents
platform: wpf
control: RichTextBoxAdv
documentation: ug
---
### Loading Documents

The **RichTextBoxAdv** provides support to load rich-text format (.rtf) files, Word documents (.doc, .docx), Html documents (.htm, .html), Xaml files (.xaml) and text files (.txt) for viewing and editing formatted rich-text content. The following code sample demonstrates how to load .rtf files, .doc or .docx files, .htm or .html files, .xaml files and .txt files in the **RichTextBoxAdv** control.

{% highlight c# %}
//Initializes the new SfRichTextBoxAdv control.

SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();

//Loads the file from the specified path in Synchronous mode.

string filePath = "D:/Sample.docx";

richTextBoxAdv.Load(filePath);

//Loads the stream in Synchronous mode.

richTextBoxAdv.Load(stream, formatType);

//Loads the file from the specified path in Asynchronous mode.

string filePath = "D:/Sample.docx";

Task<bool> loadTask = richTextBoxAdv.LoadAsync(filePath);

//Loads the stream in Asynchronous mode.

Task<bool> loadTask = richTextBoxAdv.LoadAsync(stream, formatType);



{% endhighlight %}



<table>
<tr>
<th>
**Overload** **methods******<br/><br/></th><th>
**Return** **Type******<br/><br/></th><th>
**Description** ****<br/><br/></th></tr>
<tr>
<th>
Load(StorageFile storageFile)<br/><br/></th><th>
void<br/><br/></th><th>
Loads the contents of the rich-text format (.rtf) files, Word documents (.doc, .docx) , Html documents (.htm, .html), Xaml files (.xaml) and text files (.txt) passed as file location to the **RichTextBoxAdv** control in synchronous mode. When the file in the specified location doesn’t exist or if the file is not a .doc, .docx, .rtf, .htm, .html, .xaml or .txt file, it throws an exception.<br/><br/></th></tr>
<tr>
<th>
Load(Stream stream, FormatType formatType)<br/><br/></th><th>
void<br/><br/></th><th>
Loads the contents of rich-text format (.rtf) files, Word documents (.doc, .docx) , Html documents (.htm, .html), Xaml files (.xaml) and text files (.txt) passed as a Stream with the specified FormatType to the **RichTextBoxAdv** control in synchronous mode.<br/><br/></th></tr>
<tr>
<th>
LoadAsync(string filePath)<br/><br/></th><th>
Task<bool><br/><br/></th><th>
Loads the contents of rich-text format (.rtf) files, Word documents (.doc, .docx) , Html documents (.htm, .html), Xaml files (.xaml) and text files (.txt) passed as a StorageFile to the **RichTextBoxAdv** control in asynchronous mode. It also keeps the UI responsive during loading. When the file in the specified location doesn’t exist or if the file is not a .doc, .docx, .rtf, .htm, .html, .xaml or .txt file, it throws an exception.<br/><br/></th></tr>
<tr>
<th>
LoadAsync(Stream stream, FormatType formatType)<br/><br/></th><th>
Task<bool><br/><br/></th><th>
Loads the contents of rich-text format (.rtf) files, Word documents (.doc, .docx) , Html documents (.htm, .html), Xaml files (.xaml) and text files (.txt) passed as Stream with specified FormatType to **RichTextBoxAdv** in asynchronous mode. It also keeps the UI responsive during loading.<br/><br/></th></tr>
</table>
