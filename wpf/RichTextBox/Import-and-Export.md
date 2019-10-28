---
title: Import and Export |  SfRichTextBoxAdv | WPF | Syncfusion
description: This section describes how to perform the import/export word, rich text format, HTML, XAML and text documents in WPF SfRichTextBoxAdv Control.
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: import, export, load, save
---
# Import and Export

The SfRichTextBoxAdv allows you to import/export word documents (.docx, .doc), rich text format documents (.rtf), HTML documents (.htm, .html), XAML documents (.xaml) and text documents (.txt).
The following sample code demonstrates how to import contents from a file into SfRichTextBoxAdv.
{% tabs %}
{% highlight c# %}
// Imports the document.
void ImportDocument ()
{
    // Initializes the open file dialog.
    OpenFileDialog openFileDialog = new OpenFileDialog()
    {
        Filter = "All supported files (*.docx,*.doc,*.htm,*.html,*.rtf,*.txt,*.xaml)|*.docx;*.doc;*.htm;*.html;*.rtf;*.txt;*.xaml|Word Document (*.docx)|*.docx|Word 97 - 2003 Document (*.doc)|*.doc|Web Page (*.htm,*.html)|*.htm;*.html|Rich Text File (*.rtf)|*.rtf|Text File (*.txt)|*.txt|Xaml File (*.xaml)|*.xaml",
        FilterIndex = 1,
        Multiselect = false
    };

    if ((bool)openFileDialog.ShowDialog())
    {
        // Loads the file into RichTextBoxAdv.
        richTextBoxAdv.Load(openFileDialog.FileName);
        // Sets the File name as Document Title.
        richTextBoxAdv.DocumentTitle = openFileDialog.FileName.Remove(openFileDialog.FileName.LastIndexOf("."));
    }
}



{% endhighlight %}
{% highlight VB %}
' Imports the document.
Private Sub ImportDocument()
	' Initializes the open file dialog.
	Dim openFileDialog As New OpenFileDialog() With { _
		Key .Filter = "All supported files (*.docx,*.doc,*.htm,*.html,*.rtf,*.txt,*.xaml)|*.docx;*.doc;*.htm;*.html;*.rtf;*.txt;*.xaml|Word Document (*.docx)|*.docx|Word 97 - 2003 Document (*.doc)|*.doc|Web Page (*.htm,*.html)|*.htm;*.html|Rich Text File (*.rtf)|*.rtf|Text File (*.txt)|*.txt|Xaml File (*.xaml)|*.xaml", _
		Key .FilterIndex = 1, _
		Key .Multiselect = False _
	}

	If CBool(openFileDialog.ShowDialog()) Then
		' Loads the file into RichTextBoxAdv.
		richTextBoxAdv.Load(openFileDialog.FileName)
		' Sets the File name as Document Title.
		richTextBoxAdv.DocumentTitle = openFileDialog.FileName.Remove(openFileDialog.FileName.LastIndexOf("."))
	End If
End Sub


{% endhighlight %}
{% endtabs %}

The following code example demonstrates how to export SfRichTextBoxAdv contents into a file.
{% tabs %}
{% highlight c# %}
// Exports the document.
void ExportDocument ()
{    
    // Initializes the file save picker.
    SaveFileDialog saveFileDialog = new SaveFileDialog()
    {
        Filter = "Word Document (*.docx)|*.docx|Word 97 - 2003 Document (*.doc)|*.doc|Web Page (*.htm,*.html)|*.htm;*.html|Rich Text File (*.rtf)|*.rtf|Text File (*.txt)|*.txt|Xaml File (*.xaml)|*.xaml",
        FilterIndex = 1
    };
    if ((bool)saveFileDialog.ShowDialog())
    {
        // Saves the document content into a file.
        richTextBoxAdv.Save(saveFileDialog.FileName);
    }
}



{% endhighlight %}
{% highlight VB %}
' Exports the document.
Private Sub ExportDocument()
	' Initializes the file save picker.
	Dim saveFileDialog As New SaveFileDialog() With { _
		Key .Filter = "Word Document (*.docx)|*.docx|Word 97 - 2003 Document (*.doc)|*.doc|Web Page (*.htm,*.html)|*.htm;*.html|Rich Text File (*.rtf)|*.rtf|Text File (*.txt)|*.txt|Xaml File (*.xaml)|*.xaml", _
		Key .FilterIndex = 1 _
	}
	If CBool(saveFileDialog.ShowDialog()) Then
		' Saves the document content into a file.
		richTextBoxAdv.Save(saveFileDialog.FileName)
	End If
End Sub


{% endhighlight %}
{% endtabs %}

N> When the SfRichTextBoxAdv control encounters an unsupported element, it does not render the element, instead, it continues to the next supported element and render it. Examples of unsupported elements are AutoShapes, watermarks, charts, SmartArt, WordArt, equations, document structure tags, styles, wrapping styles, fields other than hyperlinks, absolutely positioned tables, and absolutely positioned images.

## UI Commands for importing/exporting documents

The following code example demonstrates how to bind commands for performing importing and exporting documents.
{% tabs %}
{% highlight xaml %}
<!-- Binds button to the OpenDocumentCommand -->
<Button Content="Open" Command="RichTextBoxAdv:SfRichTextBoxAdv.OpenDocumentCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the SaveDocumentCommand -->
<Button Content="Save" Command="RichTextBoxAdv:SfRichTextBoxAdv.SaveDocumentCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />


{% endhighlight %}

{% endtabs %}

N> In order to perform import/export documents, the standard keyboard shortcuts such as CTRL + O, CTRL + S can also be used.
