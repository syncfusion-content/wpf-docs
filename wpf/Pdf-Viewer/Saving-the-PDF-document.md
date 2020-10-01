---
layout: post
title: Saving PDF Files | PDF Viewer | Wpf | Syncfusion
description: The PDF Viewer supports saving a PDF file loaded in it. It keeps the file up to date with any modifications by allowing you to save the file in the local disk.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Saving PDF Files in WPF Pdf Viewer

PDF Viewer allows you to save the PDF document that is being displayed in the PDF Viewer. It helps you to keep the file up to date with any modifications and prevent your work from being lost. The [Save](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_Save_System_String_) method of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) allows you to save the modified PDF file to a specific path in the local disk. Refer to the following code to achieve the same in a button click event from the application level.

{% tabs %}
{% highlight c# %}
using System.Windows;

namespace PdfViewer
{
    /// <summary>
    /// Interaction logic for Window1.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        #region Constructor
        public MainWindow()
        {
            InitializeComponent();
            //Load the PDF
            pdfViewer.Load("Sample.pdf");
        }
        #endregion

        private void SaveButton_Click(object sender, RoutedEventArgs e)
        {
            //Save the PDF file to a specific file path after doing any modifications, 
            //by passing the file name as a parameter to `Save` method
            pdfViewer.Save("Saved.pdf");
        }
    }
}
{% endhighlight %}

{% highlight vbnet %}
Imports System.Windows

Namespace PdfViewer
    Public Partial Class MainWindow
        Inherits Window

        Public Sub New()
            InitializeComponent()
            'Load the PDF
            pdfViewer.Load("Sample.pdf")
        End Sub

        Private Sub SaveButton_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
            'Save the PDF file to a specific file path after doing any modifications, 
            'by passing the file name as a parameter to the Save method
            pdfViewer.Save("Saved.pdf")
        End Sub
    End Class
End Namespace
{% endhighlight %}
{% endtabs %}

## Save PDF file using command

You can save the PDF file in the given file path using the `SaveDocumentCommand`. The following code shows how to save the PDF file by executing the command and to the pass the file path as command parameter.

{% tabs %}
{% highlight c# %}

pdfViewerControl.SaveDocumentCommand.Execute(@"C:\temp\Output.pdf");

{% endhighlight %}
{% endtabs %}