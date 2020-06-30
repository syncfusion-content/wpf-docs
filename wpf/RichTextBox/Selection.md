---
title: Selection | SfRichTextBoxAdv | WPF | Syncfusion
description: This section illustrates how to select a portion of the document through supported APIs in WPF RichTextBox control
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: selection
---
# Selection in WPF RichTextBox

The SfRichTextBoxAdv supports selecting a portion of the document either through UI interactions by using mouse, touch, keyboard or through supported APIs.
The following sample code demonstrates how to retrieve text position from document using paragraph instance and offset value.
{% tabs %}
{% highlight c# %}
// Gets the first section of the document.
SectionAdv sectionAdv = richTextBoxAdv.Document.Sections[0];


{% endhighlight %}
{% highlight VB %}
'Gets the first section of the document
Dim sectionAdv As SectionAdv = richTextBoxAdv.Document.Sections(0)


{% endhighlight %}

{% endtabs %}


{% tabs %}
{% highlight c# %}
// Gets the first block from the section, which is a paragraph.
ParagraphAdv paragraphAdv = sectionAdv.Blocks[0] as ParagraphAdv;
// Gets the text position of the specified paragraph at offset 24. 
// TextPosition is returned as null, if no such paragraph or offset exists in the document.
TextPosition startPosition = richTextBoxAdv.Document.GetTextPosition(paragraphAdv, 24);


{% endhighlight %}
{% highlight VB %}
' Gets the first block from the section, which is a paragraph.
Dim paragraphAdv As ParagraphAdv = TryCast(sectionAdv.Blocks(0), ParagraphAdv)
' Gets the text position of the specified paragraph at offset 24. 
' TextPosition is returned as null, if no such paragraph or offset exists in the document.
Dim startPosition As TextPosition = richTextBoxAdv.Document.GetTextPosition(paragraphAdv, 24)


{% endhighlight %}

{% endtabs %}

{% tabs %}
{% highlight c# %}
// Gets the third block of a section, which is table.
TableAdv tableAdv = sectionAdv.Blocks[2] as TableAdv;
// Gets the third block from second row second cell of the table, which is paragraph.
ParagraphAdv paragraphAdv = tableAdv.Rows[1].Cells[1].Blocks[2] as ParagraphAdv;
TextPosition position = richTextBoxAdv.Document.GetTextPosition(paragraphAdv, 12);


{% endhighlight %}
{% highlight VB %}
' Gets the third block of a section, which is table.
Dim tableAdv As TableAdv = TryCast(sectionAdv.Blocks(2), TableAdv)
' Gets the third block from second row second cell of the table, which is paragraph.
Dim paragraphAdv As ParagraphAdv = TryCast(tableAdv.Rows(1).Cells(1).Blocks(2), ParagraphAdv)
Dim position As TextPosition = richTextBoxAdv.Document.GetTextPosition(paragraphAdv, 12)


{% endhighlight %}

{% endtabs %}

The following sample code demonstrates how to retrieve text position from document using hierarchical index.
{% tabs %}
{% highlight c# %}
/*
The hierarchical index should be given as "section-index;block-index;offset-in-paragraph"
If block in the index is paragraph, then next value is considered as offset and position is retrieved.
For example "0;0;1" gets text position of Paragraph (first block of first section) at the offset=1.
If block in the index is table, then next value is considered as row index and following value as cell index.
The value after cell is again a block index. Then the same process continues.
"table-index;row-index;cell-index;block-index;"
For example "0;2;1;1;0;21" gets text position of Paragraph at first block of second cell of second row of table (at third block of first section) at the offset=21.
If offset value is followed by "C" which stands for comment, then the comment is retrieved which is followed by block index in comment. Then the process of retrieving paragraph from block index continues.
paragraph-index;offset-in-paragraph;C;block-index;offset-in-paragraph
For example "0;3;16;C;2;6", gets text position of Paragraph at third block of comment (present at offset = 16 in paragraph at third block of first section) at the offset=6.
*/
// Gets the text position from the document based on hierarchical index.
TextPosition position = richTextBoxAdv.Document.GetTextPosition("0;0;24");
/* Here text position returned should be first section's first block (which is paragraph) and offset=24. */


{% endhighlight %}
{% highlight VB %}
'
'The hierarchical index should be given as "section-index;block-index;offset-in-paragraph"
'If block in the index is paragraph, then next value is considered as offset and position is retrieved.
'For example "0;0;1" gets text position of Paragraph (first block of first section) at the offset=1.
'If block in the index is table, then next value is considered as row index and following value as cell index.
'The value after cell is again a block index. Then the same process continues.
'"table-index;row-index;cell-index;block-index;"
'For example "0;2;1;1;0;21" gets text position of Paragraph at first block of second cell of second row of table (at third block of first section) at the offset=21.
'If offset value is followed by "C" which stands for comment, then the comment is retrieved which is followed by block index in comment. Then the process of retrieving paragraph from block index continues.
'paragraph-index;offset-in-paragraph;C;block-index;offset-in-paragraph
'For example "0;3;16;C;2;6", gets text position of Paragraph at third block of comment (present at offset = 16 in paragraph at third block of first section) at the offset=6.
'

' Gets the text position from the document based on hierarchical index.
Dim position As TextPosition = richTextBoxAdv.Document.GetTextPosition("0;0;24")
' Here text position returned should be first section's first block (which is paragraph) and offset=24. 


{% endhighlight %}

{% endtabs %}

The following sample code demonstrates how to move selection start and selection end both at a specific text position.
{% tabs %}
{% highlight c# %}
// Makes an empty selection at the specific text position.
richTextBoxAdv.Selection.Select(position, position);


{% endhighlight %}
{% highlight VB %}
' Makes an empty selection at the specific text position.
richTextBoxAdv.Selection.[Select](position, position)


{% endhighlight %}

{% endtabs %}

The following sample code demonstrates how to select a portion of document.
{% tabs %}
{% highlight c# %}
// Retrieves the position of the first paragraph start.
TextPosition startPosition = richTextBoxAdv.Document.GetTextPosition("0;0;0");
// Retrieves the position of the first paragraph at offset=20.
TextPosition endPosition = richTextBoxAdv.Document.GetTextPosition("0;0;20");
// Selects the text positions in forward direction.
richTextBoxAdv.Selection.Select(startPosition, endPosition);


{% endhighlight %}
{% highlight VB %}
' Retrieves the position of the first paragraph start.
Dim startPosition As TextPosition = richTextBoxAdv.Document.GetTextPosition("0;0;0")
' Retrieves the position of the first paragraph at offset=20.
Dim endPosition As TextPosition = richTextBoxAdv.Document.GetTextPosition("0;0;20")
' Selects the text positions in forward direction.
richTextBoxAdv.Selection.[Select](startPosition, endPosition)


{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
// Selects the text positions in reverse direction.
richTextBoxAdv.Selection.Select(endPosition, startPosition);


{% endhighlight %}
{% highlight VB %}
' Selects the text positions in reverse direction.
richTextBoxAdv.Selection.[Select](endPosition, startPosition)


{% endhighlight %}

{% endtabs %}

N> You can select a text position within a comment with another text position within the same comment only. It is not possible to select a text position within comment with a text position that exists outside of that comment.

## Multi Selection

The SfRichTextBoxAdv also supports selecting different portions of the document at a time. The following code example demonstrates how to perform multi selection in SfRichTextBoxAdv.
{% tabs %}
{% highlight c# %}
// Retrieves the position of the first paragraph start.
TextPosition startPosition1 = richTextBoxAdv.Document.GetTextPosition("0;0;0");
// Retrieves the position of the first paragraph at offset=20.
TextPosition endPosition1 = richTextBoxAdv.Document.GetTextPosition("0;0;20");
// Retrieves the position of the third paragraph start.
TextPosition startPosition2 = richTextBoxAdv.Document.GetTextPosition("0;2;0");
// Retrieves the position of the third paragraph at offset=20.
TextPosition endPosition2 = richTextBoxAdv.Document.GetTextPosition("0;2;20");
// Selects the first paragraph and third paragraph at a time, leaving second paragraph.
richTextBoxAdv.Selection.SelectionRanges.Add(startPosition1, endPosition1);
richTextBoxAdv.Selection.SelectionRanges.Add(startPosition2, endPosition2);


{% endhighlight %}
{% highlight VB %}
' Retrieves the position of the first paragraph start.
Dim startPosition1 As TextPosition = richTextBoxAdv.Document.GetTextPosition("0;0;0")
' Retrieves the position of the first paragraph at offset=20.
Dim endPosition1 As TextPosition = richTextBoxAdv.Document.GetTextPosition("0;0;20")
' Retrieves the position of the third paragraph start.
Dim startPosition2 As TextPosition = richTextBoxAdv.Document.GetTextPosition("0;2;0")
' Retrieves the position of the third paragraph at offset=20.
Dim endPosition2 As TextPosition = richTextBoxAdv.Document.GetTextPosition("0;2;20")
' Selects the first paragraph and third paragraph at a time, leaving second paragraph.
richTextBoxAdv.Selection.SelectionRanges.Add(startPosition1, endPosition1)
richTextBoxAdv.Selection.SelectionRanges.Add(startPosition2, endPosition2)


{% endhighlight %}

{% endtabs %}

## Apply Formatting for selection

The SfRichTextBoxAdv supports the following format properties that can be applied for selection contents.
Character Format-bold, italic, font size, font family, font color, highlight color, underline, strikethrough, subscript, and superscript.
Paragraph Format-before and after spacing, first line, left and right indenting, text justification, line spacing, and multilevel list.
Selection Format-page size and page margin.
The following sample code demonstrates how to apply subscript format for the selected content.
{% tabs %}
{% highlight c# %}
// Applies subscript format for the selected text contents.
richTextBoxAdv.Selection.CharacterFormat.BaselineAlignment = Syncfusion.Windows.Controls.RichTextBoxAdv.BaselineAlignment.Subscript;


{% endhighlight %}
{% highlight VB %}
' Applies subscript format for the selected text contents.
richTextBoxAdv.Selection.CharacterFormat.BaselineAlignment = Syncfusion.Windows.Controls.RichTextBoxAdv.BaselineAlignment.Subscript


{% endhighlight %}
{% endtabs %}

The following sample code demonstrates how to apply after spacing for the selected paragraphs.
{% tabs %}
{% highlight c# %}
// Applies after spacing for the selected paragraphs.
richTextBoxAdv.Selection.ParagraphFormat.AfterSpacing = 24;


{% endhighlight %}
{% highlight VB %}
' Applies after spacing for the selected paragraphs.
richTextBoxAdv.Selection.ParagraphFormat.AfterSpacing = 24


{% endhighlight %}

{% endtabs %}

The following sample code demonstrates how to apply page margin for the selected sections.
{% tabs %}
{% highlight c# %}
// Applies page margin for the selected sections.
richTextBoxAdv.Selection.SectionFormat.PageMargin = new Thickness(96, 48, 96, 48);


{% endhighlight %}
{% highlight VB %}
' Applies page margin for the selected sections.
richTextBoxAdv.Selection.SectionFormat.PageMargin = New Thickness(96, 48, 96, 48)


{% endhighlight %}

{% endtabs %}

## Binding Selection format properties

The SfRichTextBoxAdv provides support to bind the rich-text format options of selection content. 
The following code sample demonstrates how to bind the bold format option of SfRichTextBoxAdv.
{% tabs %}
{% highlight xaml %}
<!-- Binds the toggle button to Selection bold character format -->
<ToggleButton x:Name="toggleButton" Content="Bold" IsChecked="{Binding Path=Selection.CharacterFormat.Bold, Mode=TwoWay, ElementName=richTextBoxAdv}" />


{% endhighlight %}
{% highlight c# %}
// Initializes the new binding for toggle bold.
Binding binding = new Binding() { Source = richTextBoxAdv, Path = new PropertyPath("Selection.CharacterFormat.Bold"), Mode = BindingMode.TwoWay };

// Binds the IsChecked property to Selection.CharacterFormat.Bold property of RichTextBoxAdv.
toggleButton.SetBinding(ToggleButton.IsCheckedProperty, binding);

{% endhighlight %}
{% highlight VB %}
' Initializes the new binding for toggle bold.
Dim binding As New Binding() With { _
	Key .Source = richTextBoxAdv, _
	Key .Path = New PropertyPath("Selection.CharacterFormat.Bold"), _
	Key .Mode = BindingMode.TwoWay _
}

' Binds the IsChecked property to Selection.CharacterFormat.Bold property of RichTextBoxAdv.
toggleButton.SetBinding(ToggleButton.IsCheckedProperty, binding)


{% endhighlight %}

{% endtabs %}

The following code sample demonstrates how to bind the bold format option of SfRichTextBoxAdv.
{% tabs %}
{% highlight xaml %}
<!—Binds IsChecked property of toggle button to Selection text alignment paragraph format -->
<ToggleButton x:Name="toggleButton" Content="Left" IsChecked="{Binding ElementName=richTextBoxAdv,Path=Selection.ParagraphFormat.TextAlignment,Converter={StaticResource LeftAlignmentToggleConverter}}"/>


{% endhighlight %}
{% highlight c# %}
//Initializes the new binding for toggle text alignment property as left.
Binding binding = new Binding() { Source = richTextBoxAdv, Path = new PropertyPath("Selection.ParagraphFormat.TextAlignment"), Mode = BindingMode.TwoWay, Converter = new LeftAlignmentToggleConverter() };

//Binds the IsChecked property to Selection.ParagraphFormat.TextAlignment property of RichTextBoxAdv.
toggleButton.SetBinding(ToggleButton.IsCheckedProperty, binding);


{% endhighlight %}
{% highlight VB %}
'Initializes the new binding for toggle text alignment property as left.
Dim binding As New Binding() With { _
	Key .Source = richTextBoxAdv, _
	Key .Path = New PropertyPath("Selection.ParagraphFormat.TextAlignment"), _
	Key .Mode = BindingMode.TwoWay, _
	Key .Converter = New LeftAlignmentToggleConverter() _
}

'Binds the IsChecked property to Selection.ParagraphFormat.TextAlignment property of RichTextBoxAdv.
toggleButton.SetBinding(ToggleButton.IsCheckedProperty, binding)


{% endhighlight %}

{% endtabs %}

## Keyboard shortcuts to perform selection

The following keyboard shortcuts are supported by SfRichTextBoxAdv for navigation.
<table><tr><td>Navigation Shortcut<br/></td><td>Description<br/></td></tr><tr><td>Right Arrow<br/></td><td>Navigates to one position forward.<br/></td></tr><tr><td>Left Arrow<br/></td><td>Navigates to one position backward.<br/></td></tr><tr><td>Down Arrow<br/></td><td>Navigates to the same position at next line.<br/></td></tr><tr><td>Up Arrow<br/></td><td>Navigates to the same position at previous line.<br/></td></tr><tr><td>Home<br/></td><td>Navigates to start of the current line.<br/></td></tr><tr><td>End<br/></td><td>Navigates to end of the current line.<br/></td></tr><tr><td>CTRL + Home<br/></td><td>Navigates to the document start position.<br/></td></tr><tr><td>CTRL + End<br/></td><td>Navigates to the document end position.<br/></td></tr><tr><td>CTRL + Right<br/></td><td>Navigates to the next word start position.<br/></td></tr><tr><td>CTRL + Left<br/></td><td>Navigates to the current word start position.<br/></td></tr><tr><td>CTRL + Down<br/></td><td>Navigates to the next paragraph start position.<br/></td></tr><tr><td>CTRL + Up<br/></td><td>Navigates to the current paragraph start position.<br/></td></tr></table>

The following keyboard shortcuts are supported by SfRichTextBoxAdv for selection.
<table><tr><td>Selection Shortcut<br/></td><td>Description<br/></td></tr><tr><td>CTRL + Right Arrow<br/></td><td>Extends selection to one position forward.<br/></td></tr><tr><td>CTRL + Left Arrow<br/></td><td>Extends selection to one position backward.<br/></td></tr><tr><td>CTRL + Down Arrow<br/></td><td>Extends selection to the same position at next line.<br/></td></tr><tr><td>CTRL + Up Arrow<br/></td><td>Extends selection to the same position at previous line.<br/></td></tr><tr><td>SHIFT + Home<br/></td><td>Extends selection to start of the current line.<br/></td></tr><tr><td>SHIFT + End<br/></td><td>Extends selection to end of the current line.<br/></td></tr><tr><td>CTRL + SHIFT + Home<br/></td><td>Extends selection to the document start position.<br/></td></tr><tr><td>CTRL + SHIFT + End<br/></td><td>Extends selection to the document end position.<br/></td></tr><tr><td>CTRL + SHIFT + Right<br/></td><td>Extends selection to the current word end position.<br/></td></tr><tr><td>CTRL + SHIFT + Left<br/></td><td>Extends selection to the current word start position.<br/></td></tr><tr><td>CTRL + SHIFT + Down<br/></td><td>Extends selection to the current paragraph end position.<br/></td></tr><tr><td>CTRL + SHIFT + Up<br/></td><td>Extends selection to the current paragraph start position.<br/></td></tr><tr><td>CTRL + A<br/></td><td>Selects the entire document.<br/></td></tr></table>

## How to show blinking cursor and selection highlight even when the control lost focus

The SfRichTextBoxAdv control allows you to show the blinking cursor and selection highlight even when the control doesn't have focus. You can choose any one of the following selection visibility options:

* **None** - Don't display neither caret nor selection highlight when the RichTextBox control doesn't have focus.

* **ShowCaret** - Displays the caret (blinking cursor) when the RichTextBox control doesn't have focus.

* **ShowSelection** - Displays the selection highlight when the RichTextBox control doesn't have focus.

The following code example demonstrates how to display the selection highlight even when the RichTextBox control doesn't have focus.

{% tabs %}
{% highlight xaml %}
<RichTextBoxAdv:SfRichTextBoxAdv x:Name="richTextBoxAdv" LostFocusBehavior="ShowSelection"  xmlns:RichTextBoxAdv="clr-namespace:Syncfusion.Windows.Controls.RichTextBoxAdv;assembly=Syncfusion.SfRichTextBoxAdv.Wpf" />


{% endhighlight %}
{% highlight c# %}
// Initializes a new instance of RichTextBoxAdv.
SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();
// Displays the selection highlight when the RichTextBox control doesn't have focus.
richTextBoxAdv.LostFocusBehavior = LostFocusBehavior.ShowSelection;


{% endhighlight %}
{% highlight VB %}
' Initializes a new instance of RichTextBoxAdv.
Dim richTextBoxAdv As New SfRichTextBoxAdv()

' Displays the selection highlight when the RichTextBox control doesn't have focus.
richTextBoxAdv.LostFocusBehavior = LostFocusBehavior.ShowSelection


{% endhighlight %}

{% endtabs %}

N> This API is supported starting from release version v17.4.0.X.

## How to determine the editing context type

The SfRichTextBoxAdv control allows you to know the editing context type based on the selected content. The following are the editing context types:

* **Text** - Denotes that the editing context is text

* **Image** - Denotes that the editing context is image

* **Table** - Denotes that the editing context is table

The following code example demonstrates how to determine the editing context type based on the selection.

{% tabs %}
{% highlight c# %}
// Initializes a new instance of RichTextBoxAdv.
SfRichTextBoxAdv richTextBoxAdv = new SfRichTextBoxAdv();
if (richTextBoxAdv.Selection.EditingContext.Type == EditingContextType.Text)
 {
 }


{% endhighlight %}
{% highlight VB %}
' Initializes a new instance of RichTextBoxAdv.
Dim richTextBoxAdv As New SfRichTextBoxAdv()
If (richTextBoxAdv.Selection.EditingContext.Type == EditingContextType.Text) Then
End If


## How to delete the selected content
 
The SfRichTextBoxAdv supports deleting the selected portion of the document either through UI command, keyboard or through supported APIs.

The following code sample demonstrates how to delete the selected portion of the document using the DeleteKeyCommand.
{% tabs %}
{% highlight Xaml %}
<!-- Binds button to the DeleteKeyCommand -->
<Button Content="Delete" Command="RichTextBoxAdv:SfRichTextBoxAdv.DeleteKeyCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}"/>


The following code sample demonstrates how to delete the selected portion of the document using the Delete method. This method is valid only when the selection is non-empty, and it returns true if the selected content is deleted. Otherwise false.

{% tabs %}
{% highlight c# %}
//Deletes the selected content in SfRichTextBoxAdv control.
bool isDeleted = richTextBoxAdv.Selection.Delete();

{% tabs %}
{% highlight VB %} 
Dim isDeleted As Boolean = richTextBoxAdv.Selection.Delete()

{% endhighlight %}

{% endtabs %}

N> This API is supported starting from release version v18.2.0.X.