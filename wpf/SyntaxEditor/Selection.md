---
layout: post
title: Text Selection in EditControl 
description: Explains about Text selection of the Edit Control for WPF
platform: wpf
control: Syntax Editor
documentation: ug
---

# Text Selection

SyntaxEditor supports selection of content through UI interactions such as Mouse, Keyboard and Touch. 

## Selection using Mouse

User can do selection using mouse by clicking on the desired position and drag the selection to desired line position. Selection of content can be extended through Keyboard selection. This will be explained in Keyboard selection section.

## Selection using Keyword with shortcuts

The following keyboard shortcuts are supported by SyntaxEditor for selection.

<table>
<tr>
<td>
Selection Shortcut<br/><br/></td><td>
Description<br/><br/></td></tr>
<tr>
<td>
SHIFT + Right Arrow<br/><br/></td><td>
Extends selection to one position forward.<br/><br/></td></tr>
<tr>
<td>
SHIFT + Left Arrow<br/><br/></td><td>
Extends selection to one position backward.<br/><br/></td></tr>
<tr>
<td>
SHIFT + Down Arrow<br/><br/></td><td>
Extends selection to the same position at next line.<br/><br/></td></tr>
<tr>
<td>
SHIFT + Up Arrow<br/><br/></td><td>
Extends selection to the same position at previous line.<br/><br/></td></tr>
<tr>
<td>
SHIFT + Home<br/><br/></td><td>
Extends selection to start of the current line.<br/><br/></td></tr>
<tr>
<td>
SHIFT + End<br/><br/></td><td>
Extends selection to end of the current line.<br/><br/></td></tr>
<tr>
<td>
CTRL + SHIFT + Home<br/><br/></td><td>
Extends selection to the document start position.<br/><br/></td></tr>
<tr>
<td>
CTRL + SHIFT + End<br/><br/></td><td>
Extends selection to the document end position.<br/><br/></td></tr>
<tr>
<td>
CTRL + SHIFT + Right<br/><br/></td><td>
Extends selection to the current word end position.<br/><br/></td></tr>
<tr>
<td>
CTRL + SHIFT + Left<br/><br/></td><td>
Extends selection to the current word start position.<br/><br/></td></tr>
<tr>
<td>
CTRL + A<br/><br/></td><td>
Selects the entire document.<br/><br/></td></tr>
</table>

## Selection using Touch 

User can do selection by double touch the desired word. Selection pointers will be displayed at start and end position of the selected content. 

![](Selection-Images/selection-img1.jpeg)


User can extend the selection by dragging the selection pointers. The following screenshot shows the extend selection of selected content.

![](Selection-Images/selection-img2.jpeg)

When selection goes beyond viewport of EditControl, ScrollViewer will be automatically bring new contents to the view and text selection will happen to those contents.


