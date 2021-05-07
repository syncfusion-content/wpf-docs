---
layout: post
title: Text Selection in WPF Syntax Editor control | Syncfusion
description: Learn about Text Selection support in Syncfusion Essential Studio WPF Syntax Editor control, its elements and more.
platform: wpf
control: Syntax Editor
documentation: ug
---

# Text Selection in WPF Syntax Editor

The `SyntaxEditor` control supports the selection of content through mouse, keyboard, and touch interactions. 

## Selection using Mouse

User can select text using the mouse by clicking on a position and dragging the selection to the desired line position. 

## Selection using Keyboard with shortcuts

The following keyboard shortcuts are supported for content selection.

<table>
<tr>
<td>
Selection Shortcut Keys<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
Shift + Right arrow<br/><br/></td><td>
Extends selection one position forward.<br/><br/></td></tr>
<tr>
<td>
Shift + Left arrow<br/><br/></td><td>
Extends selection one position backward.<br/><br/></td></tr>
<tr>
<td>
Shift + Down arrow<br/><br/></td><td>
Extends selection to the same position on the next line.<br/><br/></td></tr>
<tr>
<td>
Shift + Up arrow<br/><br/></td><td>
Extends selection to the same position on the previous line.<br/><br/></td></tr>
<tr>
<td>
Shift + Home<br/><br/></td><td>
Extends selection to the start of the current line.<br/><br/></td></tr>
<tr>
<td>
Shift + End<br/><br/></td><td>
Extends selection to the end of the current line.<br/><br/></td></tr>
<tr>
<td>
Ctrl + Shift + Home<br/><br/></td><td>
Extends selection to the document start position.<br/><br/></td></tr>
<tr>
<td>
Ctrl + Shift + End<br/><br/></td><td>
Extends selection to the document end position.<br/><br/></td></tr>
<tr>
<td>
Ctrl + Shift + Right arrow<br/><br/></td><td>
Extends selection to the current word end position.<br/><br/></td></tr>
<tr>
<td>
Ctrl + Shift + Left arrow<br/><br/></td><td>
Extends selection to the current word start position.<br/><br/></td></tr>
<tr>
<td>
Ctrl + A<br/><br/></td><td>
Selects the entire document.<br/><br/></td></tr>
</table>

## Selection using Touch 

Users can select text by double-tapping the desired word. Selection pointers will be displayed at the start and end positions of the selected content. 

![Selection using touch](Selection-Images/selection-img1.png)


Users can extend the selection by dragging the selection pointers. The following screenshot shows an extended selection of content.

![Selection using touch](Selection-Images/selection-img2.png)

When a selection goes beyond the view port of the SyntaxEditor control, a scroll viewer will automatically bring new content into the view and the text selection will extend to that content.

