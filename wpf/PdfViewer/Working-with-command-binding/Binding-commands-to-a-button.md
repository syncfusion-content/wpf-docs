---
layout: post
title: Binding commands to a button.
description: Inclusion of annotations in to the PDF document, performs zooming and performs page navigation through XAML binding.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Binding commands to a button

# Magnification operations:

The PdfViewerControl provides the following set of commands to perform magnification.

*   IncreaseZoomCommand
*   DecreaseZoomCommand

N>  
* When executing the IncreaseZoomCommand, the 25% of zoom value has been increased from the current zoom percentage.
* When executing the DecreaseZoomCommand, the 25% of zoom value has been decreased from the current zoom percentage.

The following XAML code shows how to bind the IncreaseZoomCommand to a button.

{% tabs %}
{% highlight xaml %}

    <Button Content="ZoomIn" Command="{Binding ElementName=pdfViewerControl, Path= IncreaseZoomCommand, Mode=OneWay}" />

{% endhighlight %}
{% endtabs %}

The following XAML code shows how to bind the DecreaseZoomCommand to a button.

{% tabs %}
{% highlight xaml %}

    <Button Content="ZoomOut" Command="{Binding ElementName=pdfViewerControl, Path= DecreaseZoomCommand, Mode= OneWay }" />
{% endhighlight %}
{% endtabs %}

# Page Navigations

The below list of commands will be helpful for performing the page navigation operations.

*  FirstPageCommand
*  LastPageCommand
*  PreviousPageCommand
*  NextPageCommand
*  GoToPageCommand

## FirstPageCommand

Navigation to the first page can be achieved by using the FirstPageCommand as shown below.

The following XAML code shows how to bind the FirstPageCommand to a button.

{% tabs %}
{% highlight xaml %}

    <Button Content="Go to first page" Command="{Binding ElementName=pdfViewerControl, Path=FirstPageCommand, Mode= OneWay }" />

{% endhighlight %}
{% endtabs %}


N> 
* If the current page is already the first page of PDF document, then FirstPageCommand does not have any effect.

## LastPageCommand

Navigation to the last page can be achieved by using the LastPageCommand as shown below.

The following XAML code shows how to bind the LastPageCommand to a button.

{% tabs %}
{% highlight xaml %}

    <Button Content="Go to last page" Command="{Binding ElementName=pdfViewerControl, Path=LastPageCommand, Mode= OneWay }" />

{% endhighlight %}
{% endtabs %}

N>
* If the current page is already the last page of PDF document, then LastPageCommand does not have any effect.

## NextPageCommand

NextPageCommand displays the page next to the currently displayed page in the PDF Viewer. 

The following XAML code shows how to bind the NextPageCommand to a button.

{% tabs %}
{% highlight xaml %}

    <Button Content="Go to next page" Command="{Binding ElementName=pdfViewerControl, Path=NextPageCommand, Mode= OneWay }" />

{% endhighlight %}
{% endtabs %}

N>
* If the current page is last page of the PDF document, then NextPageCommand does not have any effect. 

## PreviousPageCommand

PreviousPageCommand displays the page previous to the currently displayed page in the PDF Viewer.

The following XAML code shows how to bind the PreviousPageCommand to a button.

{% tabs %}
{% highlight xaml %}

    <Button Content="Go to previous page" Command="{Binding ElementName=pdfViewerControl, Path= PreviousPageCommand, Mode= OneWay }" />

{% endhighlight %}
{% endtabs %}

N>
*	If the current page is first page of the PDF document, then PreviousPageCommand does not have any effect.

## GoToPageCommand

GoToPageCommand allows you to navigate through the pages of the PDF document. The following code example illustrates the navigation to page 2 of the PDF document.

{% tabs %}
{% highlight xaml %}

    <Button Content="Go to page” Command="{Binding ElementName=pdfViewerControl, Path=GoToPageCommand, Mode= OneWay }" CommandParameter="2" />
{% endhighlight %}
{% endtabs %}

N>
* If the command parameter is some other text or invalid page number, the GoToPageCommand does not have any effect.

# Printing PDF

Printing can be performed by using the Print command.

The following XAML code shows how to bind the PrintCommand to a Button.


{% tabs %}
{% highlight xaml %}

    <Button Content="Print" Command="{Binding ElementName=pdfViewerControl,Path= PrintCommand, Mode= OneWay }" />

{% endhighlight %}
{% endtabs %}

# AnnotationCommand

The AnnotationCommand can be used to set the different types of annotation mode by using the AnnotationParameter in PdfViewer.

The following list of AnnotationCommandParameter values to the AnnotationCommand are used to set the annotation mode.

*    Line
*    Circle
*	 Rectangle
*	 Ink
*	 Strikethrough
*	 Highlight
*	 Underline

N>
*	If the AnnotationCommandParameter value of AnnotationCommand is not equivalent to above mentioned any one of the text, then the annotation mode is set as none. 
*	The AnnotationCommandParameter is not a case sensitive.

## Line Annotation:

The following XAML code shows how to bind the annotation command for line annotation to a Button.

{% tabs %}
{% highlight xaml %}

    <Button Content="Line" CommandParameter="Line" Command="{Binding ElementName=pdfViewerControl, Path=AnnotationCommand, Mode= OneWay }" />

{% endhighlight %}
{% endtabs %}

## Circle Annotation:

The following XAML code shows how to bind the annotation command for circle annotation to a Button.

{% tabs %}
{% highlight xaml %}

    <Button Content="Circle" CommandParameter="Circle " Command="{Binding ElementName=pdfViewerControl, Path=AnnotationCommand, Mode= OneWay }" />

{% endhighlight %}
{% endtabs %}

## Rectangle Annotation:

The following XAML code shows how to bind the annotation command for rectangle annotation to a Button.

{% tabs %}
{% highlight xaml %}

    <Button Content="Rectangle" CommandParameter="Rectangle" Command="{Binding ElementName=pdfViewerControl, Path=AnnotationCommand, Mode= OneWay }" />

{% endhighlight %}
{% endtabs %}

## Ink Annotation:

The following XAML code shows how to bind the annotation command for ink annotation to a Button.

{% tabs %}
{% highlight xaml %}

    <Button Content="Ink" CommandParameter="Ink" Command="{Binding ElementName=pdfViewerControl, Path=AnnotationCommand, Mode= OneWay }" />

{% endhighlight %}
{% endtabs %}

## Strikethrough Annotation:

The following XAML code shows how to bind the annotation command for strikethrough annotation to a Button.

{% tabs %}
{% highlight xaml %}

    <Button Content="Strikethrough" CommandParameter="Strikethrough" Command="{Binding ElementName=pdfViewerControl, Path=AnnotationCommand, Mode= OneWay }" />
{% endhighlight %}
{% endtabs %}

## Highlight Annotation:

The following XAML code shows how to bind the annotation command for highlight annotation to a Button.

{% tabs %}
{% highlight xaml %}

    <Button Content="Highlight" CommandParameter="Highlight" Command="{Binding ElementName=pdfViewerControl, Path=AnnotationCommand, Mode= OneWay }" />
{% endhighlight %}
{% endtabs %}

## Underline Annotation:

The following XAML code shows how to bind the annotation command for underline annotation to a Button.

{% tabs %}
{% highlight xaml %}

    <Button Content="Underline" CommandParameter="Underline" Command="{Binding ElementName=pdfViewerControl, Path=AnnotationCommand, Mode= OneWay }" />
{% endhighlight %}
{% endtabs %}
