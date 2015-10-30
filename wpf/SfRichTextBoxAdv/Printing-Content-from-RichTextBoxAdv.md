---
layout: Post
title: Printing-Content-from-RichTextBoxAdv
description: printing content from richTextBoxAdv
platform: wpf
control: RichTextBoxAdv
documentation: ug
---
### Print Content from the RichTextBoxAdv

The **RichTextBoxAdv** control supports page-by-page printing of rich-text content that is rendered in the editor. The following code example demonstrates how to print the contents of the **RichTextBoxAdv** control.

{% highlight c# %}
//Initializes the new SfRichTextBoxAdv control.

SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();

//Specifies the path of Sample.docx file.

string filePath = "D:/Sample.docx";

//Loads the file from the specified path in the Synchronous mode.

richTextBoxAdv.Load(filePath);

//Prints the content of the RichTextBoxAdv.

richTextBoxAdv.PrintDocument();



{% endhighlight %}

