---
layout: post
title: Text Navigation in Syncfusion Syntax Editor
description: Explains about Text Navigation support in Syntax Editor for WPF
platform: wpf
control: Syntax Editor
documentation: ug
---
# Text Navigation

Syntax Editor offers extensive support for text navigation. User can perform navigation between characters, words, and line items using built-in functions or using Keyboard shortcut keys. This section briefly explains navigation of text in the Syntax Editor.

## Programmatic Navigation:

### Character based navigation:

The following functions enables text navigation in the Syntax Editor in terms of characters or columns.

<table>
<tr>
<td>
<b>Functions</b><br/><br/></td><td>
<b>Description</b><br/><br/></td></tr>
<tr>
<td>
MoveToPreviousIndex<br/><br/></td><td>
Moves the cursor to a position backward in current line item.<br/><br/></td></tr>
<tr>
<td>
MoveToNextIndex<br/><br/></td><td>
Moves the cursor to a position forward in current line item.<br/><br/></td></tr>
</table>

{% highlight C# %}

this.editControl.MoveToPreviousIndex();

this.editControl.MoveToNextIndex();

{% endhighlight %}

### Word based navigation

The following functions enables text navigation in the Syntax Editor in terms of words.

<table>
<tr>
<td>
<b>Functions</b><br/><br/></td><td>
<b>Description</b><br/><br/></td></tr>
<tr>
<td>
MoveToNextWord<br/><br/></td><td>
Moves the cursor to the start position of the next word.<br/><br/></td></tr>
<tr>
<td>
MoveToPreviousWord<br/><br/></td><td>
Moves the cursor to the start position of the previous word.<br/><br/></td></tr>
</table>

{% highlight C# %}

this.editControl.MoveToNextWord();

this.editControl.MoveToPreviousWord();

{% endhighlight %}

### Line based navigation

The following functions enables text navigation in the Syntax Editor in terms of lines.

<table>
<tr>
<td>
<b>Functions</b><br/><br/></td><td>
<b>Description</b><br/><br/></td></tr>
<tr>
<td>
MoveToNextLine<br/><br/></td><td>
Moves the cursor to the same position on the next line item.<br/><br/></td></tr>
<tr>
<td>
MoveToPreviousLine<br/><br/></td><td>
Moves the cursor to the same position on the previous line item.<br/><br/></td></tr>
<tr>
<td>
MoveToLineStart<br/><br/></td><td>
Moves the cursor to a start position of current line item.<br/><br/></td></tr>
<tr>
<td>
MoveToLineEnd<br/><br/></td><td>
Moves the cursor to an end position of current line item.<br/><br/></td></tr>
</table>

{% highlight C# %}

this.editControl.MoveToNextLine();

this.editControl.MoveToPreviousLine();

this.editControl.MoveToLineStart();

this.editControl.MoveToLineEnd();

{% endhighlight %}

## Keyboard Navigation

The following keyboard shortcuts are supported for cursor navigation in Syntax Editor.

<table>
<tr>
<td>
<b> Navigation Shortcut Keys </b> <br/><br/></td><td>
<b> Description </b> <br/><br/></td></tr>
<tr>
<td>
Right arrow<br/><br/><br/><br/></td><td>
Moves the cursor to a position forward in current line item.<br/><br/></td></tr>
<tr>
<td>
Left arrow<br/><br/><br/><br/></td><td>
Moves the cursor to an end position of current line item.<br/><br/></td></tr>
<tr>
<td>
Down arrow<br/><br/><br/><br/></td><td>
Moves the cursor to the same position on the next line item.<br/><br/></td></tr>
<tr>
<td>
Up arrow<br/><br/><br/><br/></td><td>
Moves the cursor to the same position on the previous line item.<br/><br/></td></tr>
<tr>
<td>
Home<br/><br/><br/><br/></td><td>
Moves the cursor to a start position of current line item <br/><br/></td></tr>
<tr>
<td>
End<br/><br/><br/><br/></td><td>
Moves the cursor to an end position of current line item <br/><br/></td></tr>
<tr>
<td>
Ctrl + Right arrow<br/><br/></td><td>
Moves the cursor to the start position of the next word.<br/><br/></td></tr>
<tr>
<td>
Ctrl + Left arrow<br/><br/></td><td>
Moves the cursor to the start position of the previous word.<br/><br/></td></tr>
<tr>
<td>
Ctrl + Home<br/><br/><br/><br/></td><td>
Moves the cursor to the document start position.<br/><br/><br/><br/></td></tr>
<tr>
<td>
Ctrl + End<br/><br/><br/><br/></td><td>
Moves the cursor to the document end position.<br/><br/></td></tr>
</table>
