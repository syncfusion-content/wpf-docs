---
layout: post
title: Working with Commands in WPF Pdf Viewer control | Syncfusion
description: Learn about Working with Commands support in Syncfusion Essential Studio WPF Pdf Viewer control, its elements and more.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Working with Commands in WPF Pdf Viewer

## Page Navigations

The below list of commands will be helpful for performing the page navigation operations.

*  [FirstPageCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_FirstPageCommand)
*  [LastPageCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_LastPageCommand)
*  [PreviousPageCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_PreviousPageCommand)
*  [NextPageCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_NextPageCommand)
*  [GoToPageCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_GoToPageCommand)

### FirstPageCommand

Navigation to the first page can be achieved by using the FirstPageCommand as shown below.

The following XAML code shows how to bind the FirstPageCommand to a button.

{% tabs %}
{% highlight xaml %}

	<Syncfusion:PdfViewerControl x:Name="pdfViewerControl" />
    <Button Content="Go to first page" Height="20" Width="100" Command="{Binding ElementName=pdfViewerControl, Path=FirstPageCommand, Mode= OneWay }" />

{% endhighlight %}
{% endtabs %}


N> 
* If the current page is already the first page of PDF document, then FirstPageCommand does not have any effect.

### LastPageCommand

Navigation to the last page can be achieved by using the LastPageCommand as shown below.

The following XAML code shows how to bind the LastPageCommand to a button.

{% tabs %}
{% highlight xaml %}

	<Syncfusion:PdfViewerControl x:Name="pdfViewerControl" />
    <Button Content="Go to last page" Height="20" Width="100" Command="{Binding ElementName=pdfViewerControl, Path=LastPageCommand, Mode= OneWay }" />

{% endhighlight %}
{% endtabs %}

N>
* If the current page is already the last page of PDF document, then LastPageCommand does not have any effect.

### NextPageCommand

NextPageCommand displays the page next to the currently displayed page in the PDF Viewer. 

The following XAML code shows how to bind the NextPageCommand to a button.

{% tabs %}
{% highlight xaml %}

	<Syncfusion:PdfViewerControl x:Name="pdfViewerControl" />
    <Button Content="Go to next page" Height="20" Width="100" Command="{Binding ElementName=pdfViewerControl, Path=NextPageCommand, Mode= OneWay }" />

{% endhighlight %}
{% endtabs %}

N>
* If the current page is last page of the PDF document, then NextPageCommand does not have any effect. 

### PreviousPageCommand

PreviousPageCommand displays the page previous to the currently displayed page in the PDF Viewer.

The following XAML code shows how to bind the PreviousPageCommand to a button.

{% tabs %}
{% highlight xaml %}

	<Syncfusion:PdfViewerControl x:Name="pdfViewerControl" />
    <Button Content="Go to previous page" Height="20" Width="100" Command="{Binding ElementName=pdfViewerControl, Path= PreviousPageCommand, Mode= OneWay }" />

{% endhighlight %}
{% endtabs %}

N>
*	If the current page is first page of the PDF document, then PreviousPageCommand does not have any effect.

### GoToPageCommand

GoToPageCommand allows you to navigate through the pages of the PDF document. The following code example illustrates the navigation to page 2 of the PDF document.

{% tabs %}
{% highlight xaml %}

	<Syncfusion:PdfViewerControl x:Name="pdfViewerControl" />
    <Button Content="Go to page” Height="20" Width="60" Command="{Binding ElementName=pdfViewerControl, Path=GoToPageCommand, Mode= OneWay }" CommandParameter="2" />
{% endhighlight %}
{% endtabs %}

N>
* If the command parameter is some other text or invalid page number, the GoToPageCommand does not have any effect.

## Page Rotation commands

The below list of commands helps to rotate the specific pages in a PDF document. 

