---
title: Selection
description: selection
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: selection
---
# Selection

The SfRichTextBoxAdv supports selecting a portion of the document either through UI interactions by using mouse, touch, keyboard or through supported APIs.
The following sample code demonstrates how to retrieve text position from document using paragraph instance and offset value.
{% tabs %}
{% highlight c# %}
// Gets the first section of the document.
SectionAdv sectionAdv = richTextBoxAdv.Document.Sections[0];


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


{% endtabs %}

{% tabs %}
{% highlight c# %}
// Gets the third block of a section, which is table.
TableAdv tableAdv = sectionAdv.Blocks[2] as TableAdv;
// Gets the third block from second row second cell of the table, which is paragraph.
ParagraphAdv paragraphAdv = tableAdv.Rows[1].Cells[1].Blocks[2] as ParagraphAdv;
TextPosition position = richTextBoxAdv.Document.GetTextPosition(paragraphAdv, 12);


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

{% endtabs %}

The following sample code demonstrates how to move selection start and selection end both at a specific text position.
{% tabs %}
{% highlight c# %}
// Makes an empty selection at the specific text position.
richTextBoxAdv.Selection.Select(position, position);


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

{% endtabs %}

{% tabs %}
{% highlight c# %}
// Selects the text positions in reverse direction.
richTextBoxAdv.Selection.Select(endPosition, startPosition);


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

{% endtabs %}

The following sample code demonstrates how to apply after spacing for the selected paragraphs.
{% tabs %}
{% highlight c# %}
// Applies after spacing for the selected paragraphs.
richTextBoxAdv.Selection.ParagraphFormat.AfterSpacing = 24;


{% endhighlight %}

{% endtabs %}

The following sample code demonstrates how to apply page margin for the selected sections.
{% tabs %}
{% highlight c# %}
// Applies page margin for the selected sections.
richTextBoxAdv.Selection.SectionFormat.PageMargin = new Thickness(96, 48, 96, 48);


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

{% endtabs %}

## Keyboard shortcuts to perform selection

The following keyboard shortcuts are supported by SfRichTextBoxAdv for navigation and selection.
<table>
<tr>
<td colspan=1 rowspan=1>
Navigation Shortcut<br/></td><td colspan=1 rowspan=1>
Description<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
Right Arrow<br/></td><td colspan=1 rowspan=1>
Navigates to one position forward.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
Left Arrow<br/></td><td colspan=1 rowspan=1>
Navigates to one position backward.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
Down Arrow<br/></td><td colspan=1 rowspan=1>
Navigates to the same position at next line.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
Up Arrow<br/></td><td colspan=1 rowspan=1>
Navigates to the same position at previous line.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
Home<br/></td><td colspan=1 rowspan=1>
Navigates to start of the current line.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
End<br/></td><td colspan=1 rowspan=1>
Navigates to end of the current line.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
CTRL + Home<br/></td><td colspan=1 rowspan=1>
Navigates to the document start position.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
CTRL + End<br/></td><td colspan=1 rowspan=1>
Navigates to the document end position.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
CTRL + Right<br/></td><td colspan=1 rowspan=1>
Navigates to the next word start position.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
CTRL + Left<br/></td><td colspan=1 rowspan=1>
Navigates to the current word start position.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
CTRL + Down<br/></td><td colspan=1 rowspan=1>
Navigates to the next paragraph start position.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
CTRL + Up<br/></td><td colspan=1 rowspan=1>
Navigates to the current paragraph start position.<br/></td></tr>
</table>
<table>
<tr>
<td colspan=1 rowspan=1>
Selection Shortcut<br/></td><td colspan=1 rowspan=1>
Description<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
CTRL + Right Arrow<br/></td><td colspan=1 rowspan=1>
Extends selection to one position forward.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
CTRL + Left Arrow<br/></td><td colspan=1 rowspan=1>
Extends selection to one position backward.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
CTRL + Down Arrow<br/></td><td colspan=1 rowspan=1>
Extends selection to the same position at next line.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
CTRL + Up Arrow<br/></td><td colspan=1 rowspan=1>
Extends selection to the same position at previous line.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
SHIFT + Home<br/></td><td colspan=1 rowspan=1>
Extends selection to start of the current line.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
SHIFT + End<br/></td><td colspan=1 rowspan=1>
Extends selection to end of the current line.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
CTRL + SHIFT + Home<br/></td><td colspan=1 rowspan=1>
Extends selection to the document start position.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
CTRL + SHIFT + End<br/></td><td colspan=1 rowspan=1>
Extends selection to the document end position.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
CTRL + SHIFT + Right<br/></td><td colspan=1 rowspan=1>
Extends selection to the current word end position.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
CTRL + SHIFT + Left<br/></td><td colspan=1 rowspan=1>
Extends selection to the current word start position.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
CTRL + SHIFT + Down<br/></td><td colspan=1 rowspan=1>
Extends selection to the current paragraph end position.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
CTRL + SHIFT + Up<br/></td><td colspan=1 rowspan=1>
Extends selection to the current paragraph start position.<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
CTRL + A<br/></td><td colspan=1 rowspan=1>
Selects the entire document.<br/></td></tr>
</table>
