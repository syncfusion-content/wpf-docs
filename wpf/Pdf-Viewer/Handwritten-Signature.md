---
layout: post
title: Handwritten Signature in PDF Viewer WPF | Syncfusion
description: Adding, modifying and deleting handwritten signature in PDF document using Syncfusion PDF Viewer WPF.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Handwritten Signature

PDF viewer WPF allows the user to include handwritten signature in the PDF document and provides options to edit or remove the included handwritten signature in the PDF document.

The following code shows how to switch to handwritten signature mode in code behind.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.HandwrittenSignature; 
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.AnnotationMode = PdfDocumentView.PdfViewerAnnotationMode.HandwrittenSignature
End Sub

{% endhighlight %}
{% endtabs %}

Moving to `HandwrittenSignature` mode will open the signature pad, requesting the user to draw the signature. Clicking on apply will add the signature in the PDF Document, this can then be resized and moved to appropriate location.

 ![Handwritten Signature](Handwritten-Signature_images\Handwritten-Signature-1.png)

## How to set the opacity of the handwritten signature?

The opacity of the handwritten signature can be customized at the time of inclusion itself. The following code shows how to set opacity value of the handwritten signature to be included.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.HandwrittenSignatureSettings.Opacity = 0.5F;
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.HandwrittenSignatureSettings.Opacity = 0.5F
End Sub

{% endhighlight %}
{% endtabs %}

## How to set the color of the handwritten signature?

The color of the handwritten signature can be customized at the time of inclusion itself.

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.HandwrittenSignatureSettings.Color = Colors.Green; 
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.HandwrittenSignatureSettings.Color = Colors.Green
End Sub

{% endhighlight %}
{% endtabs %}

## How to flatten handwritten signature on save?

The included handwritten signature can be flattened in the PDF document when saving it, setting `FlattenSignatureOnSave` Boolean to true in `HandwrittenSignatureSettings` will do this. 

