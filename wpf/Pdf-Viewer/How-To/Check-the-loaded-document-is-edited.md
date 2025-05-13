---
layout: post
title: Check the loaded document is edited in PdfViewer | Syncfusion<sup>&reg;</sup>;
description: Learn about how to Check the loaded document is edited in Syncfusion<sup>&reg;</sup>; WPF Pdf Viewer control using IsDocumentEdited property.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Check the loaded document is edited or not

The PDF Viewer allows you to check whether the loaded PDF document has been modified during the viewing session. This helps determine if you need to prompt the user to save changes before exiting or closing the document.The [IsDocumentEdited](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_IsDocumentEdited) property of the PDF Viewer provides a simple way to determine whether the loaded document has been modified it's returning true,and false if no modifications have occurred.


{% tabs %}
{% highlight c# %}

public MainWindow()
{
    InitializeComponent();
    // Load the specified PDF file.
    pdfViewer.Load("Document.pdf");
    // Attach an event handler to the Closed event of the window.
    this.Closed += MainWindow_Closed;
}
private void MainWindow_Closed(object sender, EventArgs e)
{
    bool isPDFEdited = pdfViewer.IsDocumentEdited;

    if (isPDFEdited)
    {
        MessageBox.Show("The PDF document has been edited.", "Alert", MessageBoxButton.OK, MessageBoxImage.Information);
    }
    else
    {
        MessageBox.Show("The PDF document has not been edited.", "Alert", MessageBoxButton.OK, MessageBoxImage.Information);
    }
}
{% endhighlight %}
{% endtabs %}

