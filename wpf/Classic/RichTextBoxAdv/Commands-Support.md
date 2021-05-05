---
layout: post
title: Commands-Support in WPF RichTextBoxAdv Control | Syncfusion
description: Learn here all about Commands-Support in Syncfusion WPF RichTextBoxAdv (Classic) control, its elements and more.
platform: wpf
control: RichTextBoxAdv
documentation: ug
---

# Commands-Support in WPF RichTextBoxAdv (Classic)

The RichTextBoxAdv control provides built-in static commands that showcase the features available in RichTextBoxAdv.

### Properties





<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Data Type</th></tr>
<tr>
<td>
AfterSpacing</td><td>
Command to change the spacing after.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
BeforeSpacing</td><td>
Command to change the spacing before.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
ToggleBold</td><td>
Command which will toggle bold.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
ChangeFontFamily</td><td>
Command to change font family of the selected text.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
ChangeFontSize</td><td>
Command to change font size of the selected text.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
HighlightColor</td><td>
Command to change highlight color of the selected text.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
TextColor</td><td>
Command to change font color.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
Copy</td><td>
Command to copy the selected text.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
Cut</td><td>
Command to cut the selected text.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
ToggleStrikeThrough</td><td>
Command to change the strikethrough of the text.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
FontDialog</td><td>
Command to show the built-in Font dialog box.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
ToggleItalic</td><td>
Command which will toggle italics.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
HyperlinkDialog</td><td>
Command to show the built-in Hyperlink dialog box.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
LeftIndent</td><td>
Command to change the left indent of the paragraph.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
RightIndent</td><td>
Command to change the right indent of the paragraph.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
ParagraphDialog</td><td>
Command to show the built-in Paragraph dialog box.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
Open</td><td>
Command to show the Open dialog and open a document.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
Save</td><td>
Command to open the Save dialog and save the document.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
Paste</td><td>
Command to paste the copied text.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
ToggleSubScript</td><td>
Command which will toggle subscript.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
ToggleSuperScript</td><td>
Command which will toggle superscript.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
TextAlignment</td><td>
Command to change the text alignment of the paragraph.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
ToggleUnderline</td><td>
Command to change the underline.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
New</td><td>
Command to create a new document.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
Print</td><td>
Command to show the built-in Print dialog box.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
ListType</td><td>
Command to apply bullets and numbering to lists.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
Undo</td><td>
Command to undo the previous operation.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
Redo</td><td>
Command to redo the previous operation.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
ChangeLayout</td><td>
Command to change the layout mode.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
ToggleDoubleStrikeThrough</td><td>
Command to apply a double strikethrough.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
LineSpacing</td><td>
Command to change the line spacing.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
InsertTable</td><td>
Command to insert a table.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
InsertRow</td><td>
Command to insert a row.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
InsertColumn</td><td>
Command to insert a column.</td><td>
Command</td><td>
RoutedUICommand.</td></tr>
<tr>
<td>
DeleteRow</td><td>
Command to delete the row.</td><td>
Command</td><td>
RoutedUICommand.</td></tr>
<tr>
<td>
DeleteColumn</td><td>
Command to delete the column.</td><td>
Command</td><td>
RoutedUICommand.</td></tr>
<tr>
<td>
DeleteTable</td><td>
Command to delete the table.</td><td>
Command</td><td>
RoutedUICommand.</td></tr>
<tr>
<td>
InsertTableDialog</td><td>
Command to open the built-in Table dialog.</td><td>
Command</td><td>
RoutedUICommand.</td></tr>
<tr>
<td>
SelectCell</td><td>
Command to select a cell.</td><td>
Command</td><td>
RoutedUICommand.</td></tr>
<tr>
<td>
SelectRow</td><td>
Command to select a row.</td><td>
Command</td><td>
RoutedUICommand</td></tr>
<tr>
<td>
SelectColumn</td><td>
Command to select a column.</td><td>
Command</td><td>
RoutedUICommand.</td></tr>
<tr>
<td>
SelectTable</td><td>
Command to select a table.</td><td>
Command</td><td>
RoutedUICommand.</td></tr>
</table>


