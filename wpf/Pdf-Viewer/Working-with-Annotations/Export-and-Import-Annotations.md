---
layout: post
title: Export and Import Annotations using WPF PDF Viewer | Syncfusion
description: Learn about Export and Import information about annotations in the FDF and XFDF formats using WPF PDF Viewer.
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

Export information about annotations in files/stream in FDF and XFDF formats.

### Exporting annotations from file

The [ExportAnnotations](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ExportAnnotations_System_String_Syncfusion_Pdf_Parsing_AnnotationDataFormat_) method exports the annotations added in the document to a file in a specified file format. The annotation data format should be given as an argument.

{% tabs %}
{% highlight C# %}
//Export annotations to "fdf" data format to file 
pdfViewer.ExportAnnotations("Annotation.fdf", AnnotationDataFormat.Fdf);

{% endhighlight %}
{% endtabs %}

### Exporting annotations from stream

The [ExportAnnotations](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ExportAnnotations_System_IO_Stream_Syncfusion_Pdf_Parsing_AnnotationDataFormat_) method also exports the annotations added in the document to a stream in a specified file format. The annotation data format should be given as an argument.

{% tabs %}
{% highlight C# %}
//Export annotations to "fdf" data format to stream
Stream stream = new MemoryStream();
pdfViewer.ExportAnnotations(stream, AnnotationDataFormat.Fdf);

{% endhighlight %}
{% endtabs %}

## Importing annotations

Import information about annotations from files/stream in FDF and XFDF formats.

### Importing annotations from file

The [ImportAnnotations](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ImportAnnotations_System_String_Syncfusion_Pdf_Parsing_AnnotationDataFormat_) method imports the annotations from the file of a specified type and fills the annotations into the loaded PDF document. The full path of the file contains the annotation information. The annotation data format should be given as the arguments.

{% tabs %}
{% highlight C# %}
//Import annotations to "fdf " data format
pdfViewer.ImportAnnotations("Annotation.fdf", AnnotationDataFormat.Fdf);

{% endhighlight %}
{% endtabs %}

### Importing annotations from stream

The [ImportAnnotations](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_ImportAnnotations_System_IO_Stream_Syncfusion_Pdf_Parsing_AnnotationDataFormat_) method imports the annotations from the file stream of a specified type and fills the annotations into the loaded PDF document. The file stream contains the annotation information. The annotation data format should be given as the arguments.

{% tabs %}
{% highlight C# %}
//Import annotations to "fdf" data format to stream
FileStream stream = File.OpenRead("Annotation.fdf");
pdfViewer.ImportAnnotations(stream, AnnotationDataFormat.Fdf);

{% endhighlight %}
{% endtabs %}