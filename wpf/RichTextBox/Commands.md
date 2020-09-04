---
title: Commands | WPF RichTextBox | Syncfusion
description: This section illustrates the list of built-in commands supported in WPF RichTextBox control (SfRichTextBoxAdv).
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: commands
---
# Commands in WPF RichTextBox (SfRichTextBoxAdv)

Commands are a way to handle user interface (UI) actions. They are a loosely coupled way to bind the UI to the logic that performs the action. The SfRichTextBoxAdv supports commands for mostly used operations which are classified below.

* Character Formatting – Bold, Italic, Underline, Strike through, Baseline alignment, Font family, Font size, Font color and Highlight color.

* Paragraph Formatting – Left indent, Right indent, First line indent, Text alignment, Before spacing, After spacing, Line spacing, Line spacing type, Increase indent, Decrease indent and Change list type.

* Clipboard – Cut, Copy and Paste.

* History – Undo and Redo.

* Import and Export – Open document, Save document and New document.

* Comments – New comment, Delete comment, Delete all comments, Previous comment, Next comment and Show comments.

* Table – Insert table, Insert row, Insert column, Delete table, Delete row, Delete column and Merge selected cells, Select cell, Select column, Select row, Select table and Align cell content.

* UI options – Show hyperlink dialog, Show options pane and Layout type.

* Insert – Insert picture and Insert hyperlink.

* Document Styles – Create, modify, apply and clear style.

## UI Command to access character formatting


The following code example demonstrates how to bind commands for applying character format.
{% tabs %}
{% highlight xaml %}
<!-- Binds button to the BoldCommand -->
<Button Content="Bold" Command="RichTextBoxAdv:SfRichTextBoxAdv.BoldCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}"/>
<!-- Binds button to the ItalicCommand -->
<Button Content="Italic" Command="RichTextBoxAdv:SfRichTextBoxAdv.ItalicCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}"/>


{% endhighlight %}

{% endtabs %}

The following code example demonstrates how to bind commands with parameter.
{% tabs %}
{% highlight xaml %}
<Button Content="Textalignment" Command="Syncfusion:SfRichTextBoxAdv.TextAlignmentCommand" CommandTarget="{Binding ElementName=richTextBoxAdv}" CommandParameter="Right" />
{% endhighlight %}
{% endtabs %}

## List of available Commands

The following table contains the list of available UI Commands in SfRichTextBoxAdv.

