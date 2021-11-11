---
layout: post
title: Form Filling in PDF Files in WPF Pdf Viewer | Syncfusion
description: Learn about Form Filling in PDF Files support in Syncfusion WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Form Filling in PDF Files in WPF Pdf Viewer

PDF Viewer provides the ability to Fill, Edit, Flatten, and Save the `AcroForm` fields in PDF files.

![WPF PDF Viewer Form Filling](form-filling-images/wpf-pdf-viewer-form-filling.png)

## Supported form fields

You can load and fill the following form fields in a PDF document using the PDF Viewer.

1.	Text box.
2.	Password box.
3.	Checkbox.
4.	Radio button.
5.	Combo box.
6.	List box.

## Retrieve the form field details 

You can retrieve the details of a form field through the [FormFieldClicked](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_FormFieldClicked) event of [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) by simply clicking on the field. The [FormField](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.FormFieldClickedEventArgs.html#Syncfusion_Windows_PdfViewer_FormFieldClickedEventArgs_FormField) property of the [FormFieldClickedEventArgs](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.FormFieldClickedEventArgs.html) needs to be typecast to the respective control.The following code snippet explains how to retrieve details for all [supported form fields](https://help.syncfusion.com/wpf/pdf-viewer/form-filling-in-pdf#supported-form-fields) using the FormFieldClicked event.

{% tabs %}
{% highlight c# %}

//Wire the `FormFieldClicked` event.
pdfViewer.FormFieldClicked += PdfViewer_FormFieldClicked;

private void PdfViewer_FormFieldClicked(object sender, FormFieldClickedEventArgs args)
{
	  //Typecast the `FormField` property to `System.Windows.Controls.TextBox`
            TextBox textBox = args.FormField as TextBox;
            if (textBox != null)
            {
                //Retrive the `Text` property
                string text = textBox.Text;
                //{Insert your code here}
            }

            //Typecast the `FormField` property to `System.Windows.Controls.PasswordBox`
            PasswordBox PasstextBox = args.FormField as PasswordBox;
            if (PasstextBox != null)
            {
                //Retrive the `Text` property
                string password = PasstextBox.Password;
                //{Insert your code here}
            }

            //Typecast the `FormField` property to `System.Windows.Controls.ListBox`
            ListBox listBox = args.FormField as ListBox;
            if (listBox != null)
            {
                //Retrive the `SelectedItem` value
                object selectedItem = listBox.SelectedItem;
                //{Insert your code here}
            }

            //Typecast the `FormField` property to `System.Windows.Controls.ComboBox`
            ComboBox comboBox = args.FormField as ComboBox;
            if (comboBox != null)
            {
                //Retrive the `SelectedItem` value
                object selectedItem  =  comboBox.SelectedItem;
                 //{Insert your code here}
            }

            //Typecast the `FormField` property to `System.Windows.Controls.CheckBox`
            CheckBox checkBox = args.FormField as CheckBox;
            if (checkBox != null)
            {
                //Retrive the checkbox `IsChecked` status
                bool ischecked = (bool)checkBox.IsChecked;
                //{Insert your code here}
            }

            //Typecast the `FormField` property to `System.Windows.Controls.RadioButton`
            RadioButton radiobtn = args.FormField as RadioButton;
            if (radiobtn != null)
            {
                //Retrive the radio button `IsChecked` status
                bool ischecked =  (bool)radiobtn.IsChecked;
                //{Insert your code here}
            }
}

{% endhighlight %}
{% endtabs %}

N> The sample project of PDF form filling using the Syncfusion PDF Viewer is available in the [GitHub](https://github.com/syncfusion/wpf-demos/tree/master/pdfviewer).

## Import and Export Form Data

In WPF, the PDF viewer allows the users to import and export form data to and from the PDF documents.

### Import Form Data

Follow the below steps to import date to PDF document with `AcroForm`.

1.	Click the form data tool button in the left pane, the form data toolbar will appear as a secondary toolbar in the [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html).
2.	Select **Import** option in form data toolbar to import the PDF form data.

![WPF PDF Viewer Import Form Data](form-filling-images/wpf-pdf-viewer-import-form-data.png)  

The following code shows how to import form data in code behind.

{% tabs %}
{% highlight c# %}

private void button1_Click(object sender, RoutedEventArgs e)
{
    //Import PDF form data
    pdfviewer.ImportFormData("Import.fdf", Syncfusion.Pdf.Parsing.DataFormat.Fdf);
}

{% endhighlight %}
{% highlight VB %}

Private Sub button1_Click(sender As Object, e As RoutedEventArgs)
    'Import PDF form data
    pdfviewer.ImportFormData("Import.fdf", Syncfusion.Pdf.Parsing.DataFormat.Fdf)
End Sub

{% endhighlight %}
{% endtabs %}

### Export Form Data

Follow the below steps to export data from PDF document

1. Select **Export** option in the form data toolbar, to save the completed PDF form data as a file in another file format.
2. In Export Form Data As dialog box, you can select the desired format to save the form data (FDF, XFDF, XML, and JSON).

N> If the PDF document is loaded as a stream, the [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html) will request for the form name when exporting.

The following code shows how to export form data in code behind.

{% tabs %}
{% highlight c# %}

private void button1_Click(object sender, RoutedEventArgs e)
{
    //Export PDF form data
    pdfviewer.ExportFormData("Export.fdf", Syncfusion.Pdf.Parsing.DataFormat.Fdf, "SourceForm.pdf");
}

{% endhighlight %}
{% highlight VB %}

Private Sub button1_Click(sender As Object, e As RoutedEventArgs)
    'Export PDF form data
    pdfviewer.ExportFormData("Export.fdf", Syncfusion.Pdf.Parsing.DataFormat.Fdf, "SourceForm.pdf")
End Sub

{% endhighlight %}
{% endtabs %}


N> You can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the pdfviewer.