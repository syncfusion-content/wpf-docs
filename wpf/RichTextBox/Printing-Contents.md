---
title: Printing Contents in WPF RichTextBox control | Syncfusion
description: Learn here all about Printing Contents support in Syncfusion WPF RichTextBox (SfRichTextBoxAdv) control and more.
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: printing
---
# Printing Contents in WPF RichTextBox (SfRichTextBoxAdv)

The SfRichTextBoxAdv supports API to print the rich text content rendered as pages using the print dialog.
The following sample code demonstrates how to print the document content as pages.
{% tabs %}
{% highlight c# %}
// Displays the Print Dialog to perform printing of document content as pages.
richTextBoxAdv.PrintDocument();


{% endhighlight %}
{% highlight VB %}
' Displays the Print Dialog to perform printing of document content as pages.
richTextBoxAdv.PrintDocument()


{% endhighlight %}
{% endtabs %}

The SfRichTextBoxAdv also supports event to notify whenever the printing operation is completed. The following code example demonstrates how to handle for the print completed event.
{% tabs %}
{% highlight c# %}
// Hooks the print completed event.
richTextBoxAdv.PrintCompleted += RichTextBoxAdv_PrintCompleted;

// Called whenever the print completed event is fired.
private void RichTextBoxAdv_PrintCompleted(object obj, PrintCompletedEventArgs args)
{
    // Handle your code here.
}

// Unhooks the print completed event.
richTextBoxAdv.PrintCompleted -= RichTextBoxAdv_PrintCompleted;


{% endhighlight %}
{% highlight VB %}
' Hooks the print completed event.
AddHandler richTextBoxAdv.PrintCompleted, AddressOf RichTextBoxAdv_PrintCompleted

' Called whenever the print completed event is fired.
Private Sub RichTextBoxAdv_PrintCompleted(obj As Object, args As PrintCompletedEventArgs)
	' Handle your code here.
End Sub

' Unhooks the print completed event.
RemoveHandler richTextBoxAdv.PrintCompleted, AddressOf RichTextBoxAdv_PrintCompleted
{% endhighlight %}
{% endtabs %}

## UI Command for printing

The following code example demonstrates how to bind UI Command to invoke printing in SfRichTextBoxAdv.
{% tabs %}
{% highlight XAML %}
<!-- Binds button to the PrintDocumentCommand -->
<Button Content="Print" Command="RichTextBoxAdv:SfRichTextBoxAdv.PrintDocumentCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />


{% endhighlight %}

{% endtabs %}

N> In order to invoke printing, the standard keyboard shortcut CTRL + P can also be used.
