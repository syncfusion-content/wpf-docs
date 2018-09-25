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

<table style="border-collapse: collapse; border: none;">
<tbody>
<thead>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">Command Name</p>
</td>
<td style="width: 162.75pt; border: solid windowtext 1.0pt; border-left: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Description</p>
</td>
<td style="width: 114.2pt; border: solid windowtext 1.0pt; border-left: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">Command parameter (optional)</p>
</td>
</thead>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">AddToDictionaryCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to add the selected spelling error word or specified word into the custom dictionary.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The custom word to add into dictionary.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">AfterSpacingCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command change the after spacing value for the selected paragraphs in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The after spacing value to apply.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">AutoFitTableCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to fits the columns width of selected table in `SfRichTextBoxAdv` control based on type `AutoFitType`.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The `AutoFitType` to fit the columns of the table.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">BackSpaceKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to perform Backspace shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">BaselineAlignmentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to change `BaselineAlignment` for the selected contents in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">`BaselineAlignment` value to apply for the selected contents.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">BeforeSpacingCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to change the value of before spacing for the selected paragraphs in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The before spacing value to apply.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">BoldCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to toggle the bold format for the selected contents in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">CellBottomMarginCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to change bottom margin for the selected table cell in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The value to apply for the bottom margin of selected cell.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">CellContentAlignmentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to apply cell content alignment for the selected table cells in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The value to be applied for cell content alignement.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">CellLeftMarginCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to change left margin for the selected table cell in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The value to apply for the left margin of selected cell.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">CellRightMarginCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to chnage the value of right margin for the selected table cell in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The value to apply for the right margin of selected cell.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">CellSpacingCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to apply cell spacing for the selected table in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The cell spacing value to apply for the selected table.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">CellTopMarginCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to apply top margin for the selected table cell in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The value to apply for the top margin of selected cell.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">CellVerticalAlignmentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to apply vertical alignment for the selected contents in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">`CellVerticalAlignment` value to apply for the selected contents.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ChangeAllSpellingCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command, that all occurrences of any misspelled word at the current position to be changed.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The word to be replaced for all occurrences of misspelled word.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ChangeSpellingCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that any misspelled word at the current position to be changed.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The word to be replaced for immediate occurrence of misspelled word.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">CheckSpellingCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that the document in a `SfRichTextBoxAdv` control be checked for spelling mistakes.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ControlDownKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to perform CTRL + Down shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ControlEndKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to perform CTRL + End shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ControlHomeKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to perform CTRL + Home shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ControlLeftKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to perform CTRL + Left shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ControlRightKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to perform CTRL + Right shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ControlShiftDownKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to perform CTRL + Shift + Down shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ControlShiftEndKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to perform CTRL + Shift + End shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ControlShiftHomeKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to perform CTRL + Shift + Home shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ControlShiftLeftKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to perform CTRL + Shit + Left shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ControlShiftRightKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to perform CTRL + Shift + Right shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ControlShiftUpKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to perform CTRL + Shift + Up shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ControlUpKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to perform CTRL + Up shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">CopyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that selected contents in a `SfRichTextBoxAdv` control be copied into the clipboard.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">CopyHyperlinkCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that any hyperlink at the current position be copied.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">CutCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that the selected contents in a `SfRichTextBoxAdv` control be moved to the clipboard.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">DecreaseFontSizeCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to decrease font size for the selected contents in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The value to applied for the font size.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">DecreaseIndentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to decrease the left indent for the selected paragraphs in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">DefaultCellBottomMarginCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to apply bottom margin for the selected table in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The cell bottom margin value need to be set for current selected table.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">DefaultCellLeftMarginCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to apply left margin for the selected table in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The cell left margin value need to be set for current selected table.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">DefaultCellRightMarginCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to apply right margin for the selected table in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The cell right margin value need to be set for current selected table.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">DefaultCellTopMarginCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to apply top margin for the selected table in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The cell top margin value need to be set for current selected table.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">DeleteAllCommentsCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that to delete all comments in the document.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">DeleteColumnCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command to delete the entire column of a table at current position in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">DeleteCommentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that any comment at the current position be deleted.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">DeleteKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform Delete shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">DeleteRowCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that delete the entire row of the table at current position in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">DeleteTableCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that delete the entire table at current position in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">DownKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform Down shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">EndKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform End shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">EnterKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform Enter shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">FirstLineIndentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that apply first line indent for the selected paragraphs in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The value need to be set for first line indent of current selection.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">FontColorCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that apply font color for the selected contents in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The font color value to be applied for current selection.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">FontFamilyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that apply font family for the selected contents in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The font family value to be applied for current selection.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">FontSizeCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that apply font size for the selected contents in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The font size value to be applied for current selection.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">HighlightColorCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that apply `HighlightColor` for the selected contents in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The highlight color value to be applied for current selection.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">HomeKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform Home shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">IgnoreAllSpellingErrorsCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that that all occurrences of any misspelled word at the current position be ignored.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The misspelled word to be ignored.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">IncreaseFontSizeCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that increase font size for the selected contents in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The value to be applied for font size.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">IncreaseIndentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that increase indent for the selected paragraphs in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">InsertBreakCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that inserts a break at current position in `SfRichTextBoxAdv` control</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The break type to be inserted</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">InsertColumnCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that insert a column at current position in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The `ColumnPlacement` value to insert column.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">InsertHyperlinkCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that inserts a hyperlink at current position in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The hyperlink to be inserted.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">InsertPictureCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that inserts a picture at current position in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The picture to be inserted.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">InsertRowCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that insert a row at current position in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The `RowPlacement` value to insert row.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">InsertTableCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that inserts a table at current position in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The row and column count to insert.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ItalicCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that toggle the italic format for the selected contents in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">LayoutTypeCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that the change the layout type in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The layout type to set.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">LeftIndentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that apply left indent for the selected paragraphs in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The left indent value to be set for selected contents.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">LeftKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform Left shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">LineSpacingCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that apply line spacing for the selected paragraphs in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The line spacing value to be set for current selection.</p>
<p style="margin-bottom: .0001pt; line-height: normal;">&nbsp;</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">LineSpacingTypeCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that apply `LineSpacingType` for the selected paragraphs in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The line spacing type value to be set for current selection.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">MergeSelectedCellsCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that merge the currently selected cells in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">NavigateHyperlinkCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that any hyperlink at the current position be navigated.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">NewCommentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that adds a comment at the current position.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">NewDocumentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that creates a new document in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">NextCommentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform navigation to any next comment in the document.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">OpenDocumentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that open an existing document in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">PageDownKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform PageDown shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">PageFitCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that the changes `PageFitType` in a `SfRichTextBoxAdv` control be changed.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The `PageFitType` value for the document in pages view.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">PageUpKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform PageUp shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">PasteCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that the clipboard contents be pasted in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">PreviousCommentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform navigation to any previous comment in the document.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">PrintDocumentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that print the document in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">RedoCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that the last undone operation in a `SfRichTextBoxAdv` control be redone.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">RemoveHyperlinkCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that any hyperlink at the current position be removed.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">RightIndentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that apply right indent for the selected paragraphs in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The right indent value to be set for selected contents.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">RightKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform Right shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">SaveAsDocumentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that save the document in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">SaveDocumentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that save the document in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">SelectAllCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that the entire document in a `SfRichTextBoxAdv` control be selected.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">SelectCellCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that selects the current cell from a table in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">SelectColumnCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that selects the entire current column from a table in a `SfRichTextBoxAdv`.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">SelectRowCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that selects the entire current row from a table in a `SfRichTextBoxAdv`.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">SelectTableCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that selects the current table in a `SfRichTextBoxAdv`.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShiftDownKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform Shift + Down shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShiftEndKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform Shift + End shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShiftEnterKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform Shift + Enter shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShiftHomeKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform Shift + Home shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShiftLeftKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform Shift + Left shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShiftRightKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform Shift + Right shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShiftTabKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform Shift + Tab shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShiftUpKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform Shift + Up shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShowBordersAndShadingDialogCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that shows the borders and shading dialog in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShowCellOptionsDialogCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that shows the cell options dialog in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShowCommentsCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that shows the comments in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShowEncryptDocumentDialogCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that shows the encrypt document dialog in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShowFindAndReplaceDialogCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that shows the find and replace dialog in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">&nbsp;&nbsp;</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShowFontDialogCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that shows the font dialog in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShowHyperlinkDialogCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that shows the hyperlink dialog in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShowInsertTableDialogCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that shows the insert table dialog in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShowListDialogCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that shows the list dialog in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShowOptionsPaneCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that shows the options pane in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShowParagraphDialogCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that shows the paragraph dialog in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShowSpellingPaneCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that shows the spelling pane in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShowTableDialogCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that shows the table dialog in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ShowTableOptionsDialogCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that shows the table options dialog in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">SpaceKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform Space shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">StrikeThroughCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that apply `StrikeThrough` for the selected contents in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The strike through value to be set for current selection.</p>
<p style="margin-bottom: .0001pt; line-height: normal;">&nbsp;</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">TabKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform Tab shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">TableAlignmentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that apply table alignment for the selected table in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">`TableAlignment` value to apply for the selected table.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">TableLeftIndentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that apply left indent for the selected table in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The left indent value to be set for selected table.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">TextAlignmentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that apply text alignment for the selected paragraphs in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The text alignment value to be set for current selection.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ToggleBaselineAlignmentCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that toggles baseline alignment for the selected contents in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">`BaselineAlignment` value to apply for the selected contents.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ToggleBeforeSpacingCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that toggle before spacing for the selected paragraphs in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ToggleHighlightColorCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that toggle highlight color` for the selected contents in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">ToggleUnderlineCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that toggle underline for the selected contents in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The `Underline` value to be toggled.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">UnderlineCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that apply underline for the selected contents in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">The `Underline` value to be applied.</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">UndoCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that the last edit operation in a `SfRichTextBoxAdv` control be undone.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
<tr>
<td style="width: 198.0pt; border: solid windowtext 1.0pt; border-top: none; padding: 0pt 5.4pt 0pt 5.4pt;" width="264">
<p style="margin-bottom: .0001pt; line-height: normal;">UpKeyCommand</p>
</td>
<td style="width: 162.75pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="217">
<p style="margin-bottom: .0001pt; line-height: normal;">Represents the command that perform Up shortcut operation in a `SfRichTextBoxAdv` control.</p>
</td>
<td style="width: 114.2pt; border-top: none; border-left: none; border-bottom: solid windowtext 1.0pt; border-right: solid windowtext 1.0pt; padding: 0pt 5.4pt 0pt 5.4pt;" width="152">
<p style="margin-bottom: .0001pt; line-height: normal;">NA</p>
</td>
</tr>
</tbody>
</table>
