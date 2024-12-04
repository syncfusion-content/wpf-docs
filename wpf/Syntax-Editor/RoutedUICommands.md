---
layout: post
title: RoutedUICommands in WPF Syntax Editor control | Syncfusion
description: Learn about RoutedUICommands support in Syncfusion Essential Studio WPF Syntax Editor control, its elements and more.
platform: wpf
control: Syntax Editor
documentation: ug
---

# RoutedUICommands in WPF Syntax Editor

**EditCommands members**

The EditControl ships with a variety of built-in RoutedUICommands to perform various editing operations in it using commands. The EditCommands class in the Edit WPF library contains lot of necessary commands. The following are the list of RoutedUICommands available in the EditControl.

<table>
<tr>
<td>
RoutedUICommand<br/><br/></td>
<td>
Shortcut<br/><br/></td>
<td>
Description<br/><br/></td>
</tr>
<tr>
<td>
Backspace<br/><br/></td>
<td>
BACKSPACE<br/><br/></td>
<td>
Performs backspace key operations.<br/><br/></td>
</tr>
<tr>
<td>
CollapseAll<br/><br/></td>
<td>
N/A<br/><br/></td>
<td>
Collapses all the blocks in the EditControl text.<br/><br/></td>
</tr>
<tr>
<td>
CommentSelection<br/><br/></td>
<td>
CTRL+K+C, CTRL+E+C<br/><br/></td>
<td>
Selects comments or individual lines based on the selected language.<br/><br/></td>
</tr>
<tr>
<td>
Copy<br/><br/></td>
<td>
CTRL+C, CTRL+SHIFT+C, CTRL+INSERT<br/><br/></td>
<td>
Performs copying of text.<br/><br/></td>
</tr>
<tr>
<td>
Cut<br/><br/></td>
<td>
CTRL+X, CTRL+SHIFT+X, SHIFT+DELETE<br/><br/></td>
<td>
Cuts the text.<br/><br/></td>
</tr>
<tr>
<td>
Delete<br/><br/></td>
<td>
DELETE, CTRL+SHIFT+H<br/><br/></td>
<td>
Performs delete key operation.<br/><br/></td>
</tr>
<tr>
<td>
ExpandAll<br/><br/></td>
<td>
N/A<br/><br/></td>
<td>
Expands all the blocks in the EditControl text.<br/><br/></td>
</tr>
<tr>
<td>
Find<br/><br/></td>
<td>
CTRL+F<br/><br/></td>
<td>
Opens the find and replace window with the selected quick find tab.<br/><br/></td>
</tr>
<tr>
<td>
FindAllReferences<br/><br/></td>
<td>
SHIFT+F12<br/><br/></td>
<td>
Finds all the occurrences of the specified text.<br/><br/></td>
</tr>
<tr>
<td>
IncreaseIndent<br/><br/></td>
<td>
N/A<br/><br/></td>
<td>
Increases the indent of individual or selected lines.<br/><br/></td>
</tr>
<tr>
<td>
DecreaseIndent<br/><br/></td>
<td>
N/A<br/><br/></td>
<td>
Decreases the indent of individual or selected lines.<br/><br/></td>
</tr>
<tr>
<td>
InsertNewLine<br/><br/></td>
<td>
CTRL+ENTER<br/><br/></td>
<td>
Inserts a new line at the current cursor position.<br/><br/></td>
</tr>
<tr>
<td>
New<br/><br/></td>
<td>
CTRL+N<br/><br/></td>
<td>
Resets all the text in the EditControl.<br/><br/></td>
</tr>
<tr>
<td>
Open<br/><br/></td>
<td>
CTRL+O<br/><br/></td>
<td>
Opens an existing file and displays the OpenFileDialog to select the file.<br/><br/></td>
</tr>
<tr>
<td>
Paste<br/><br/></td>
<td>
CTRL+V, CTRL+SHIFT+V, SHIFT+INSERT<br/><br/></td>
<td>
Paste the copied text to the clipboard.<br/><br/></td>
</tr>
<tr>
<td>
Print<br/><br/></td>
<td>
CTRL+P<br/><br/></td>
<td>
Sends the EditControl content to a printer.<br/><br/></td>
</tr>
<tr>
<td>
PrintPreview<br/><br/></td>
<td>
CTRL+F2<br/><br/></td>
<td>
Displays a preview of the content to be printed.<br/><br/></td>
</tr>
<tr>
<td>
Redo<br/><br/></td>
<td>
CTRL+Y, CTRL+SHIFT+Y, CTRL+SHIFT+Z<br/><br/></td>
<td>
Performs redo operations.<br/><br/></td>
</tr>
<tr>
<td>
Replace<br/><br/></td>
<td>
CTRL+H<br/><br/></td>
<td>
Replaces the text specified in the Find What field with the field in Find and Replace window.<br/><br/></td>
</tr>
<tr>
<td>
Save<br/><br/></td>
<td>
CTRL+S<br/><br/></td>
<td>
Saves the text in the EditControl to a file. It displays the SaveFileDialog to enter the name and location to save the file.<br/><br/></td>
</tr>
<tr>
<td>
SaveAs<br/><br/></td>
<td>
N/A<br/><br/></td>
<td>
Allows the user to save the file under a new name or location.<br/><br/></td>
</tr>
<tr>
<td>
Search<br/><br/></td>
<td>
F3<br/><br/></td>
<td>
Finds the text specified in the last search, without opening the Find and Replace window.<br/><br/></td>
</tr>
<tr>
<td>
SearchInSelected<br/><br/></td>
<td>
CTRL+F3<br/><br/></td>
<td>
Finds the text specified in the last search within the selected text, without opening the Find and Replace window.<br/><br/></td>
</tr>
<tr>
<td>
SelectAll<br/><br/></td>
<td>
CTRL+A<br/><br/></td>
<td>
Selects all the text in EditControl.<br/><br/></td>
</tr>
<tr>
<td>
ShowIntellisense<br/><br/></td>
<td>
CTRL+SPACE, CTRL+J<br/><br/></td>
<td>
Displays the provided IntellisensePopup if the IntelliSense items are not empty.<br/><br/></td>
</tr>
<tr>
<td>
UncommentSelection<br/><br/></td>
<td>
CTRL+K+U<br/><br/></td>
<td>
Removes the comment Lexem from individual or selected lines.<br/><br/></td>
</tr>
<tr>
<td>
Undo<br/><br/></td>
<td>
CTRL+Z<br/><br/></td>
<td>
Performs undo operations.<br/><br/></td>
</tr>
</table>