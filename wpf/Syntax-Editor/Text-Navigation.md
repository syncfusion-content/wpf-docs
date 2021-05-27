---
layout: post
title: Text Navigation in WPF Syntax Editor control | Syncfusion
description: Learn about Text Navigation support in Syncfusion Essential Studio WPF Syntax Editor control, its elements and more.
platform: wpf
control: Syntax Editor
 documentation: ug
---
# Text Navigation in WPF Syntax Editor

Syntax Editor offers extensive support to text navigation. Users can perform navigation between characters, words, and line items using the built-in functions or keyboard shortcut keys.

## Programmatic Navigation

### Character based navigation

The following functions enables text navigation in the Syntax Editor in terms of characters or columns.

1. [MoveToPreviousIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Edit.EditControl.html#Syncfusion_Windows_Edit_EditControl_MoveToPreviousIndex) to move cursor position in backward position. 

2. [MoveToNextIndex](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Edit.EditControl.html#Syncfusion_Windows_Edit_EditControl_MoveToNextIndex) to move cursor position in forward position in .

{% tabs %}

{% highlight C# %}

//To move cursor to previous index
this.editControl.MoveToPreviousIndex();

{% endhighlight %}

{% highlight VB %}

//To move cursor to previous index
Me.editControl.MoveToPreviousIndex()

{% endhighlight %}

{% endtabs %}


### Word based navigation

The following functions enables text navigation in the Syntax Editor in terms of words.

1. [MoveToNextWord](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Edit.EditControl.html#Syncfusion_Windows_Edit_EditControl_MoveToNextWord) moves cursor to start position of next word.

2. [MoveToPreviousWord](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Edit.EditControl.html#Syncfusion_Windows_Edit_EditControl_MoveToPreviousWord) moves cursor to start position of previous word.

{% tabs %}

{% highlight C# %}

//To move cursor to next word
this.editControl.MoveToNextWord();

{% endhighlight %}

{% highlight VB %}

//To move cursor to next word
Me.editControl.MoveToPreviousWord()

{% endhighlight %}

{% endtabs %}

### Line based navigation

The following functions enables text navigation in the Syntax Editor in terms of lines.

1. [MoveToNextLine](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Edit.EditControl.html#Syncfusion_Windows_Edit_EditControl_MoveToNextLine) to move cursor to same position on next line.

2. [MoveToPreviousLine](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Edit.EditControl.html#Syncfusion_Windows_Edit_EditControl_MoveToPreviousLine) to move cursor to same position on previous line.

3. [MoveToLineStart](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Edit.EditControl.html#Syncfusion_Windows_Edit_EditControl_MoveToLineStart) to move cursor to start postion of current line.

4. [MoveToLineEnd](https://help.syncfusion.com/cr/wpf/Syncfusion.Windows.Edit.EditControl.html#Syncfusion_Windows_Edit_EditControl_MoveToLineEnd) to move cursor to end postion of current line.

{% tabs %}

{% highlight C# %}

//To move cursor to next line
this.editControl.MoveToNextLine();

{% endhighlight %}

{% highlight VB %}

//To move cursor to next line
Me.editControl.MoveToNextLine()

{% endhighlight %}

{% endtabs %}

## Keyboard Navigation

The following keyboard shortcuts are supported for cursor navigation in Syntax Editor.

<table>
<tr>
<td>
<b> Navigation Shortcut Keys </b> <br/><br/></td><td>
<b> Descriptions </b> <br/><br/></td></tr>
<tr>
<td>
Right arrow<br/><br/></td><td>Moves the cursor to a position forward in the current line item.<br/><br/></td></tr>
<tr>
<td>
Left arrow<br/><br/></td><td>
Moves the cursor to the end position of the current line item.<br/><br/></td></tr>
<tr>
<td>
Down arrow<br/><br/></td><td>
Moves the cursor to the same position on the next line item.<br/><br/></td></tr>
<tr>
<td>
Up arrow<br/><br/></td><td>
Moves the cursor to the same position on the previous line item.<br/><br/></td></tr>
<tr>
<td>
Home<br/><br/></td><td>
Moves the cursor to the start position of the current line item.<br/><br/></td></tr>
<tr>
<td>
End<br/><br></td><td>
Moves the cursor to the end position of the current line item. <br/><br/></td></tr>
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
Ctrl + Home<br/><br/></td><td>
Moves the cursor to the document start position.<br/><br/></td></tr>
<tr>
<td>
Ctrl + End<br/><br/></td><td>
Moves the cursor to the end position of document. <br/><br/></td></tr>
</table>
