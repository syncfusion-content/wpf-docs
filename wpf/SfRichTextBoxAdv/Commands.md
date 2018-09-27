---
title: Commands
description: commands
platform: wpf
control: SfRichTextBoxAdv
documentation: ug
keywords: commands
---
# Commands

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

## List of available Commands

The following table contains the list of available UI Commands in SfRichTextBoxAdv.

<table>
<thead>
<th width="264">
<p>Command Name</p>
</th>
<th width="217">
<p>Description</p>
</th>
<th width="152">
<p>Command parameter (optional)</p>
</th>
</thead>
<tbody>
<tr>
<td width="264">
<p>AddToDictionaryCommand</p>
</td>
<td width="217">
<p>Represents the command to add the selected spelling error word or specified word into the custom dictionary.</p>
</td>
<td width="152">
<p>The custom word to add into dictionary.</p>
</td>
</tr>
<tr>
<td width="264">
<p>AfterSpacingCommand</p>
</td>
<td width="217">
<p>Represents the command to change the after spacing value for the selected paragraphs in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The after spacing value to be applied for selected paragraph.</p>
</td>
</tr>
<tr>
<td width="264">
<p>AutoFitTableCommand</p>
</td>
<td width="217">
<p>Represents the command to fits the columns width of selected table in `SfRichTextBoxAdv` control based on type `AutoFitType`.</p>
</td>
<td width="152">
<p>The `AutoFitType` to fit the columns of the table.</p>
</td>
</tr>
<tr>
<td width="264">
<p>BackSpaceKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform action for "Backspace" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>BaselineAlignmentCommand</p>
</td>
<td width="217">
<p>Represents the command to change `BaselineAlignment` for the selected contents in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The baseline alignment value to be applied for selected text.</p>
</td>
</tr>
<tr>
<td width="264">
<p>BeforeSpacingCommand</p>
</td>
<td width="217">
<p>Represents the command to change the value of before spacing for the selected paragraphs in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The before spacing value to be applied for current selection.</p>
</td>
</tr>
<tr>
<td width="264">
<p>BoldCommand</p>
</td>
<td width="217">
<p>Represents the command to toggle the bold format for the selected contents in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>CellBottomMarginCommand</p>
</td>
<td width="217">
<p>Represents the command to change bottom margin for the selected table cell in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The bottom margin value to be applied for the selected cell.</p>
</td>
</tr>
<tr>
<td width="264">
<p>CellContentAlignmentCommand</p>
</td>
<td width="217">
<p>Represents the command to apply cell content alignment for the selected table cells in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The cell content alignment value to be applied for the selected cell.</p>
</td>
</tr>
<tr>
<td width="264">
<p>CellLeftMarginCommand</p>
</td>
<td width="217">
<p>Represents the command to change left margin for the selected table cell in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The left margin value to be applied for the selected cell.</p>
</td>
</tr>
<tr>
<td width="264">
<p>CellRightMarginCommand</p>
</td>
<td width="217">
<p>Represents the command to change the value of right margin for the selected table cell in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The right margin value to be applied for the selected cell.</p>
</td>
</tr>
<tr>
<td width="264">
<p>CellSpacingCommand</p>
</td>
<td width="217">
<p>Represents the command to apply cell spacing for the selected table in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The cell spacing value to be applied for the selected table.</p>
</td>
</tr>
<tr>
<td width="264">
<p>CellTopMarginCommand</p>
</td>
<td width="217">
<p>Represents the command to apply top margin for the selected table cell in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The top margin value to be applied for the selected cell.</p>
</td>
</tr>
<tr>
<td width="264">
<p>CellVerticalAlignmentCommand</p>
</td>
<td width="217">
<p>Represents the command to apply vertical alignment for the selected contents in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The vertical alignment value to be applied for the selected cell.</p>
</td>
</tr>
<tr>
<td width="264">
<p>ChangeAllSpellingCommand</p>
</td>
<td width="217">
<p>Represents the command, that all occurrences of any misspelled word at the current position to be changed.</p>
</td>
<td width="152">
<p>The word to be replaced for all occurrences of misspelled word.</p>
</td>
</tr>
<tr>
<td width="264">
<p>ChangeSpellingCommand</p>
</td>
<td width="217">
<p>Represents the command that any misspelled word at the current position to be changed.</p>
</td>
<td width="152">
<p>The word to be replaced in immediate occurrence of misspelled word.</p>
</td>
</tr>
<tr>
<td width="264">
<p>CheckSpellingCommand</p>
</td>
<td width="217">
<p>Represents the command that the document in `SfRichTextBoxAdv` control be checked for spelling mistakes.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ControlDownKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform navigation for "CTRL + DOWN" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ControlEndKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform navigation for "CTRL + END" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ControlHomeKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform navigation for "CTRL + HOME" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ControlLeftKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform navigation for "CTRL + LEFT" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ControlRightKeyCommand</p>
</td>
<td width="217">
<p>Represents the command to perform navigation for "CTRL + RIGHT" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ControlShiftDownKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform selection for "CTRL + SHIFT + DOWN" key in a`SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ControlShiftEndKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform selection for "CTRL + SHIFT + END" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ControlShiftHomeKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform selection for "CTRL + SHIFT + HOME" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ControlShiftLeftKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform selection for "CTRL + SHIFT + LEFT" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ControlShiftRightKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform selection for "CTRL + SHIFT + RIGHT" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ControlShiftUpKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform selection for "CTRL + SHIFT + UP" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ControlUpKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform navigation for "CTRL + UP" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>CopyCommand</p>
</td>
<td width="217">
<p>Represents the command that selected contents in `SfRichTextBoxAdv` control be copied into the clipboard.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>CopyHyperlinkCommand</p>
</td>
<td width="217">
<p>Represents the command that any hyperlink at the current position be copied.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>CutCommand</p>
</td>
<td width="217">
<p>Represents the command that the selected contents in `SfRichTextBoxAdv` control be moved to the clipboard.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>DecreaseFontSizeCommand</p>
</td>
<td width="217">
<p>Represents the command to decrease font size for the selected contents in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The font size value to be applied for the selected text.</p>
</td>
</tr>
<tr>
<td width="264">
<p>DecreaseIndentCommand</p>
</td>
<td width="217">
<p>Represents the command to decrease the left indent for the selected paragraphs in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>DefaultCellBottomMarginCommand</p>
</td>
<td width="217">
<p>Represents the command to apply bottom margin for the selected table in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The cell bottom margin value to be applied for current selected table.</p>
</td>
</tr>
<tr>
<td width="264">
<p>DefaultCellLeftMarginCommand</p>
</td>
<td width="217">
<p>Represents the command to apply left margin for the selected table in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The cell left margin value to be applied for current selected table..</p>
</td>
</tr>
<tr>
<td width="264">
<p>DefaultCellRightMarginCommand</p>
</td>
<td width="217">
<p>Represents the command to apply right margin for the selected table in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The cell right margin value to be applied for current selected table.</p>
</td>
</tr>
<tr>
<td width="264">
<p>DefaultCellTopMarginCommand</p>
</td>
<td width="217">
<p>Represents the command to apply top margin for the selected table in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The cell top margin value to be applied for current selected table.</p>
</td>
</tr>
<tr>
<td width="264">
<p>DeleteAllCommentsCommand</p>
</td>
<td width="217">
<p>Represents the command that to delete all comments in the document.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>DeleteColumnCommand</p>
</td>
<td width="217">
<p>Represents the command to delete the entire column of a table at current position in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>DeleteCommentCommand</p>
</td>
<td width="217">
<p>Represents the command that any comment at the current position be deleted.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>DeleteKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform action for "DELETE" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>DeleteRowCommand</p>
</td>
<td width="217">
<p>Represents the command that delete the entire row of the table at current position in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>DeleteTableCommand</p>
</td>
<td width="217">
<p>Represents the command that delete the entire table at current position in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>DownKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform navigation for "DOWN" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>EndKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform navigation for "END" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>EnterKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform action for "ENTER" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>FirstLineIndentCommand</p>
</td>
<td width="217">
<p>Represents the command that apply first line indent for the selected paragraphs in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The first line indent value to be applied for the selected paragraph.</p>
</td>
</tr>
<tr>
<td width="264">
<p>FontColorCommand</p>
</td>
<td width="217">
<p>Represents the command that apply font color for the selected contents in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The font color value to be applied for selected text.</p>
</td>
</tr>
<tr>
<td width="264">
<p>FontFamilyCommand</p>
</td>
<td width="217">
<p>Represents the command that apply font family for the selected contents in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The font family value to be applied for selected text.</p>
</td>
</tr>
<tr>
<td width="264">
<p>FontSizeCommand</p>
</td>
<td width="217">
<p>Represents the command that apply font size for the selected contents in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The font size value to be applied for selected text.</p>
</td>
</tr>
<tr>
<td width="264">
<p>HighlightColorCommand</p>
</td>
<td width="217">
<p>Represents the command that apply `HighlightColor` for the selected contents in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The highlight color value to be applied for selected text.</p>
</td>
</tr>
<tr>
<td width="264">
<p>HomeKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform navigation for "HOME" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>IgnoreAllSpellingErrorsCommand</p>
</td>
<td width="217">
<p>Represents the command that that all occurrences of any misspelled word at the current position be ignored.</p>
</td>
<td width="152">
<p>The misspelled word to be ignored.</p>
</td>
</tr>
<tr>
<td width="264">
<p>IncreaseFontSizeCommand</p>
</td>
<td width="217">
<p>Represents the command that increase font size for the selected contents in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The font size value to be applied for the selected text.</p>
</td>
</tr>
<tr>
<td width="264">
<p>IncreaseIndentCommand</p>
</td>
<td width="217">
<p>Represents the command that increase indent for the selected paragraphs in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>InsertBreakCommand</p>
</td>
<td width="217">
<p>Represents the command that inserts a break at current position in `SfRichTextBoxAdv` control</p>
</td>
<td width="152">
<p>The break type to be inserted</p>
</td>
</tr>
<tr>
<td width="264">
<p>InsertColumnCommand</p>
</td>
<td width="217">
<p>Represents the command that insert a column at current position in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The `ColumnPlacement` value to insert column.</p>
</td>
</tr>
<tr>
<td width="264">
<p>InsertHyperlinkCommand</p>
</td>
<td width="217">
<p>Represents the command that inserts a hyperlink at current position in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The hyperlink to be inserted.</p>
</td>
</tr>
<tr>
<td width="264">
<p>InsertPictureCommand</p>
</td>
<td width="217">
<p>Represents the command that inserts a picture at current position in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The picture to be inserted.</p>
</td>
</tr>
<tr>
<td width="264">
<p>InsertRowCommand</p>
</td>
<td width="217">
<p>Represents the command that insert a row at current position in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The `RowPlacement` value to insert row.</p>
</td>
</tr>
<tr>
<td width="264">
<p>InsertTableCommand</p>
</td>
<td width="217">
<p>Represents the command that inserts a table at current position in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The row and column count to insert.</p>
</td>
</tr>
<tr>
<td width="264">
<p>ItalicCommand</p>
</td>
<td width="217">
<p>Represents the command that toggle the italic format for the selected contents in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>LayoutTypeCommand</p>
</td>
<td width="217">
<p>Represents the command that the change the layout type in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The layout type to be set for SfRichTextBoxAdv.</p>
</td>
</tr>
<tr>
<td width="264">
<p>LeftIndentCommand</p>
</td>
<td width="217">
<p>Represents the command that apply left indent for the selected paragraphs in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The left indent value to be applied for selected paragraph.</p>
</td>
</tr>
<tr>
<td width="264">
<p>LeftKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform navigation for "LEFT" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>LineSpacingCommand</p>
</td>
<td width="217">
<p>Represents the command that apply line spacing for the selected paragraphs in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The line spacing value to be applied for selected paragraph.</p>
</td>
</tr>
<tr>
<td width="264">
<p>LineSpacingTypeCommand</p>
</td>
<td width="217">
<p>Represents the command that apply `LineSpacingType` for the selected paragraphs in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The line spacing type value to be applied for selected paragraph.</p>
</td>
</tr>
<tr>
<td width="264">
<p>MergeSelectedCellsCommand</p>
</td>
<td width="217">
<p>Represents the command that merge the currently selected cells in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>NavigateHyperlinkCommand</p>
</td>
<td width="217">
<p>Represents the command that any hyperlink at the current position be navigated.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>NewCommentCommand</p>
</td>
<td width="217">
<p>Represents the command that adds a comment at the current position.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>NewDocumentCommand</p>
</td>
<td width="217">
<p>Represents the command that creates a new document in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>NextCommentCommand</p>
</td>
<td width="217">
<p>Represents the command that perform navigation to any next comment in the document.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>OpenDocumentCommand</p>
</td>
<td width="217">
<p>Represents the command that open an existing document in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>PageDownKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform navigation for "PAGEDOWN" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>PageFitCommand</p>
</td>
<td width="217">
<p>Represents the command that the changes `PageFitType` in `SfRichTextBoxAdv` control be changed.</p>
</td>
<td width="152">
<p>The `PageFitType` value for the document in pages view.</p>
</td>
</tr>
<tr>
<td width="264">
<p>PageUpKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform navigation for "PAGEUP" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>PasteCommand</p>
</td>
<td width="217">
<p>Represents the command that the clipboard contents be pasted in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>PreviousCommentCommand</p>
</td>
<td width="217">
<p>Represents the command that perform navigation to any previous comment in the document.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>PrintDocumentCommand</p>
</td>
<td width="217">
<p>Represents the command that print the document in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>RedoCommand</p>
</td>
<td width="217">
<p>Represents the command that the last undone operation in `SfRichTextBoxAdv` control be redone.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>RemoveHyperlinkCommand</p>
</td>
<td width="217">
<p>Represents the command that any hyperlink at the current position be removed.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>RightIndentCommand</p>
</td>
<td width="217">
<p>Represents the command that apply right indent for the selected paragraphs in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The right indent value to be applied for selected paragraph.</p>
</td>
</tr>
<tr>
<td width="264">
<p>RightKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform navigation for "RIGHT" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>SaveAsDocumentCommand</p>
</td>
<td width="217">
<p>Represents the command that save the document in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>SaveDocumentCommand</p>
</td>
<td width="217">
<p>Represents the command that save the document in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>SelectAllCommand</p>
</td>
<td width="217">
<p>Represents the command that the entire document in `SfRichTextBoxAdv` control be selected.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>SelectCellCommand</p>
</td>
<td width="217">
<p>Represents the command that selects the current cell from a table in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>SelectColumnCommand</p>
</td>
<td width="217">
<p>Represents the command that selects the entire current column from a table in `SfRichTextBoxAdv`.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>SelectRowCommand</p>
</td>
<td width="217">
<p>Represents the command that selects the entire current row from a table in `SfRichTextBoxAdv`.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>SelectTableCommand</p>
</td>
<td width="217">
<p>Represents the command that selects the current table in `SfRichTextBoxAdv`.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShiftDownKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform selection for "SHIFT + DOWN" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShiftEndKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform selection for "SHIFT + END" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShiftEnterKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform action for "SHIFT + ENTER" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShiftHomeKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform selection for "SHIFT + HOME" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShiftLeftKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform selection for "SHIFT + LEFT" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShiftRightKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform selection for "SHIFT + RIGHT" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShiftTabKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform selection for "SHIFT + TAB" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShiftUpKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform selection for "SHIFT + UP" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShowBordersAndShadingDialogCommand</p>
</td>
<td width="217">
<p>Represents the command that shows the borders and shading dialog in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShowCellOptionsDialogCommand</p>
</td>
<td width="217">
<p>Represents the command that shows the cell options dialog in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShowCommentsCommand</p>
</td>
<td width="217">
<p>Represents the command that shows the comments in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShowEncryptDocumentDialogCommand</p>
</td>
<td width="217">
<p>Represents the command that shows the encrypt document dialog in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShowFindAndReplaceDialogCommand</p>
</td>
<td width="217">
<p>Represents the command that shows the find and replace dialog in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">The Boolean value to determine the dialog should show the find or replace tab.</td>
</tr>
<tr>
<td width="264">
<p>ShowFontDialogCommand</p>
</td>
<td width="217">
<p>Represents the command that shows the font dialog in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShowHyperlinkDialogCommand</p>
</td>
<td width="217">
<p>Represents the command that shows the hyperlink dialog in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShowInsertTableDialogCommand</p>
</td>
<td width="217">
<p>Represents the command that shows the insert table dialog in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShowListDialogCommand</p>
</td>
<td width="217">
<p>Represents the command that shows the list dialog in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShowOptionsPaneCommand</p>
</td>
<td width="217">
<p>Represents the command that shows the options pane in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShowParagraphDialogCommand</p>
</td>
<td width="217">
<p>Represents the command that shows the paragraph dialog in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShowSpellingPaneCommand</p>
</td>
<td width="217">
<p>Represents the command that shows the spelling pane in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShowTableDialogCommand</p>
</td>
<td width="217">
<p>Represents the command that shows the table dialog in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ShowTableOptionsDialogCommand</p>
</td>
<td width="217">
<p>Represents the command that shows the table options dialog in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>SpaceKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform action for "SPACE" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>StrikeThroughCommand</p>
</td>
<td width="217">
<p>Represents the command that apply `StrikeThrough` for the selected contents in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The strike through value to be applied for selected text.</p>
</td>
</tr>
<tr>
<td width="264">
<p>TabKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform operation for "TAB" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>TableAlignmentCommand</p>
</td>
<td width="217">
<p>Represents the command that apply table alignment for the selected table in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The table alignment value to be applied for the selected table.</p>
</td>
</tr>
<tr>
<td width="264">
<p>TableLeftIndentCommand</p>
</td>
<td width="217">
<p>Represents the command that apply left indent for the selected table in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The left indent value to be applied for selected table.</p>
</td>
</tr>
<tr>
<td width="264">
<p>TextAlignmentCommand</p>
</td>
<td width="217">
<p>Represents the command that apply text alignment for the selected paragraphs in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The text alignment value to be applied for selected paragraph.</p>
</td>
</tr>
<tr>
<td width="264">
<p>ToggleBaselineAlignmentCommand</p>
</td>
<td width="217">
<p>Represents the command that toggles baseline alignment for the selected contents in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The baseline alignment value to be applied for selected text.</p>
</td>
</tr>
<tr>
<td width="264">
<p>ToggleBeforeSpacingCommand</p>
</td>
<td width="217">
<p>Represents the command that toggle before spacing for the selected paragraphs in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ToggleHighlightColorCommand</p>
</td>
<td width="217">
<p>Represents the command that toggle highlight color for the selected contents in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>ToggleUnderlineCommand</p>
</td>
<td width="217">
<p>Represents the command that toggle underline for the selected contents in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The `Underline` value to be toggled for selected text.</p>
</td>
</tr>
<tr>
<td width="264">
<p>UnderlineCommand</p>
</td>
<td width="217">
<p>Represents the command that apply underline for the selected contents in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>The `Underline` value to be applied for selected text.</p>
</td>
</tr>
<tr>
<td width="264">
<p>UndoCommand</p>
</td>
<td width="217">
<p>Represents the command that the last edit operation in `SfRichTextBoxAdv` control be undone.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
<tr>
<td width="264">
<p>UpKeyCommand</p>
</td>
<td width="217">
<p>Represents the command that perform navigation for "UP" key in `SfRichTextBoxAdv` control.</p>
</td>
<td width="152">
<p>NA</p>
</td>
</tr>
</tbody>
</table>