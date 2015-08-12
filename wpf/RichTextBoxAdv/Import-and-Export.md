---
layout: post
title: Import-and-Export
description:  import and export
platform: wpf
control: RichTextBoxAdv
documentation: ug
---

#  Import and Export

This feature lets you use several file formats, namely .doc, .docx, .html, .xaml, and .txt, inside the RichTextBoxAdv control. Using any one format allows the use of the other formats.

##  HTML Import/Export

The HTML import feature allows the user to import an .html file into the RichTextBoxAdv. It renders the HTML tags like a browser and displays the text in the format of RichTextBoxAdv’s content model. The HTML export feature actually exposes the RichTextBoxAdv’s document as an .html file. The following methods clearly show this use case.



{% highlight C# %}

 DocumentAdv doucment = HTMLImporting.ConvertToDocumentAdv(stream);  
 DocumentAdv document = HTMLImporting.ConvertToDocumentAdv(htmlstring);
 
{% endhighlight %}

{% highlight C# %}

string html = HTMLExporting.ConvertToHtml(RichTextBox.Document, stream);

{% endhighlight %}


### Methods



Methods Table

<table>
<tr>
<th>
Method</th><th>
Description</th><th>
Parameters</th><th>
Type</th><th>
Return Type</th></tr>
<tr>
<td>
ConvertToDocumentAdv()</td><td>
Converts htmlstream into DocumentAdv.</td><td>
(Stream stream)(string htmlstring)</td><td>
NA</td><td>
DocumentAdv</td></tr>
<tr>
<td>
ConvertToHtml()</td><td>
Converts the DocumentAdv to an HTML string.</td><td>
NA</td><td>
NA</td><td>
String</td></tr>
</table>


###  Limitations

The HTML import/export feature has the following limitations:

1. Script support has not been provided.
2. It does not provide support for tables.



##  Doc Import/Export and Docx Import/Export

This feature allows you to open and save the Word Doc and Docx format (.doc, .docx) documents, and to view, edit, and print the contents by using the RichTextBoxAdv control.

The following assembly references are required to use this feature and its namespace.

#### WPF 3.5 and 4.0 framework:

* Assembly: Syncfusion.RichTextDocIOParser.Wpf
* Dependent Assemblies: Syncfusion.Compression.Base, Syncfusion.Core, Syncfusion.DocIO.ClientProfile, Syncfusion.RichTextBoxAdv.Wpf, and Syncfusion.Shared.Wpf
* Namespace: Syncfusion.Windows.Tools.Controls



#### WPF 4.5 and 4.5.1 framework:

* Assembly: Syncfusion.RichTextDocIOParser. Wpf
* Dependent Assemblies: Syncfusion.Compression.Base, Syncfusion.Core, Syncfusion.DocIO.Base, Syncfusion.RichTextBoxAdv.Wpf, and Syncfusion.Shared.Wpf
* Namespace: Syncfusion.Windows.Tools.Controls



#### Silverlight platform:

* Assembly: Syncfusion.RichTextDocIOParser.Silverlight
* Dependent Assemblies: Syncfusion.Compression.Silverlight, Syncfusion.DocIO.Silverlight, Syncfusion.RichTextBoxAdv.Silverlight, and Syncfusion.Shared.Silverlight
* Namespace: Syncfusion.Windows.Tools.Controls



#### Doc and Docx Import

You can convert the Word document stream to RichTextBoxAdv document by invoking the ConvertToDocumentAdv method from the extension class DocxImporting. 

ConvertToDocumentAdv Method

<table>
<tr>
<th>
Method</th><th>
Return Type</th><th>
Parameters</th><th>
Description</th></tr>
<tr>
<td>
ConvertToDocumentAdv</td><td>
DocumentAdv</td><td>

1. Stream documentStream2. String documentExtension (.doc, .docx)</td><td>
Converts the Word document stream to DocumentAdv instance.</td></tr>
</table>

{% highlight C# %}

//Initializes the new RichTextBoxAdv control.

RichTextBoxAdv richTextBoxAdv = new RichTextBoxAdv();

//Loads the Doc format document in RichTextBoxAdv control from document stream.

richTextBoxAdv.Document = DocxImporting.ConvertToDocumentAdv(documentStream, ".doc");

//Loads the Docx format document in RichTextBoxAdv control from document stream.

richTextBoxAdv.Document = DocxImporting.ConvertToDocumentAdv(documentStream, ".docx");

{% endhighlight %}

{% highlight vbnet %}

'Initializes the new RichTextBoxAdv control.

Dim richTextBoxAdv As New RichTextBoxAdv()

'Loads the Doc format document in RichTextBoxAdv control from document stream.

richTextBoxAdv.Document = DocxImporting.ConvertToDocumentAdv(documentStream, ".doc")

'Loads the Docx format document in RichTextBoxAdv control from document stream.

richTextBoxAdv.Document = DocxImporting.ConvertToDocumentAdv(documentStream, ".docx")
{% endhighlight %}


### Doc and Docx Export

You can convert the RichTextBoxAdv document to Word document stream by invoking the ConvertToDocument method from the extension class DocxExporting. 

ConvertToDocument Method

<table>
<tr>
<th>
Method</th><th>
Return Type</th><th>
Parameters</th><th>
Description</th></tr>
<tr>
<td>
ConvertToDocument</td><td>
void</td><td>
1. DocumentAdv documentadv 2. Stream documentStream3. String documentExtension (.doc, .docx)</td><td>
Converts the DocumentAdv instance to Word document stream.</td></tr>
</table>

{% highlight C# %}

//Saves the RichTextBoxAdv document to Word Doc format document stream.

DocxExporting.ConvertToDocument(richTextBoxAdv.Document, documentStream, ".doc");

//Saves the RichTextBoxAdv document to Word Docx format document stream.

DocxExporting.ConvertToDocument(richTextBoxAdv.Document, documentStream, ".docx");

{% endhighlight %}

{% highlight vbnet %}

'Saves the RichTextBoxAdv document to Word Doc format document stream.

DocxExporting.ConvertToDocument(richTextBoxAdv.Document, documentStream, ".doc")

'Saves the RichTextBoxAdv document to Word Docx format document stream.

DocxExporting.ConvertToDocument(richTextBoxAdv.Document, documentStream, ".docx")

{% endhighlight %}

###  Limitations

The .doc import/export and .docx import/export features have the following limitations:

1. Hyperlinks do not work for tables of contents.

##  XAML Import/Export


The XAML import feature allows users to import a .xaml file into the RichTextBoxAdv. It renders the XAML elements as XamlReader and displays the text in the format of RichTextBoxAdv’s content model. The XAML export feature actually exposes the RichTextBoxAdv’s document as a .xaml file. The following methods clearly show this use case.

{% highlight C# %}

RichTextBox.Document=XAMLImporting.ConvertToDocumentAdv(xamlStream)

{% endhighlight %}

{% highlight C# %}

string xaml = XAMLExporting.ConvertToXAML(RichTextBox.Document, xamlstream);

{% endhighlight %}

Methods



_Methods table_

<table>
<tr>
<th>
Method</th><th>
Description</th><th>
Parameters</th><th>
Type</th><th>
Return Type</th></tr>
<tr>
<td>
ConvertToDocumentAdv()</td><td>
It converts XAML stream into DocumentAdv.</td><td>
NA</td><td>
NA</td><td>
DocumentAdv</td></tr>
<tr>
<td>
ConvertToXaml()</td><td>
It returns the RichText content as XAML.</td><td>
NA</td><td>
NA</td><td>
Void</td></tr>
</table>


## Text Import/Export

The text import feature allows the user to import a .txt file into the RichTextBoxAdv. It renders the text in Notepad format and displays the text in the format of RichTextBoxAdv’s content model. The text export feature actually exposes the RichTextBoxAdv’s document as a .txt file. The following methods clearly show this usage.


{% highlight C# %}

RichTextBox.Document = TextImporting.ConvertToDocumentAdv(textstream);

{% endhighlight %}

{% highlight C# %}

string txtstring= TextExporting.ConvertToText(RichTextBox.Document, textStream);

{% endhighlight %}


Methods

_Methods table_

<table>
<tr>
<th>
Method</th><th>
Description</th><th>
Parameters</th><th>
Type</th><th>
Return Type</th></tr>
<tr>
<td>
ConvertToDocumentAdv()</td><td>
Converts text stream into DocumentAdv.</td><td>
NA</td><td>
NA</td><td>
DocumentAdv</td></tr>
<tr>
<td>
ConvertText()</td><td>
Returns the rich-text content as a text file.</td><td>
NA</td><td>
NA</td><td>
String</td></tr>
</table>


