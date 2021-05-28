---
layout: post
title: Command Support in WPF Wizard Control control | Syncfusion
description: Learn here all about Command Support in Syncfusion WPF SpreadsheetControl (Classic) control, its elements and more.
platform: wpf
control: Spreadsheet
 documentation: ug
---

# Command Support in WPF SpreadsheetControl (Classic)

The Spreadsheet control provides the built-in commands to show case the features available in Spreadsheet. It can be executed in the Spreadsheet whenever it is bound to Command Property. 

### Commands Table

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Data Type</th><th>
Reference links</th></tr>
<tr>
<td>
BoldCommand</td><td>
Command which will toggle bold.</td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
ItalicCommand</td><td>
Command which will toggle Italics.</td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
UnderlineCommand</td><td>
Command to change the underline.</td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
CopyCommand</td><td>
Command to copy the selected cells.</td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
CutCommand</td><td>
Command to cut the selected cells.</td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
PasteCommand</td><td>
Command to paste the cells from the clipboard. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
ColumnWidthCommand </td><td>
Command to customize the column width.</td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
ConditionalFormatCommand</td><td>
Command to apply conditional formatting for the selected cells. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
DataValidationCommand</td><td>
Command to apply data validation for the selected cells.</td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
DeleteCommentCommand</td><td>
Command to delete the comment. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
DeleteColumnCommand</td><td>
Command to delete column.</td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
DeleteRowCommand</td><td>
Command to delete row. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
DeleteCurrentSheetCommand</td><td>
Command to delete current sheet. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
EncryptCommand</td><td>
Command to encrypt the workbook.</td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
ExportToExcelCommand</td><td>
Command to save the workbook as Excel. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
FormatAsTableCommand</td><td>
Command to format as table. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
HyperlinkCommand</td><td>
Command to insert hyperlink. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
ImportFromExcelCommand</td><td>
Command to import the Excel document to Spreadsheet. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
InsertCommentCommand</td><td>
Command to insert comment. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
InsertPictureCommand</td><td>
Command to insert picture.</td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
InsertRowCommand</td><td>
Command to insert row. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
InsertSheetCommand</td><td>
Command to insert worksheet. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
ProtectCurrentSheetCommand</td><td>
Command to protect current worksheet. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
ProtectWorkbookCommand</td><td>
Command to protect workbook. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
RowHeightCommand</td><td>
Command to customize row height. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
ShowGridLinesCommand</td><td>
Command to show or hide gridlines.</td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
<tr>
<td>
RowColumnHeadersVisibilityCommand </td><td>
Command to show or hide row and column header. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
NA</td></tr>
</table>


### Parameterized Commands

<table>
<tr>
<th>
Property</th><th>
Description</th><th>
Type</th><th>
Data Type</th><th>
Reference links</th></tr>
<tr>
<td>
BorderCommand</td><td>
Command to customize the cell border. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
String</td><td>
NA</td></tr>
<tr>
<td>
FreezePaneCommand</td><td>
Command to freeze rows and column. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
Freeze</td><td>
NA</td></tr>
<tr>
<td>
HideColumnCommand</td><td>
Command to hide the column. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
</td><td>
NA</td></tr>
<tr>
<td>
HideRowCommand</td><td>
Command to hide the row. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
Boolean </td><td>
NA</td></tr>
<tr>
<td>
HideCurrentSheetCommand</td><td>
Command to hide the current sheet.</td><td>
Dependency Property</td><td>
CommandBase</td><td>
Boolean</td><td>
NA</td></tr>
<tr>
<td>
VerticalAlignmentCommand </td><td>
Command to align the cells vertically. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
String</td><td>
NA</td></tr>
<tr>
<td>
MergeCommand </td><td>
Command to merge the cells.</td><td>
Dependency Property</td><td>
CommandBase</td><td>
String</td><td>
NA</td></tr>
<tr>
<td>
NewCommand </td><td>
Command to add new workbook. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
Int</td><td>
Creating an Excel Document</td></tr>
<tr>
<td>
NumberFormatCommand </td><td>
Command to apply number formatting. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
String</td><td>
NA</td></tr>
<tr>
<td>
IncreaseDecimalCommand  </td><td>
Command to increase decimal places.</td><td>
Dependency Property</td><td>
CommandBase</td><td>
Boolean</td><td>
NA</td></tr>
<tr>
<td>
IncreaseIndentCommand </td><td>
Command to increase text margin.</td><td>
Dependency Property</td><td>
CommandBase</td><td>
Boolean</td><td>
NA</td></tr>
<tr>
<td>
InsertColumnCommand </td><td>
Command to insert column.</td><td>
Dependency Property</td><td>
CommandBase</td><td>
Boolean</td><td>
NA</td></tr>
<tr>
<td>
HorizontalAlignmentCommand  </td><td>
Command to align the cells horizontally. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
String</td><td>
NA</td></tr>
<tr>
<td>
CellStyleCommand </td><td>
Command to apply cell style.</td><td>
Dependency Property</td><td>
CommandBase</td><td>
BuiltInStyles</td><td>
NA</td></tr>
<tr>
<td>
FontFamilyCommand </td><td>
Command to specify the font family.</td><td>
Dependency Property</td><td>
CommandBase</td><td>
String</td><td>
NA</td></tr>
<tr>
<td>
FontSizeCommand </td><td>
Command to specify the font size. </td><td>
Dependency Property</td><td>
CommandBase</td><td>
Double</td><td>
NA</td></tr>
</table>