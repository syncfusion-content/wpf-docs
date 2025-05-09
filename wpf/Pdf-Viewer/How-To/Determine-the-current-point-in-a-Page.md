---
layout: post
title: Getting the clicked location in a page in WPF Pdf Viewer | Syncfusion®
description: Calculate the exact clicked point on a page in the Syncfusion® WPF PDF Viewer control using the PageClicked event.
platform: wpf
control: PDF Viewer
documentation: ug
---

#  Determining the Clicked Position in the WPF PDF Viewer

Use the [PageClicked](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_PageClicked) event of the Syncfusion WPF PDF Viewer control to capture the exact location where the user clicks on a PDF page. The event provides pixel coordinates, which can be converted to PDF points (1 point = 1/72 inch) and adjusted for the viewer’s zoom level to yield accurate positions on the document.

Refer to the code snippet below for implementation details

{% tabs %}
{% highlight c# %}

 private void PdfViewer_PageClicked(object sender, Syncfusion.Windows.PdfViewer.PageClickedEventArgs args)
 {
     //Get the current point where the mouse is clicked. The value is in pixels.
     Point currentPointInPixels = args.Position;

     //Convert the point from pixels to points.
     PdfUnitConvertor convertor = new PdfUnitConvertor();
     System.Drawing.PointF currentPoint = convertor.ConvertFromPixels( new System.Drawing.PointF((float)currentPointInPixels.X, (float)currentPointInPixels.Y), PdfGraphicsUnit.Point);

     //Convert the point based on the zoom factor.
     float zoomFactor = (float)pdfViewer.ZoomPercentage / 100;
     System.Drawing.PointF finalPoint = new System.Drawing.PointF(currentPoint.X / zoomFactor, currentPoint.Y / zoomFactor);

     //Display the point through message box.
     MessageBox.Show("The point clicked is: " + finalPoint.ToString());
 }

{% endhighlight %}

{% highlight vbnet %}

Private Sub PdfViewer_PageClicked(sender As Object, args As Syncfusion.Windows.PdfViewer.PageClickedEventArgs)
    ' Get the current point where the mouse is clicked. The value is in pixels.
    Dim currentPointInPixels As Point = args.Position

    ' Convert the point from pixels to points.
    Dim convertor As New PdfUnitConvertor()
    Dim currentPoint As System.Drawing.PointF = convertor.ConvertFromPixels(New System.Drawing.PointF(CSng(currentPointInPixels.X), CSng(currentPointInPixels.Y)), PdfGraphicsUnit.Point)

    ' Convert the point based on the zoom factor.
    Dim zoomFactor As Single = CSng(pdfViewer.ZoomPercentage) / 100
    Dim finalPoint As New System.Drawing.PointF(currentPoint.X / zoomFactor, currentPoint.Y / zoomFactor)

    ' Display the point through message box.
    MessageBox.Show("The point clicked is: " & finalPoint.ToString())
End Sub

{% endhighlight %}
{% endtabs %}



