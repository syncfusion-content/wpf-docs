---
layout: post
title: Extract Text from PDF Files in WPF Pdf Viewer control | Syncfusion
description: Learn about Extract Text from PDF Files support in Syncfusion WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
 documentation: ug
---

# Extract Text from PDF Files in WPF Pdf Viewer

PDF Viewer allows you to extract the text from a particular page or from the entire PDF file using the [ExtractText](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html#Syncfusion_Windows_PdfViewer_PdfDocumentView_ExtractText_System_Int32_Syncfusion_Pdf_TextLines__) methods of [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html). 

N> PDF Viewer uses PDFium as a default rendering engine to extract text from PDF files. Refer to this [link](https://help.syncfusion.com/wpf/pdf-viewer/pdf-rendering-engines) for more details about the PDF rendering engines.

## Extract text from a particular page

You can extract the text from a page using [ExtractText](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html#Syncfusion_Windows_PdfViewer_PdfDocumentView_ExtractText_System_Int32_Syncfusion_Pdf_TextLines__) method in [PdfDocumentView](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html) class. The following code sample explains how to extract the text from the first page.

{% tabs %}
{% highlight c# %}
using System.Windows;
using Syncfusion.Pdf;
using Syncfusion.Windows.PdfViewer;

namespace TextExtractionDemo
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

            //Initialize the `PdfDocumentView` control.
            PdfDocumentView pdfDocumentView = new PdfDocumentView();

            //Load the PDF file.
            pdfDocumentView.Load(@"Sample.pdf");

            //Extract text from the first page.
            TextLines textLines = new TextLines();
            string extractedText = pdfDocumentView.ExtractText(0, out textLines);
        }
        #endregion
    }
}
{% endhighlight %}
{% endtabs %}

N> In this method, the text is extracted in the order in which it is written in the document stream and it may not be in the order in which it is viewed in the PDF reader application.

## Extract text from an entire file

You can extract text from an entire file by using the following code sample.

{% tabs %}
{% highlight c# %}
using System.Windows;
using Syncfusion.Pdf;
using Syncfusion.Windows.PdfViewer;

namespace TextExtractionDemo
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
			
			//Initialize the `PdfDocumentView` control.
            PdfDocumentView pdfDocumentView = new PdfDocumentView();
			
			//Load the PDF file.
            pdfDocumentView.Load(@"Sample.pdf");
			
			//Extract text from the file.
            TextLines textLines = new TextLines();
            string extractedText = string.Empty;
            for (int i = 0; i < pdfDocumentView.PageCount; i++)
            {
                extractedText += pdfDocumentView.ExtractText(i, out textLines);
            }
        }
        #endregion
    }
}			
{% endhighlight %}
{% endtabs %}

## Extract text with bounds

### Extract lines

You can get the text line by line along with the bounds using the [TextLines](https://help.syncfusion.com/cr/wpf/Syncfusion.Pdf.TextLines.html) property from the [ExtractText](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html#Syncfusion_Windows_PdfViewer_PdfDocumentView_ExtractText_System_Int32_Syncfusion_Pdf_TextLines__) method. Refer to the following code sample to perform the same.

{% tabs %}
{% highlight C# %}
using System.Drawing;
using System.Windows;
using Syncfusion.Pdf;
using Syncfusion.Windows.PdfViewer;

namespace TextExtractionDemo
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

            //Initialize the `PdfDocumentView` control.
            PdfDocumentView pdfDocumentView = new PdfDocumentView();

            //Load the PDF file.
            pdfDocumentView.Load(@"Sample.pdf");

            //Initialize the `TextLines`
            TextLines textLines = new TextLines();

            //Pass the `TextLines` as a parameter to the `ExtractText` method.
            pdfDocumentView.ExtractText(0, out textLines);

            //Gets specific line from the collection through the index.
            TextLine line = textLines[0];

            //Get text in the line.
            string text = line.Text;
			
            //Get bounds of the line.
            RectangleF lineBounds = line.Bounds;
        }
        #endregion
    }
}
{% endhighlight %}
{% endtabs %}

### Extract words
 
You can get the words in a line along with the bounds using the [WordCollection](https://help.syncfusion.com/cr/wpf/Syncfusion.Pdf.TextLine.html#Syncfusion_Pdf_TextLine_WordCollection) property of the [TextLine](https://help.syncfusion.com/cr/wpf/Syncfusion.Pdf.TextLine.html) using [ExtractText](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfDocumentView.html#Syncfusion_Windows_PdfViewer_PdfDocumentView_ExtractText_System_Int32_Syncfusion_Pdf_TextLines__) method. Refer to the following code sample to perform the same.

{% tabs %}
{% highlight C# %}
using System.Collections.Generic;
using System.Drawing;
using System.Windows;
using Syncfusion.Pdf;
using Syncfusion.Windows.PdfViewer;

namespace TextExtractionDemo
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

            //Initialize the `PdfDocumentView` control.
            PdfDocumentView pdfDocumentView = new PdfDocumentView();

            //Load the PDF file.
            pdfDocumentView.Load(@"Sample.pdf");

            //Initialize the `TextLines`
            TextLines textLines = new TextLines();

            //Pass the `TextLines` as a parameter to the `ExtractText` method.
            pdfDocumentView.ExtractText(0, out textLines);

            //Gets specific line from the collection through the index.
            TextLine line = textLines[0];

            //Get the word collection in a line.
            List<TextWord> wordCollection= line.WordCollection;

            //Get the word
            string word = wordCollection[0].Text;

            //Get the bounds of the word
            RectangleF bounds= wordCollection[0].Bounds;
        }
        #endregion
    }
}
{% endhighlight %}
{% endtabs %}