*  [RotatePagesCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PageOrganizer.html#Syncfusion_Windows_PdfViewer_PageOrganizer_RotatePagesCommand)
*  [RotatePagesClockwiseCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PageOrganizer.html#Syncfusion_Windows_PdfViewer_PageOrganizer_RotatePagesClockwiseCommand)
*  [RotatePagesCounterclockwiseCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PageOrganizer.html#Syncfusion_Windows_PdfViewer_PageOrganizer_RotatePagesCounterclockwiseCommand)

### RotatePagesCommand

We can rotate the pages to a specified angle regardless of their current rotation angle(0,90,180,270).

The following C# code shows how to rotate the pages to 180-degree angle 

{% tabs %}
{% highlight c# %}

<!--The below code rotates the 6 th page to 180 degree in clockwise direction -->
pdfViewer.PageOrganizer.RotatePagesCommand.Execute(new object[] { new int[] {  5 }, PdfPageRotateAngle.RotateAngle180 });

{% endhighlight %}
{% endtabs %}

### RotatePagesClockwiseCommand

We can rotate the pages 90 degrees with respect to the current rotation angle in a clockwise direction.

The following C# code shows how to rotate the pages in a clockwise direction using the command RotatePagesClockwiseCommand

{% tabs %}
{% highlight c# %}

<!--The below code rotates the 1 and 2 page to 90 degree in clockwise direction-->
pdfViewer.PageOrganizer.RotatePagesClockwiseCommand.Execute(new int[] { 0, 1 });

{% endhighlight %}
{% endtabs %}

### RotatePagesCounterclockwiseCommand

We can rotate the pages only 90 degrees with respect to the current rotation angle in a counterclockwise direction.

The following C# code shows how to rotate the pages in a counterclockwise direction using the command RotatePagesCounterclockwiseCommand

{% tabs %}
{% highlight c# %}

<!--The below code rotates teh 1 and 2 page to 90 degree in counter clockwise direction-->
pdfViewer.PageOrganizer.RotatePagesCounterclockwiseCommand.Execute(new int[] { 0, 1 });

{% endhighlight %}
{% endtabs %}

## RemovePagesCommand

Removing the specific pages can be achieved using the RemovePagesCommand. To achieve this functionality we have to define the code in the code-behind(i.e In a button click event

The following C# code shows how to remove pages using the [RemovePagesCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PageOrganizer.html#Syncfusion_Windows_PdfViewer_PageOrganizer_RemovePagesCommand) that is bonded to the button click event

{% tabs %}
{% highlight c# %}

private void Button_Click(object sender, RoutedEventArgs e)
  {
          // This line removes the 3 rd page in the PDF
          pdfViewer.PageOrganizer.RemovePagesCommand.Execute(new int[] {2});
  }	

{% endhighlight %}
{% endtabs %}

## Magnification operations

The PdfViewerControl provides the following set of commands to perform magnification.

*   [IncreaseZoomCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_IncreaseZoomCommand)
*   [DecreaseZoomCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_DecreaseZoomCommand)

### IncreaseZoomCommand

IncreaseZoomCommand increases the current zoom percentage by 25%.

The following XAML code shows how to bind the IncreaseZoomCommand to a button.

{% tabs %}
{% highlight xaml %}

	<Syncfusion:PdfViewerControl x:Name="pdfViewerControl" />
    <Button Content="ZoomIn" Height="20" Width="60" Command="{Binding ElementName=pdfViewerControl, Path= IncreaseZoomCommand, Mode=OneWay}" />

{% endhighlight %}
{% endtabs %}

### DecreaseZoomCommand

DecreaseZoomCommand decreases the current zoom percentage by 25%.

The following XAML code shows how to bind the DecreaseZoomCommand to a button.

{% tabs %}
{% highlight xaml %}

	<Syncfusion:PdfViewerControl x:Name="pdfViewerControl" />
    <Button Content="ZoomOut" Height="20" Width="60" Command="{Binding ElementName=pdfViewerControl, Path= DecreaseZoomCommand, Mode= OneWay }" />
{% endhighlight %}
{% endtabs %}

## Text Search Operations

The below two commands will help perform text searching

*   [SearchNextCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_SearchNextCommand)
*   [SearchPreviousCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_SearchPreviousCommand)

### SearchNextCommand

Finding the next occurrence of a text will be achieved using the SearchNextCommand.

The following XAML code shows how to bind the SearchNextCommand to a button.

{% tabs %}
{% highlight xaml %}

     <Syncfusion:PdfViewerControl  x:Name="PdfViewer" />
     <Button Content="Search text" Height="20" Width="100" Command="{Binding ElementName=PdfViewer,Path=SearchNextCommand,Mode=OneWay}" CommandParameter="annotation"/>

{% endhighlight %}
{% endtabs %}

### SearchPreviousCommand

Finding a previous occurrence of a text will be achieved using the SearchPreviousCommand 

The following XAML code shows how to bind the SearchPreviousCommand to a button.

{% tabs %}
{% highlight xaml %}

     <Syncfusion:PdfViewerControl  x:Name="PdfViewer" />
     <Button Content="Search text" Height="20" Width="100" Command="{Binding ElementName=PdfViewer,Path=SearchPreviousCommand,Mode=OneWay}" CommandParameter="annotation"/>

{% endhighlight %}
{% endtabs %}

N>
* If the Searched text is not found a dialogue box will prompt which shows No matches were found

## AnnotationCommand

The [AnnotationCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_AnnotationCommand) can be used to set the different types of annotation mode by using the AnnotationParameter in PdfViewer.

The following list of AnnotationCommandParameter values to the AnnotationCommand are used to set the annotation mode.

*    Line
*    Circle
*	 Rectangle
*	 Arrow
*	 Ink
*	 Strikethrough
*	 Highlight
*	 Underline

N>
*	If the AnnotationCommandParameter value of AnnotationCommand is not equivalent to above mentioned any one of the text, then the annotation mode is set as none. 
*	The AnnotationCommandParameter is not a case sensitive.

### Line Annotation

The following XAML code shows how to bind the annotation command for line annotation to a Button.

{% tabs %}
{% highlight xaml %}

	<Syncfusion:PdfViewerControl x:Name="pdfViewerControl" />
    <Button Content="Line" Height="20" Width="60" CommandParameter="Line" Command="{Binding ElementName=pdfViewerControl, Path=AnnotationCommand, Mode= OneWay }" />

{% endhighlight %}
{% endtabs %}

### Circle Annotation

The following XAML code shows how to bind the annotation command for circle annotation to a Button.

{% tabs %}
{% highlight xaml %}

	<Syncfusion:PdfViewerControl x:Name="pdfViewerControl" />
    <Button Content="Circle" Height="20" Width="60" CommandParameter="Circle " Command="{Binding ElementName=pdfViewerControl, Path=AnnotationCommand, Mode= OneWay }" />

{% endhighlight %}
{% endtabs %}

### Rectangle Annotation

The following XAML code shows how to bind the annotation command for rectangle annotation to a Button.

{% tabs %}
{% highlight xaml %}

	<Syncfusion:PdfViewerControl x:Name="pdfViewerControl" />
    <Button Content="Rectangle" Height="20" Width="60" CommandParameter="Rectangle" Command="{Binding ElementName=pdfViewerControl, Path=AnnotationCommand, Mode= OneWay }" />

{% endhighlight %}
{% endtabs %}

### Arrow Annotation

The following XAML code shows how to bind the annotation command for arrow annotation to a Button.

{% tabs %}
{% highlight xaml %}

	<Syncfusion:PdfViewerControl x:Name="pdfViewerControl"/>	
    <Button Content="Arrow" CommandParameter="Arrow" Command="{Binding ElementName=pdfViewerControl, Path=AnnotationCommand, Mode= OneWay }" />

{% endhighlight %}
{% endtabs %}

### Ink Annotation

The following XAML code shows how to bind the annotation command for ink annotation to a Button.

{% tabs %}
{% highlight xaml %}

	<Syncfusion:PdfViewerControl x:Name="pdfViewerControl" />
    <Button Content="Ink" Height="20" Width="60" CommandParameter="Ink" Command="{Binding ElementName=pdfViewerControl, Path=AnnotationCommand, Mode= OneWay }" />

{% endhighlight %}
{% endtabs %}

### Strikethrough Annotation

The following XAML code shows how to bind the annotation command for strikethrough annotation to a Button.

{% tabs %}
{% highlight xaml %}

	<Syncfusion:PdfViewerControl x:Name="pdfViewerControl" />
    <Button Content="Strikethrough" Height="20" Width="60" CommandParameter="Strikethrough" Command="{Binding ElementName=pdfViewerControl, Path=AnnotationCommand, Mode= OneWay }" />
	
{% endhighlight %}
{% endtabs %}

### Highlight Annotation

The following XAML code shows how to bind the annotation command for highlight annotation to a Button.

{% tabs %}
{% highlight xaml %}

	<Syncfusion:PdfViewerControl x:Name="pdfViewerControl" />
    <Button Content="Highlight" Height="20" Width="60" CommandParameter="Highlight" Command="{Binding ElementName=pdfViewerControl, Path=AnnotationCommand, Mode= OneWay }" />
	
{% endhighlight %}
{% endtabs %}

### Underline Annotation

The following XAML code shows how to bind the annotation command for underline annotation to a Button.

{% tabs %}
{% highlight xaml %}

	<Syncfusion:PdfViewerControl x:Name="pdfViewerControl" />
    <Button Content="Underline" Height="20" Width="60" CommandParameter="Underline" Command="{Binding ElementName=pdfViewerControl, Path=AnnotationCommand, Mode= OneWay }" />
	
{% endhighlight %}
{% endtabs %}

## Undo/Redo Command

The UndoCommand and RedoCommand provided by Syncfusion enable users to revert or reapply their recent actions on the PDF document

*   [UndoCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_UndoCommand)
*   [RedoCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_RedoCommand)

### UndoCommand

You can undo your last action by using the UndoCommand.

The following XAML code shows how to bind the UndoCommand to a button.

{% tabs %}
{% highlight xaml %}

        <Syncfusion:PdfViewerControl Grid.Row="1" x:Name="PdfViewer" />
        <Button  Content="undo" Height="20" Width="100" Command="{Binding ElementName=PdfViewer,Path=UndoCommand,Mode=OneWay}"/>
	
{% endhighlight %}
{% endtabs %}

### RedoCommand

You can redo the last undone action by using the RedoCommand.

The following XAML code shows how to bind the RedoCommand to a button.

{% tabs %}
{% highlight xaml %}

        <Syncfusion:PdfViewerControl Grid.Row="1" x:Name="PdfViewer" />
        <Button  Content="Redo" Height="20" Width="100" Command="{Binding ElementName=PdfViewer,Path=RedoCommand,Mode=OneWay}"/>
	
{% endhighlight %}
{% endtabs %}

## Printing PDF

Printing can be performed by using the Print command.

The following XAML code shows how to bind the [PrintCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_PrintCommand) to a Button.


{% tabs %}
{% highlight xaml %}

	<Syncfusion:PdfViewerControl x:Name="pdfViewerControl" />
    <Button Content="Print" Height="20" Width="60" Command="{Binding ElementName=pdfViewerControl,Path= PrintCommand, Mode= OneWay }" />

{% endhighlight %}
{% endtabs %}

## Save Document Command

You can save the PDF file in the given file path using the `SaveDocumentCommand`. The following code shows how to save the PDF file by executing the command and to the pass the file path as command parameter.

{% tabs %}
{% highlight c# %}

pdfViewerControl.SaveDocumentCommand.Execute(@"C:\temp\Output.pdf");

{% endhighlight %}
{% endtabs %}

## Unload Command

Unloading a document in runtime can be easily achieved using the unload command

The following XAML code shows how to bind the [UnloadCommand](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.PdfViewer.PdfViewerControl.html#Syncfusion_Windows_PdfViewer_PdfViewerControl_UnloadCommand) to a button

{% tabs %}
{% highlight xaml %}

	 <Syncfusion: PdfViewerControl Grid.Row="1" x:Name="PdfViewer" />
     <Button  Content="undo" Height="20" Width="100" Command="{Binding ElementName=PdfViewer,Path= Unload,Mode=OneWay}"/>

{% endhighlight %}
{% endtabs %}

N> You can refer to our [WPF PDF Viewer](https://www.syncfusion.com/wpf-controls/pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [WPF PDF Viewer example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the pdfviewer.