<table>
<thead>
<th>
<p>Command Name</p>
</th>
<th>
<p>Description</p>
</th>
<th>
<p>Command parameter (optional)</p>
</th>
</thead>
<tbody>
<tr>
<td>
<p>AddToDictionaryCommand</p>
</td>
<td>
<p>Represents the command to add the selected or specified custom word into the custom dictionary.</p>
</td>
<td>
<p>The custom word to be added.</p>
</td>
</tr>
<tr>
<td>
<p>AfterSpacingCommand</p>
</td>
<td>
<p>Represents the command to apply after spacing for the selected paragraphs.</p>
</td>
<td>
<p>The after spacing value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>AutoFitTableCommand</p>
</td>
<td>
<p>Represents the command that fits the columns width of selected table based on the specified `AutoFitType`.</p>
</td>
<td>
<p>The `AutoFitType` to fit the columns of the table.</p>
</td>
</tr>
<tr>
<td>
<p>BackSpaceKeyCommand</p>
</td>
<td>
<p>Represents the command that performs action for "Backspace" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>BaselineAlignmentCommand</p>
</td>
<td>
<p>Represents the command to apply `BaselineAlignment` for the selected text.</p>
</td>
<td>
<p>The baseline alignment value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>BeforeSpacingCommand</p>
</td>
<td>
<p>Represents the command to apply before spacing for the selected paragraphs.</p>
</td>
<td>
<p>The before spacing value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>BoldCommand</p>
</td>
<td>
<p>Represents the command to toggle bold style for the selected text.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>CellBottomMarginCommand</p>
</td>
<td>
<p>Represents the command to apply bottom margin for the selected table cells.</p>
</td>
<td>
<p>The bottom margin value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>CellContentAlignmentCommand</p>
</td>
<td>
<p>Represents the command to apply content alignment for the selected table cells.</p>
</td>
<td>
<p>The cell content alignment value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>CellLeftMarginCommand</p>
</td>
<td>
<p>Represents the command to apply left margin for the selected table cells.</p>
</td>
<td>
<p>The left margin value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>CellRightMarginCommand</p>
</td>
<td>
<p>Represents the command to apply right margin for the selected table cells.</p>
</td>
<td>
<p>The right margin value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>CellSpacingCommand</p>
</td>
<td>
<p>Represents the command to apply cell spacing for the selected table.</p>
</td>
<td>
<p>The cell spacing value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>CellTopMarginCommand</p>
</td>
<td>
<p>Represents the command to apply top margin for the selected table cells.</p>
</td>
<td>
<p>The top margin value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>CellVerticalAlignmentCommand</p>
</td>
<td>
<p>Represents the command to apply vertical alignment for the selected table cells.</p>
</td>
<td>
<p>The vertical alignment value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>ChangeAllSpellingCommand</p>
</td>
<td>
<p>Represents the command that changes all occurrences of a selected misspelled word.</p>
</td>
<td>
<p>The word to be replaced.</p>
</td>
</tr>
<tr>
<td>
<p>ChangeSpellingCommand</p>
</td>
<td>
<p>Represents the command that changes the selected misspelled word.</p>
</td>
<td>
<p>The word to be replaced.</p>
</td>
</tr>
<tr>
<td>
<p>CheckSpellingCommand</p>
</td>
<td>
<p>Represents the command that checks spelling mistakes in the document of `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ControlDownKeyCommand</p>
</td>
<td>
<p>Represents the command that performs navigation for "CTRL + DOWN" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ControlEndKeyCommand</p>
</td>
<td>
<p>Represents the command that performs navigation for "CTRL + END" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ControlHomeKeyCommand</p>
</td>
<td>
<p>Represents the command that performs navigation for "CTRL + HOME" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ControlLeftKeyCommand</p>
</td>
<td>
<p>Represents the command that performs navigation for "CTRL + LEFT" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ControlRightKeyCommand</p>
</td>
<td>
<p>Represents the command that performs navigation for "CTRL + RIGHT" key .</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ControlShiftDownKeyCommand</p>
</td>
<td>
<p>Represents the command that performs selection for "CTRL + SHIFT + DOWN" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ControlShiftEndKeyCommand</p>
</td>
<td>
<p>Represents the command that performs selection for "CTRL + SHIFT + END" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ControlShiftHomeKeyCommand</p>
</td>
<td>
<p>Represents the command that performs selection for "CTRL + SHIFT + HOME" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ControlShiftLeftKeyCommand</p>
</td>
<td>
<p>Represents the command that performs selection for "CTRL + SHIFT + LEFT" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ControlShiftRightKeyCommand</p>
</td>
<td>
<p>Represents the command that performs selection for "CTRL + SHIFT + RIGHT" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ControlShiftUpKeyCommand</p>
</td>
<td>
<p>Represents the command that performs selection for "CTRL + SHIFT + UP" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ControlUpKeyCommand</p>
</td>
<td>
<p>Represents the command that performs navigation for "CTRL + UP" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>CopyCommand</p>
</td>
<td>
<p>Represents the command that copies the selected contents to clipboard.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>CopyHyperlinkCommand</p>
</td>
<td>
<p>Represents the command that copies the selected hyperlink to clipboard.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>CutCommand</p>
</td>
<td>
<p>Represents the command that removes the selected contents from `SfRichTextBoxAdv` control and copies the same to clipboard.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>DecreaseFontSizeCommand</p>
</td>
<td>
<p>Represents the command to decrease font size for the selected text.</p>
</td>
<td>
<p>The font size value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>DecreaseIndentCommand</p>
</td>
<td>
<p>Represents the command to decrease left indent for the selected paragraphs.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>DefaultCellBottomMarginCommand</p>
</td>
<td>
<p>Represents the command to apply bottom margin for the selected table.</p>
</td>
<td>
<p>The cell bottom margin value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>DefaultCellLeftMarginCommand</p>
</td>
<td>
<p>Represents the command to apply left margin for the selected table.</p>
</td>
<td>
<p>The cell left margin value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>DefaultCellRightMarginCommand</p>
</td>
<td>
<p>Represents the command to apply right margin for the selected table.</p>
</td>
<td>
<p>The cell right margin value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>DefaultCellTopMarginCommand</p>
</td>
<td>
<p>Represents the command to apply top margin for the selected table.</p>
</td>
<td>
<p>The cell top margin value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>DeleteAllCommentsCommand</p>
</td>
<td>
<p>Represents the command to delete all the comments in the document.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>DeleteColumnCommand</p>
</td>
<td>
<p>Represents the command to delete the selected column of a table.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>DeleteCommentCommand</p>
</td>
<td>
<p>Represents the command that deletes the selected comment.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>DeleteKeyCommand</p>
</td>
<td>
<p>Represents the command that performs action for "DELETE" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>DeleteRowCommand</p>
</td>
<td>
<p>Represents the command to delete the selected row of a table.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>DeleteTableCommand</p>
</td>
<td>
<p>Represents the command to delete the selected table.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>DownKeyCommand</p>
</td>
<td>
<p>Represents the command that performs navigation for "DOWN" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>EndKeyCommand</p>
</td>
<td>
<p>Represents the command that performs navigation for "END" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>EnterKeyCommand</p>
</td>
<td>
<p>Represents the command that performs action for "ENTER" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>FirstLineIndentCommand</p>
</td>
<td>
<p>Represents the command to apply first line indent for the selected paragraphs.</p>
</td>
<td>
<p>The first line indent value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>FontColorCommand</p>
</td>
<td>
<p>Represents the command to apply font color for the selected text.</p>
</td>
<td>
<p>The font color value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>FontFamilyCommand</p>
</td>
<td>
<p>Represents the command to apply font family for the selected text.</p>
</td>
<td>
<p>The font family value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>FontSizeCommand</p>
</td>
<td>
<p>Represents the command to apply font size for the selected text.</p>
</td>
<td>
<p>The font size value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>HighlightColorCommand</p>
</td>
<td>
<p>Represents the command to apply `HighlightColor` for the selected text.</p>
</td>
<td>
<p>The highlight color value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>HomeKeyCommand</p>
</td>
<td>
<p>Represents the command that performs navigation for "HOME" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>IgnoreAllSpellingErrorsCommand</p>
</td>
<td>
<p>Represents the command that ignores all the occurrence of a selected misspelled word.</p>
</td>
<td>
<p>The misspelled word to be ignored.</p>
</td>
</tr>
<tr>
<td>
<p>IncreaseFontSizeCommand</p>
</td>
<td>
<p>Represents the command to increase font size for the selected text.</p>
</td>
<td>
<p>The font size value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>IncreaseIndentCommand</p>
</td>
<td>
<p>Represents the command to increase indent for the selected paragraphs.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>InsertBreakCommand</p>
</td>
<td>
<p>Represents the command that inserts a break at selection.</p>
</td>
<td>
<p>The break type to be inserted</p>
</td>
</tr>
<tr>
<td>
<p>InsertColumnCommand</p>
</td>
<td>
<p>Represents the command that inserts a column to the selected table.</p>
</td>
<td>
<p>The `ColumnPlacement` value to insert column.</p>
</td>
</tr>
<tr>
<td>
<p>InsertHyperlinkCommand</p>
</td>
<td>
<p>Represents the command that inserts a hyperlink at selection.</p>
</td>
<td>
<p>The hyperlink to be inserted.</p>
</td>
</tr>
<tr>
<td>
<p>InsertPictureCommand</p>
</td>
<td>
<p>Represents the command that inserts a picture at selection.</p>
</td>
<td>
<p>The picture to be inserted.</p>
</td>
</tr>
<tr>
<td>
<p>InsertRowCommand</p>
</td>
<td>
<p>Represents the command that inserts a row to the selected table.</p>
</td>
<td>
<p>The `RowPlacement` value to insert row.</p>
</td>
</tr>
<tr>
<td>
<p>InsertTableCommand</p>
</td>
<td>
<p>Represents the command that inserts a table at selection.</p>
</td>
<td>
<p>The row and column count of the table.</p>
</td>
</tr>
<tr>
<td>
<p>ItalicCommand</p>
</td>
<td>
<p>Represents the command to toggle italic style for the selected text.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>LayoutTypeCommand</p>
</td>
<td>
<p>Represents the command to change layout type of the `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>The layout type to set for the `SfRichTextBoxAdv` control.</p>
</td>
</tr>
<tr>
<td>
<p>LeftIndentCommand</p>
</td>
<td>
<p>Represents the command to apply left indent for the selected paragraphs.</p>
</td>
<td>
<p>The left indent value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>LeftKeyCommand</p>
</td>
<td>
<p>Represents the command that performs navigation for "LEFT" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>LineSpacingCommand</p>
</td>
<td>
<p>Represents the command to apply line spacing for the selected paragraphs.</p>
</td>
<td>
<p>The line spacing value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>LineSpacingTypeCommand</p>
</td>
<td>
<p>Represents the command to apply `LineSpacingType` for the selected paragraphs.</p>
</td>
<td>
<p>The `LineSpacingType` value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>MergeSelectedCellsCommand</p>
</td>
<td>
<p>Represents the command that merges the selected table cells.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>NavigateHyperlinkCommand</p>
</td>
<td>
<p>Represents the command that performs navigation for the selected hyperlink.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>NewCommentCommand</p>
</td>
<td>
<p>Represents the command that adds a comment at the selection.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>NewDocumentCommand</p>
</td>
<td>
<p>Represents the command that creates a new document in `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>NextCommentCommand</p>
</td>
<td>
<p>Represents the command that performs navigation to next comment in the document.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>OpenDocumentCommand</p>
</td>
<td>
<p>Represents the command that opens an existing document in the `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>PageDownKeyCommand</p>
</td>
<td>
<p>Represents the command that performs navigation for "PAGEDOWN" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>PageFitCommand</p>
</td>
<td>
<p>Represents the command to apply `PageFitType` for the `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>The `PageFitType` value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>PageUpKeyCommand</p>
</td>
<td>
<p>Represents the command that performs navigation for "PAGEUP" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>PasteCommand</p>
</td>
<td>
<p>Represents the command that pastes the content from clipboard to `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>PreviousCommentCommand</p>
</td>
<td>
<p>Represents the command that performs navigation to previous comment in the document.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>PrintDocumentCommand</p>
</td>
<td>
<p>Represents the command that prints the document of `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>RedoCommand</p>
</td>
<td>
<p>Represents the command that redo the last undo operation in `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>RemoveHyperlinkCommand</p>
</td>
<td>
<p>Represents the command that removes the selected hyperlink.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>RightIndentCommand</p>
</td>
<td>
<p>Represents the command to apply right indent for the selected paragraphs.</p>
</td>
<td>
<p>The right indent value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>RightKeyCommand</p>
</td>
<td>
<p>Represents the command that performs navigation for "RIGHT" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>SaveAsDocumentCommand</p>
</td>
<td>
<p>Represents the command that saves the document of `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>SaveDocumentCommand</p>
</td>
<td>
<p>Represents the command that saves the document of `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>SelectAllCommand</p>
</td>
<td>
<p>Represents the command that selects all the content of `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>SelectCellCommand</p>
</td>
<td>
<p>Represents the command that selects the table cell.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>SelectColumnCommand</p>
</td>
<td>
<p>Represents the command that selects the entire column of a table.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>SelectRowCommand</p>
</td>
<td>
<p>Represents the command that selects the entire row of a table.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>SelectTableCommand</p>
</td>
<td>
<p>Represents the command that selects the table.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShiftDownKeyCommand</p>
</td>
<td>
<p>Represents the command that performs selection for "SHIFT + DOWN" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShiftEndKeyCommand</p>
</td>
<td>
<p>Represents the command that performs selection for "SHIFT + END" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShiftEnterKeyCommand</p>
</td>
<td>
<p>Represents the command that performs action [inserts line break] for "SHIFT + ENTER" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShiftHomeKeyCommand</p>
</td>
<td>
<p>Represents the command that performs selection for "SHIFT + HOME" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShiftLeftKeyCommand</p>
</td>
<td>
<p>Represents the command that performs selection for "SHIFT + LEFT" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShiftRightKeyCommand</p>
</td>
<td>
<p>Represents the command that performs selection for "SHIFT + RIGHT" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShiftTabKeyCommand</p>
</td>
<td>
<p>Represents the command that performs selection for "SHIFT + TAB" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShiftUpKeyCommand</p>
</td>
<td>
<p>Represents the command that performs selection for "SHIFT + UP" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShowBordersAndShadingDialogCommand</p>
</td>
<td>
<p>Represents the command that shows the borders and shading dialog.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShowCellOptionsDialogCommand</p>
</td>
<td>
<p>Represents the command that shows the cell options dialog.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShowCommentsCommand</p>
</td>
<td>
<p>Represents the command to show or hide comments in the `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShowEncryptDocumentDialogCommand</p>
</td>
<td>
<p>Represents the command that shows dialog to specify password for opening encrypted Word document.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShowFindAndReplaceDialogCommand</p>
</td>
<td>
<p>Represents the command that shows the find and replace dialog.</p>
</td>
<td>The Boolean value to show find or replace tab.</td>
</tr>
<tr>
<td>
<p>ShowFontDialogCommand</p>
</td>
<td>
<p>Represents the command that shows the font dialog.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShowHyperlinkDialogCommand</p>
</td>
<td>
<p>Represents the command that shows the hyperlink dialog.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShowInsertTableDialogCommand</p>
</td>
<td>
<p>Represents the command that shows the insert table dialog.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShowListDialogCommand</p>
</td>
<td>
<p>Represents the command that shows the list dialog.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShowOptionsPaneCommand</p>
</td>
<td>
<p>Represents the command that shows the options pane.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShowParagraphDialogCommand</p>
</td>
<td>
<p>Represents the command that shows the paragraph dialog.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShowSpellingPaneCommand</p>
</td>
<td>
<p>Represents the command that shows the spelling pane.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShowTableDialogCommand</p>
</td>
<td>
<p>Represents the command that shows the table dialog.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShowTableOptionsDialogCommand</p>
</td>
<td>
<p>Represents the command that shows the table options dialog.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>SpaceKeyCommand</p>
</td>
<td>
<p>Represents the command that performs action [inserts space] for "SPACE" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>StrikeThroughCommand</p>
</td>
<td>
<p>Represents the command to apply `StrikeThrough` for the selected text.</p>
</td>
<td>
<p>The strike through value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>TabKeyCommand</p>
</td>
<td>
<p>Represents the command that performs action [inserts tab] for "TAB" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>TableAlignmentCommand</p>
</td>
<td>
<p>Represents the command to apply table alignment for the selected table.</p>
</td>
<td>
<p>The table alignment value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>TableLeftIndentCommand</p>
</td>
<td>
<p>Represents the command to apply left indent for the selected table.</p>
</td>
<td>
<p>The left indent value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>TextAlignmentCommand</p>
</td>
<td>
<p>Represents the command to apply text alignment for the selected paragraphs.</p>
</td>
<td>
The {{'[TextAlignment](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Controls.RichTextBoxAdv.ParagraphFormat.html#Syncfusion_Windows_Controls_RichTextBoxAdv_ParagraphFormat_TextAlignment)'| markdownify}} value to be applied.
</td>
</tr>
<tr>
<td>
<p>ToggleBaselineAlignmentCommand</p>
</td>
<td>
<p>Represents the command that toggles baseline alignment for the selected text.</p>
</td>
<td>
<p>The baseline alignment value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>ToggleBeforeSpacingCommand</p>
</td>
<td>
<p>Represents the command that toggles before spacing for the selected paragraphs.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ToggleHighlightColorCommand</p>
</td>
<td>
<p>Represents the command that toggles highlight color for the selected text.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ToggleUnderlineCommand</p>
</td>
<td>
<p>Represents the command that toggles underline for the selected text.</p>
</td>
<td>
<p>The `Underline` value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>UnderlineCommand</p>
</td>
<td>
<p>Represents the command to apply underline for the selected text.</p>
</td>
<td>
<p>The `Underline` value to be applied.</p>
</td>
</tr>
<tr>
<td>
<p>UndoCommand</p>
</td>
<td>
<p>Represents the command that undo the last edit operation in `SfRichTextBoxAdv` control.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>UpKeyCommand</p>
</td>
<td>
<p>Represents the command that performs navigation for "UP" key.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShowStyleDialogCommand</p>
</td>
<td>
<p>Represents the command that shows the create style dialog.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ShowStylesDialogCommand</p>
</td>
<td>
<p>Represents the command that shows the modify style dialog.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
<tr>
<td>
<p>ApplyStyleCommand</p>
</td>
<td>
<p>Represents the command, which requests to apply style for the selected paragraph.</p>
</td>
<td>
<p>Name of the Style</p>
</td>
</tr>
<tr>
<td>
<p>ClearFormattingCommand</p>
</td>
<td>
<p>Represents the command, which requests to remove formatting from the selected paragraph.</p>
</td>
<td>
<p>NA</p>
</td>
</tr>
</tbody>
</table>