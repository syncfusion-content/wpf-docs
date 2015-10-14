---
layout: post
title: Merge-Documents
description: merge documents
platform: wpf
control: PDF
documentation: ug
---

# Merge Documents

Merging feature in the Essential PDF enables you in appending all documents to the target document. When merging, all bookmarks and attachments are copied.

There are various overloads of the Merge method that allow specifying different parameters. Some important parameters are:

* Array of strings 
* Array of PdfDocumentBase instances

You can also merge the documents in the following ways: 

* Append all the documents one after another by using the Append method.
* Import the pages from different documents by using the ImportPageRange or ImportPage method.

## Merging Multiple Documents from Disk


In this method, path of the source PDF files is provided in a string array. They are merged in the order of their appearance in the array. The following code example illustrates how to merge multiple documents.

{% highlight c# %}

//Creates a string array of source files, which are to be merged.

string[] source = { "Input.pdf", "Input1.pdf"};

//Merges PDF document.

PdfDocument document = PdfDocument.Merge(source);

//Saves and closes the document.

document.Save("Output.pdf");

document.Close(true);

{% endhighlight %}



{% highlight vbnet %}

'Creates a string array of source files, which are to be merged.

Dim source As String() = {"Input.pdf", "Input1.pdf"}

'Merges PDF document.

Dim document As PdfDocument = PdfDocument.Merge(source)

'Saves and closes the document.

document.Save("Output.pdf")

document.Close(True)

{% endhighlight %}


## Merging Multiple Documents from Stream

It is also possible to merge multiple PDF documents from stream using the static merge method of PdfDocument class. The following code example illustrates this. 



{% highlight c# %}

FileStream stream1 = new FileStream("Input.pdf", FileMode.Open);

FileStream stream2 = new FileStream("Input1.pdf", FileMode.Open);

//Creates stream array of source files, which is to be merged.

Stream[] source = { stream1, stream2 };

//Creates a new document.

PdfDocument document = new PdfDocument();

//Merges PDF document.

PdfDocument.Merge(document,source);

//Saves and closes the document.

document.Save("Output.pdf");

document.Close(true);

stream1.Dispose();

stream2.Dispose();

{% endhighlight %}



{% highlight vbnet %}

Dim stream1 As New FileStream("Input.pdf", FileMode.Open)

Dim stream2 As New FileStream("Input1.pdf", FileMode.Open)

'Creates stream array of source files, which are to be merged.

Dim source As Stream() = {stream1, stream2}

'Creates a new document.

Dim document As New PdfDocument()

'Merges PDF document.

PdfDocument.Merge(document, source)

'Saves and closes the document.

document.Save("Output.pdf")

document.Close(True)

stream1.Dispose()

stream2.Dispose()

{% endhighlight %}


## Merging Two Files using Append method

Two files can also be merged by appending one file after another using append method in the PdfDocumentBase class. The following code example illustrates this.



{% highlight c# %}

//Loads documents.

PdfLoadedDocument document1 = new PdfLoadedDocument("Input.pdf");

PdfLoadedDocument document2 = new PdfLoadedDocument("Input1.pdf");

//Appends documents.

document1.Append(document2);

//Saves document.

document1.Save("Output.pdf");

document1.Close(true);

document2.Close(true);

{% endhighlight %}



{% highlight vbnet %}

'Loads documents.

Dim document1 As New PdfLoadedDocument("Input.pdf")

Dim document2 As New PdfLoadedDocument("Input1.pdf")

'Appends documents.

document1.Append(document2)

'Saves document.

document1.Save("Merged.pdf")

document1.Close(True)

document2.Close(True)

{% endhighlight %}


## Merging pages of different Documents

Another way of merging is to import all the pages from one document to another using ImportPageRange method. The following code example illustrates this.



{% highlight c# %}

//Loads documents.

PdfLoadedDocument document1 = new PdfLoadedDocument("Input.pdf");

PdfLoadedDocument document2 = new PdfLoadedDocument("Input1.pdf");

//Imports all the pages to another document.

document1.ImportPageRange(document2, 0, document2.Pages.Count - 1);

//Saves document.

document1.Save("Merged.pdf");

document1.Close(true);

document2.Close(true);

{% endhighlight %}



{% highlight vbnet %}

'Loads documents.

Dim document1 As New PdfLoadedDocument("Input.pdf")

Dim document2 As New PdfLoadedDocument("Input1.pdf")

'Imports all the pages to another document.

document1.ImportPageRange(document2, 0, document2.Pages.Count - 1)

'Saves the document.

document1.Save("Merged.pdf")

document1.Close(True)

document2.Close(True)

{% endhighlight %}


## Best practices

Merging multiple large PDF documents can lead to high memory usage. To optimize memory usage, you can use the following code sample. First, parent PDF document needs to be created, loaded, and then import pages and its contents to the parent PDF document and dispose the loaded PDF document. Setting EnableMemoryOptimization to true also reduces the memory usage once the document instance is closed.

N> The PDF document (parent document) contents are still in run time memory. It releases the memory once the PDF document instance is disposed.



{% highlight c# %}

//Inputs PDF documents.

string[] inputDocuments = { "Input1.pdf", "Input2.pdf", "Input3.pdf", "Input4.pdf", "Input5.pdf", 

"Input6.pdf", "Input7.pdf", "Input8.pdf", "Input9.pdf", "Input10.pdf" };

//Creates a new instance. 

PdfDocument document = new PdfDocument();

//Optimizes memory while merging PDF documents.

document.EnableMemoryOptimization = true;

//Iterates input PDF documents.

foreach (string inputDocument in inputDocuments)

{

//Loads PDF document in order to merge.

PdfLoadedDocument loadedDocument = new PdfLoadedDocument(inputDocument);

loadedDocument.EnableMemoryOptimization = true;

//Merges loaded document contents to the parent PDF document.

document.ImportPageRange(loadedDocument, 0, loadedDocument.Pages.Count - 1);

//Closes the document.

loadedDocument.Close(true);

}

//Saves and closes the document.

document.Save("Output.pdf");

document.Close(true);

{% endhighlight %}



{% highlight vbnet %}

'Inputs PDF documents.

Dim inputDocuments As String() = {"Input1.pdf", "Input2.pdf", "Input3.pdf", "Input4.pdf", "Input5.pdf", "Input6.pdf", _"Input7.pdf", "Input8.pdf", "Input9.pdf", "Input10.pdf"}

'Creates a new instance. 

Dim document As New PdfDocument()

'Optimizes memory while merging PDF documents.

document.EnableMemoryOptimization = True

'Iterates input PDF documents.

For Each inputDocument As String In inputDocuments

'Loads PDF document in order to merge.

Dim loadedDocument As New PdfLoadedDocument(inputDocument)

loadedDocument.EnableMemoryOptimization = True

'Merges loaded document contents to parent PDF document.

document.ImportPageRange(loadedDocument, 0, loadedDocument.Pages.Count - 1)

'Closes the document.

loadedDocument.Close(True)

Next

'Saves and closes the document.

document.Save("Output.pdf")

document.Close(True)

{% endhighlight %}

