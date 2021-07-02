---
layout: post
title: Export and Import Annotations in WPF Pdf Viewer control | Syncfusion
description: Learn about Export and Import information about annotations in the FDF and XFDF formats using WPF Pdf Viewer.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Exporting and Importing Annotations

PDF viewer allows the users to import and export information of annotations in PDF files. The annotation information can be exported and imported in the following data formats.

* fdf
* xfdf

The required data format can be chosen from the [AnnotationDataFormat](https://help.syncfusion.com/cr/wpf/Syncfusion.Pdf.Parsing.AnnotationDataFormat.html) enumeration. In the following sections, the fdf data format is explained for brevity and similarly we can implement for xfdf.

## Exporting annotations

### Export to a file

The ExportAnnotations method exports the annotations added in the document to a file in specified file format. The annotation data format should be given as an arguments.

{% tabs %}
{% highlight C# %}
//Export annotations to "fdf" data format to file 
pdfViewer.ExportAnnotations("Annotation.fdf", AnnotationDataFormat.Fdf);

{% endhighlight %}
{% endtabs %}

### Export to a stream

The ExportAnnotations method also exports the annotations added in the document to a stream in specified file format. The annotation data format should be given as an arguments.

{% tabs %}
{% highlight C# %}
//Export annotations to "fdf" data format to stream
Stream stream = new MemoryStream();
pdfViewer.ExportAnnotations(stream, AnnotationDataFormat.Fdf);

{% endhighlight %}
{% endtabs %}

## Importing annotations

### Import from a file
The ImportAnnotations method imports the annotations from the file of a specified type and fills the annotations into the loaded PDF document. The full path of file contains the annotation information. The annotation data format should be given as the arguments.

{% tabs %}
{% highlight C# %}
//Import annotations to "fdf " data format
pdfViewer.ImportAnnotations("Annotation.fdf", AnnotationDataFormat.Fdf);

{% endhighlight %}
{% endtabs %}

### Import from a stream
The ImportAnnotations method imports the annotations from the file stream of a specified type and fills the annotations into the loaded PDF document. The file stream contains the annotation information. The annotation data format should be given as the arguments.

{% tabs %}
{% highlight C# %}
//Import annotations to "fdf" data format to stream
FileStream stream = File.OpenRead("Annotation.fdf");
pdfViewer.ImportAnnotations(stream, AnnotationDataFormat.Fdf);

{% endhighlight %}
{% endtabs %}