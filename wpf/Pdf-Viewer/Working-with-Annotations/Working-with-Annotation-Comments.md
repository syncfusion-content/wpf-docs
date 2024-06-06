---
layout: post
title: Working with annotation comments using WPF PDF Viewer | Syncfusion
description: Learn how to expand or collapse, show or hide the comments pane, and add, edit, or delete annotation comments in the Syncfusion WPF PDF Viewer control.
platform: wpf
control: PDF Viewer
documentation: ug
---

# Working with annotation comments

PDF viewer provides options to add, edit, and delete the comments to the following annotation in the PDF documents:

* Ink.
* Text markups (Highlight, Underline, Squiggly and Strikethrough).
* Shapes (Line, Circle, Rectangle, Arrow, Polygon and Polyline).
* Stamp.
* Text box (Text and Text Callout).
* Sticky note.

![Annotation Comments](Annotation-images\comments.png)

## Expand/Collapse the comments pane

The user can expand or collapse the comments pane of the ‘PdfViewerControl’ by setting the 'CommentSettings.IsExpanded' property to true or false. By default, the value of 'IsExpanded' is false.
Refer to the following code example to expand the comments pane.

{% tabs %}
{% highlight c# %}

Private void button_Click(object sender,RoutedEventArgs e)
{
    //expand the comments pane
    pdfViewer.CommentSettings.IsExpanded = true;
}

{% endhighlight %}
{% highlight VB %}

Private Sub button_Click(sender As Object, e As RoutedEventArgs) 
    'expand the comments pane.
    pdfViewer.CommentSettings.IsExpanded = true
End Sub

{% endhighlight %}
{% endtabs %}

The sample project to expand the comments pane in the PDF Viewer is available in the 'GitHub'

## Show/Hide the comments pane

The user can show or hide the comments pane of the ‘PdfViewerControl’ by setting the 'CommentSettings.IsVisible' property to true or false. By default, the value of 'IsVisible' is true.
Refer to the following code example to hide the comments pane.

{% tabs %}
{% highlight c# %}

Private void button_Click(object sender,RoutedEventArgs e)
{
    //hide the comments pane
    pdfViewer.CommentSettings.IsVisible = false;
}

{% endhighlight %}
{% highlight VB %}

Private Sub button_Click(sender As Object, e As RoutedEventArgs) 
    'hide the comments pane.
    pdfViewer.CommentSettings.IsVisible = false
End Sub

{% endhighlight %}
{% endtabs %}

## Adding a comment to the annotation

Annotation comment, comment replies, and status can be added to the PDF document using the comment panel.

### Adding comments

Annotation comments can be added to the PDF using the comment panel. If the comment panel is expanded, you can select the annotations and add annotation comments using the comment panel. The initial comment of the annotation will be reflected in the popup note and vice versa.

![Adding Comments](Annotation-images\add-comments.png)

### Adding Comment Replies

* The ‘PdfViewerControl’ provides an option to add multiple replies to the comment.
* After adding the annotation comment, you can add a reply to the comment.

### Adding Comment or Reply Status

* Select the Annotation Comments in the comment panel.
* Click the more options button showing in the Comments or reply container.
* Select the Set Status option in the context menu that appears.
* Select the status of the annotation comment in the context menu that appears.

![Comment Status](Annotation-images\comment-status.png)

## Editing the comments and comments replies of the annotations

The comment, comment replies, and status of the annotation can be edited using the comment panel.

### Editing the Comment or Comment Replies

* Select the Annotation Comments in the comment panel.
* Click the More options button showing in the Comments or reply container.
* Select the Edit option in the context menu that appears.
* Now, an editable text box appears. You can change the content of the annotation comment or comment reply.

![Editing the Comments](Annotation-images\edit-comment.png)

### Editing Comment or Reply Status

* Select the Annotation Comments in the comment panel.
* Click the more options button showing in the Comments or reply container.
* Select the Set Status option in the context menu that appears.
* Select the status of the annotation comment in the context menu that appears.
* Status ‘None’ is the default state. If the status is set to ‘None,’ the comments or reply does not appear.

### Delete Comment or Comment Replies

* Select the Annotation Comments in the comment panel.
* Click the more options button shown in the Comments or reply container.
* Select the Delete option in the context menu that appears.

![Deleteing the Comments](Annotation-images\delete-comment.png)