{% tabs %}
{% highlight C# %}

private void Window_Loaded(object sender, RoutedEventArgs e)
{
    PdfLoadedDocument pdf = new PdfLoadedDocument("Input.pdf");
    pdfviewer.Load(pdf);
    pdfviewer.HandwrittenSignatureSettings.FlattenSignatureOnSave = true; 
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub Window_Loaded(sender As Object, e As RoutedEventArgs)
    Dim pdf As New PdfLoadedDocument(“Input.pdf”)
    pdfViewer.Load(pdf)
    pdfviewer.HandwrittenSignatureSettings.FlattenSignatureOnSave = true
End Sub

{% endhighlight %}
{% endtabs %}

N> If the handwritten signature is not flattened, it will be saved as ink annotation in the PDF document. 

## Working with included handwritten signatures

The PDF viewer allows editing the color and opacity of the Handwritten signature included in the document in the UI.. To perform this, select the included handwritten signature and click right using mouse, over the selected handwritten signature, a pop-up context menu will appear with the following options,

*	Properties
*	Delete

### Properties

Selecting properties from the context menu will display the Handwritten Signature Properties window, which would have Appearance tab.

#### Appearance tab

The color, opacity of the handwritten signature can be edited using Appearance tab of Handwritten Signature Properties window. 

##### Editing color of the signature

The color of the selected handwritten signature will be displayed in the color row in the appearance tab. Selecting the Color would displays the color palette, choosing a color from the color palette and clicking OK will apply the color to the handwritten signature.

The following image illustrates how to change the color of the handwritten signature.

![Edit color of the signature](Handwritten-Signature_images\Handwritten-Signature-2.png)

##### Editing opacity of the signature

The slider displayed in the Appearance tab allows modifying opacity of the selected handwritten signature. You can also modify the opacity of the selected handwritten signature by giving numeric value in the opacity text box.

![Edit opacity of the signature](Handwritten-Signature_images\Handwritten-Signature-3.png)

### Deleting a signature

Selecting delete option from the context menu which is displayed when clicking right on the selected signature would delete the respective signature from the PDF document.

![Delete a signature](Handwritten-Signature_images\Handwritten-Signature-4.png)

## Track the changes in a handwritten signature

You can track the changes occurred in a handwritten signature such as add, select, deselect, move, resize, and remove. The `HandwrittenSignatureChanged` event indicates that a signature is changed in the current document and the `Action` property of the `HandwrittenSignatureChangedEventArgs` provides you the type of changes made in the signature. The following code shows how to wire the event in [PdfViewerControl](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html).

{% tabs %}
{% highlight C# %}

PdfViewerControl pdfViewer = new PdfViewerControl();
pdfViewer.Load("Barcode.pdf");
pdfViewer.HandwrittenSignatureChanged += PdfViewer_HandwrittenSignatureChanged;

private void PdfViewer_HandwrittenSignatureChanged(object sender, HandwrittenSignatureChangedEventArgs e)
{
	//Insert your code that does something
}

{% endhighlight %}

{% highlight vbnet %}

Dim pdfViewer As PdfViewerControl = New PdfViewerControl()
pdfViewer.Load("Barcode.pdf")
AddHandler pdfViewer.HandwrittenSignatureChanged, AddressOf PdfViewer_HandwrittenSignatureChanged

Private Sub PdfViewer_HandwrittenSignatureChanged(ByVal sender As Object, ByVal e As HandwrittenSignatureChangedEventArgs)
'Insert your code that does something
End Sub

{% endhighlight %}
{% endtabs %}

### Get the added handwritten signature

You can get the added handwritten signature as `System.Windows.Shapes.Path` using the `Signature` property of the `HandwrittenSignatureChangedEventArgs`. Refer to the following code example for more details.

{% tabs %}
{% highlight C# %}

private void PdfViewer_HandwrittenSignatureChanged(object sender, HandwrittenSignatureChangedEventArgs e)
{           
	if (e.Action == AnnotationChangedAction.Add)
	{
		//Get the signature
		System.Windows.Shapes.Path signature = e.Signature as System.Windows.Shapes.Path;
	}
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub PdfViewer_HandwrittenSignatureChanged(ByVal sender As Object, ByVal e As HandwrittenSignatureChangedEventArgs)
	If e.Action = AnnotationChangedAction.Add Then
		'Get the signature
		Dim signature As System.Windows.Shapes.Path = TryCast(e.Signature, System.Windows.Shapes.Path)
	End If

{% endhighlight %}

{% endtabs %}

### Track the changes in the location and size of a handwritten signature

You can track the changes in the location and size of a handwritten signature using the ` OldBounds` and `NewBounds` properties of the `HandwrittenSignatureChangedEventArgs`. Refer to the following code example for more details.

{% tabs %}
{% highlight C# %}

private void PdfViewer_HandwrittenSignatureChanged(object sender, HandwrittenSignatureChangedEventArgs e)
{    
	if(e.Action== AnnotationChangedAction.Move)
	{
		//Get the old location
		PointF oldLocation = e.OldBounds.Location;
		//Get the new location
		PointF newLocation = e.NewBounds.Location;
	}       
	else if(e.Action == AnnotationChangedAction.Resize)
	{
		//Get the old size
		SizeF oldSize = e.OldBounds.Size;
		//Get the new size
		SizeF newSize = e.NewBounds.Size;
	}
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub PdfViewer_HandwrittenSignatureChanged(ByVal sender As Object, ByVal e As HandwrittenSignatureChangedEventArgs)
    If e.Action = AnnotationChangedAction.Move Then
		'Get the old location
        Dim oldLocation As PointF = e.OldBounds.Location
		'Get the new location
        Dim newLocation As PointF = e.NewBounds.Location
    ElseIf e.Action = AnnotationChangedAction.Resize Then
        'Get the old size
		Dim oldSize As SizeF = e.OldBounds.Size
        'Get the new size
		Dim newSize As SizeF = e.NewBounds.Size
    End If
End Sub

{% endhighlight %}

{% endtabs %}

### Track the details of the selected handwritten signature

You can track the details such as location, size, and page number of the selected handwritten signature using `HandwrittenSignatureChangedEventArgs`. Refer to the following code example for more details.

{% tabs %}
{% highlight C# %}

private void PdfViewer_HandwrittenSignatureChanged(object sender, HandwrittenSignatureChangedEventArgs e)
{
	if(e.Action== AnnotationChangedAction.Select)
	{
		//Get the page number
		int pageNumber = e.PageNumber;
		//Get the signature location
		PointF location = e.NewBounds.Location;
		//Get the signature size
		SizeF size = e.NewBounds.Size;
	}
}

{% endhighlight %}

{% highlight vbnet %}

Private Sub PdfViewer_HandwrittenSignatureChanged(ByVal sender As Object, ByVal e As HandwrittenSignatureChangedEventArgs)
    If e.Action = AnnotationChangedAction.[Select] Then
		'Get the page number
        Dim pageNumber As Integer = e.PageNumber
		'Get the signature location
        Dim location As PointF = e.NewBounds.Location
		'Get the signature size
        Dim size As SizeF = e.NewBounds.Size
    End If
End Sub

{% endhighlight %}
{% endtabs %}

## Add handwritten signature from code

PDF Viewer allows you to add a signature anywhere in the pages of a PDF document from code behind.

### Add a handwritten signature in a single page

You can add signature in a particular page as `System.Windows.Shapes.Path` by using the `AddHandwrittenSignature` with the page number and the bounds as parameters. The following code explains how to add a handwritten signature at the first page of the PDF document.

{% tabs %}
{% highlight C# %}

private void button_Click(object sender, RoutedEventArgs e)
{
	System.Windows.Shapes.Path signature = new System.Windows.Shapes.Path();
	//Note: Set your signature appearance as Data for the path here.
	//Add signature in the first page of the PDF document at the location: X= 450, Y=750 and with the size: Width=100, Height=100.
	pdfViewer.AddHandwrittenSignature(signature, 1, new RectangleF(450, 750, 100, 100));
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub button_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
    Dim signature As System.Windows.Shapes.Path = New System.Windows.Shapes.Path()
	'Note: Set your signature appearance as Data for the path here.
	'Add signature in the first page of the PDF document at the location: X= 450, Y=750 and with the size: Width=100, Height=100.
    pdfViewer.AddHandwrittenSignature(signature, 1, New RectangleF(450, 750, 100, 100))
End Sub

{% endhighlight %}
{% endtabs %}

### Add a handwritten signature in multiple pages

You can also add a signature in multiple pages of the PDF document at multiple places using the `AddHandwrittenSignature` method with the overload of dictionary with page numbers as keys and the list of bounds as values. The following code explains how to add a handwritten signature at the first and second page of the PDF document with different bounds.

{% tabs %}
{% highlight C# %}

private void button_Click(object sender, RoutedEventArgs e)
{
	System.Windows.Shapes.Path signature = new System.Windows.Shapes.Path();
	//Note: Set your signature appearance using `Data` property of the path here.
	Dictionary<int, List<RectangleF>> bounds = new Dictionary<int, List<RectangleF>>();
	//Add signature bounds for the first page as: X= 450, Y=750, Width=100, Height=100.
	bounds.Add(1, new List<RectangleF>() { new RectangleF(450, 750, 100, 100) });
	//Add signature bounds for the second page as: X= 350, Y=550, Width=200, Height=200
	bounds.Add(2, new List<RectangleF>() { new RectangleF(350, 550, 200, 200) });
	pdfViewer.AddHandwrittenSignature(signature, bounds);
}

{% endhighlight %}
{% highlight vbnet %}

Private Sub button_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)
    Dim signature As System.Windows.Shapes.Path = New System.Windows.Shapes.Path()
	'Note: Set your signature appearance using `Data` property of the path here.
    Dim bounds As Dictionary(Of Integer, List(Of RectangleF)) = New Dictionary(Of Integer, List(Of RectangleF))()
    'Add signature bounds for the first page as: X= 450, Y=750, Width=100, Height=100.
	bounds.Add(1, New List(Of RectangleF)() From {
        New RectangleF(450, 750, 100, 100)
    })	
	'Add signature bounds for the second page as: X= 350, Y=550, Width=200, Height=200.
    bounds.Add(2, New List(Of RectangleF)() From {
        New RectangleF(350, 550, 200, 200)
    })
    pdfViewer.AddHandwrittenSignature(signature, bounds)
End Sub

{% endhighlight %}
{% endtabs %}

## Keyboard shortcuts

The below keyboard shortcuts are available to customize the handwritten signature in the PDF document.

*	Delete key – Deletes the selected signature from the PDF document.
*	Ctrl + Z – Performs undo functionality for recently performed operations.
*	Ctrl + Y – Performs redo functionality for recently performed operations.
