---
layout: post
title: Export and Import Annotations in WPF Pdf Viewer control | Syncfusion
description: Learn about Export and Import Annotations support in Syncfusion Essential Studio WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Exporting and Importing Annotations

PDF viewer allows the users to import and export information about annotations in PDF files. The annotation information can be exported and imported in the following data formats.

* fdf
* xfdf

The required data format can be chosen from the ‘AnnotationDataFormat’ enumeration. In the following sections the fdf data format is explained for brevity, similarly we can implement for xfdf.

## Exporting annotations

The ExportAnnotations method exports the all the annotations added in the document into a file or stream in the specified file format. The full path of file or file stream in which the annotation information should export, and the annotation data format should be given as the arguments.

{% tabs %}
{% highlight C# %}
//Export annotations to "fdf" data format to file 
pdfViewer.ExportAnnotations("Annotation.fdf ", AnnotationDataFormat.fdf);

//Export annotations to "fdf" data format to stream
Stream stream = new MemoryStream();
pdfViewer.ExportAnnotations(stream, AnnotationDataFormat.fdf);

{% endhighlight %}
{% endtabs %}

## Importing annotations

The ImportAnnotations method imports the annotations from the file or file stream of specified type and fills the annotations into the loaded PDF document. The full path to file or file stream which contains the annotation information, and the annotation data format should be given as the arguments.

{% tabs %}
{% highlight C# %}
//Import annotations to "fdf " data format
pdfViewer.ImportAnnotations("Annotation.fdf ", AnnotationDataFormat.fdf);

//Export annotations to "fdf" data format to stream
pdfViewer.ImportAnnotations (stream, AnnotationDataFormat.fdf);

{% endhighlight %}
{% endtabs %}
