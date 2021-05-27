---
title: Comment in WPF RichTextBox control | Syncfusion
description: Learn here all about Comment support in Syncfusion WPF RichTextBox (SfRichTextBoxAdv) control and more.
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: comment
---
# Comment in WPF RichTextBox (SfRichTextBoxAdv)

A Comment is a note or annotation that an author or reviewer can add to the document. The SfRichTextBoxAdv control supports viewing and editing the comments in the document. It renders the comments present in the document in review pane, similar to the Microsoft Word.
![Comment_img1](Comment_images/Comment_img1.jpeg)

N> Currently, the SfRichTextBoxAdv shows review pane only with Pages layout type.

## UI Commands for accessing comment

The following operations can be performed through command binding in SfRichTextBoxAdv control:

* Insert a new comment.

* Delete an existing comment or delete all the existing comments.

* Navigate to the next comment.

* Navigate to the previous comment.

* Show/Hide review pane.


The following code example demonstrates how to bind commands for accessing comment in SfRichTextBoxAdv document.
{% tabs %}
{% highlight xaml %}
<!-- Binds button to the ShowCommentsCommand -->
<Button Content="Show Comments" Command="RichTextBoxAdv:SfRichTextBoxAdv.ShowCommentsCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the NewCommentCommand -->
<Button Content="New Comment" Command="RichTextBoxAdv:SfRichTextBoxAdv.NewCommentCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the DeleteCommentCommand -->
<Button Content="Delete Comment" Command="RichTextBoxAdv:SfRichTextBoxAdv.DeleteCommentCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the DeleteAllCommentsCommand -->
<Button Content="Delete All Comments" Command="RichTextBoxAdv:SfRichTextBoxAdv.DeleteAllCommentsCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the PreviousCommentCommand -->
<Button Content="Previous Comment" Command="RichTextBoxAdv:SfRichTextBoxAdv.PreviousCommentCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />
<!-- Binds button to the NextCommentCommand -->
<Button Content="Next Comment" Command="RichTextBoxAdv:SfRichTextBoxAdv.NextCommentCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" />


{% endhighlight %}

{% endtabs %}

## Customizing comment visual style

The SfRichTextBoxAdv provides event support to notify whenever a comment is added to the document. With the help of it, you can customize the visual style for the comment. You can also set the author and initial of the comment.
The following code example demonstrates how to customize comment visual style using event.
{% tabs %}
{% highlight c# %}
// Hooks the CommentAdding event of RichTextBoxAdv.
richTextBoxAdv.CommentAdding += RichTextBoxAdv_CommentAdding;

// Unhooks the CommentAdding event of RichTextBoxAdv.
richTextBoxAdv.CommentAdding -= RichTextBoxAdv_CommentAdding;

// Handles the CommentAdding event of the richTextBoxAdv control.
private void RichTextBoxAdv_CommentAdding(object obj, CommentAddingEventArgs args)
{
    if (!isFileLoading)
    {
        //Defines the author and initial for the comment.
        args.Comment.Author = "Peter";
        args.Comment.Initial = "Franken";
    }

    // Defines the background brush for the comment.
    args.VisualStyle.BackgroundBrush = new SolidColorBrush(Color.FromArgb(0xff, 0xff, 0xa8, 0xa8));

    // Defines the border brush for the comment.
    args.VisualStyle.BorderBrush = new SolidColorBrush(Color.FromArgb(0xff, 0xFF, 0x01, 0x01));

    // Defines the highlight color for the commented content.
    args.VisualStyle.HighlightColor = Color.FromArgb(0xff, 0xFf, 0xa8, 0x8);

}



{% endhighlight %}
{% highlight VB %}
' Hooks the CommentAdding event of RichTextBoxAdv.
AddHandler richTextBoxAdv.CommentAdding, AddressOf RichTextBoxAdv_CommentAdding

' Unhooks the CommentAdding event of RichTextBoxAdv.
RemoveHandler richTextBoxAdv.CommentAdding, AddressOf RichTextBoxAdv_CommentAdding

' Handles the CommentAdding event of the richTextBoxAdv control.
Private Sub RichTextBoxAdv_CommentAdding(obj As Object, args As CommentAddingEventArgs)
	If Not isFileLoading Then
		'Defines the author and initial for the comment.
		args.Comment.Author = "Peter"
		args.Comment.Initial = "Franken"
	End If

	' Defines the background brush for the comment.
	args.VisualStyle.BackgroundBrush = New SolidColorBrush(Color.FromArgb(&Hff, &Hff, &Ha8, &Ha8))

	' Defines the border brush for the comment.
	args.VisualStyle.BorderBrush = New SolidColorBrush(Color.FromArgb(&Hff, &Hff, &H1, &H1))

	' Defines the highlight color for the commented content.
	args.VisualStyle.HighlightColor = Color.FromArgb(&Hff, &Hff, &Ha8, &H8)

End Sub


{% endhighlight %}
{% endtabs %}
![Comment_img2](Comment_images/Comment_img2.jpeg)

