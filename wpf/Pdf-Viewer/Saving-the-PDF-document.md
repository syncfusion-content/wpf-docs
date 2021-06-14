---
layout: post
title: Saving PDF Files in WPF Pdf Viewer control | Syncfusion
description: Learn about Saving PDF Files support in Syncfusion Essential Studio WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Saving PDF Files in WPF Pdf Viewer

The PDF Viewer allows you to save the PDF document that is being displayed. It helps you to keep the file up to date with any modifications and prevent your work from being lost. You can save the changes in the PDF document using the "Save" and "Save As" options available in the toolbar.

![WPF PDF Viewer Save PDF Files](Concept-and-Features_images\wpf-pdf-viewer-save-pdf-files.png)

N> The "Save" option in the toolbar will not be enabled if the file is not edited, or if the file is loaded using the Stream and `PdfLoadedDocument` objects. In these cases, you can use the "Save As" option.

You can also call the [Save](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_Save_System_String_) method to silently save the modified PDF file to a specific path in the local disk. Refer to the following code to perform the same from the application level.

{% tabs %}
{% highlight c# %}

Private void SavePDF()
{
    //Save the PDF file to a specific file path after doing any modifications by passing the file name as a parameter to the `Save` method.
    pdfViewer.Save("Saved.pdf");
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub SavePDF()
    'Save the PDF file to a specific file path after doing any modifications by passing the file name as a parameter to the Save method.
    pdfViewer.Save("Saved.pdf")
End Sub

{% endhighlight %}
{% endtabs %}

## Events

The [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) notifies you at the start and end of the save operation using the [BeginSave](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_BeginSave) and [EndSave](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_EndSave) events respectively.

### Begin Save

The [BeginSave](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_BeginSave) event occurs before initiating the save operation of the PDF file. It also allows you to cancel the save operation using the [Cancel](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.BeginSaveEventArgs.html#Syncfusion_Windows_PdfViewer_BeginSaveEventArgs_Cancel) property of [BeginSaveEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.BeginSaveEventArgs.html). The following code shows how to wire the event in the [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html).

{% tabs %}
{% highlight c# %}

namespace SaveEvents
{
	public partial class MainWindow : Window
	{
		#region Constructor
		public MainWindow()
		{
			InitializeComponent();

			//Wire the `BeginSave` event.
			PdfViewer.BeginSave += PdfViewer_BeginSave;

			//Load the PDF file
			PdfViewer.Load("../../Data/Windows Store Apps Succinctly.pdf");
		}
		#endregion

		#region Events
		private void PdfViewer_BeginSave(object sender, BeginSaveEventArgs e)
		{
			//Insert your code here
		}
		#endregion
	}
}

{% endhighlight %}
{% endtabs %}

### End Save

The [EndSave](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_EndSave) event occurs after the completion of the save operation.  The [IsCanceled](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.EndSaveEventArgs.html#Syncfusion_Windows_PdfViewer_EndSaveEventArgs_IsCanceled) property of the [EndSaveEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.EndSaveEventArgs.html) helps you to know whether the save operation is canceled or not. The following code shows how to wire the event in the [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html).

{% tabs %}
{% highlight c# %}

namespace SaveEvents
{
    public partial class MainWindow : Window
    {
        #region Constructor
        public MainWindow()
        {
            InitializeComponent();

            //Wire the `EndSave` event.
            PdfViewer.EndSave += PdfViewer_EndSave;

            //Load the PDF file
            PdfViewer.Load("../../Data/Windows Store Apps Succinctly.pdf");
        }
        #endregion

        #region Events
        private void PdfViewer_EndSave(object sender, EndSaveEventArgs e)
        {
            //Insert your code here
        }
        #endregion
    }
}

{% endhighlight %}
{% endtabs %}

## Keyboard shortcuts

The following keyboard shortcuts can be used to save the files when the toolbar is enabled:
* `Ctrl + S`: If the "Save" option is enabled in the PDF Viewer, it performs "Save" in the PDF document. Else, it performs "Save As" in the PDF document.
* `Shift + Ctrl + S`: Performs "Save As" in the PDF document.
