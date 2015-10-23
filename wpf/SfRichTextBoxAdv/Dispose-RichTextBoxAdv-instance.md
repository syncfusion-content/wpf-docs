---
layout: Post
title: Dispose-RichTextBoxAdv-instance
description: dispose richTextBoxAdv instance
platform: wpf
control: RichTextBoxAdv
documentation: ug
---
### Dispose the RichTextBoxAdv instance

The **RichTextBoxAdv** control keeps all the contents of a document in the main memory that consumes a considerable amount of memory based on the content. It is mandatory to release the resources used by the **RichTextBoxAdv** instance by using the **Dispose** method. Invoking this method, explicitly disposes the content and release the resources.

The following code example demonstrates how to dispose the **RichTextBoxAdv** instance.

{% highlight c# %}
//Initializes the new SfRichTextBoxAdv control.

SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();

//Specifies the path of the Sample.docx file.

string filePath = "D:/Sample.docx";

//Loads the file from the specified path in an Asynchronous mode.

richTextBoxAdv.LoadAsync(filePath);

//Disposes the RichTextBoxAdv instance.

richTextBoxAdv.Dispose();



{% endhighlight %}

