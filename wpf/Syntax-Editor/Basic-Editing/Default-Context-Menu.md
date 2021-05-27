---
layout: post
title: Default Context Menu in WPF Syntax Editor control | Syncfusion
description: Learn about Default Context Menu support in Syncfusion WPF Syntax Editor control, its elements and more.
platform: wpf
control: Syntax Editor
documentation: ug
---

## Default Context Menu

ShowDefaultContextMenu

EditControl has a built-in context menu which enables users to easily perform common text editing operations. The default context menu can be enabled/disabled using `ShowDefaultContextMenu` property. By default, this property is set to `true`.

Set the ShowDefaultContextMenu property of EditControl by using the following code.

{% tabs %}

{% highlight XAML %}
<sfedit:EditControl x:Name="editControl" ShowDefaultContextMenu="True"/>


{% endhighlight %}

{% highlight C# %}
editControl.ShowDefaultContextMenu = true;



{% endhighlight %}

{% endtabs %}

The following image displays the Outlining Menu Expanded window.

![Default-Context-Menu_img1](Default-Context-Menu_images/Default-Context-Menu_img1.jpeg)


**Functionalities supported by EditControl’s ContextMenu**

EditControl’s built-in context menu supports the following functionalities.

<table>
<tr>
<td>
Command<br/><br/></td><td>
Usage<br/><br/></td></tr>
<tr>
<td>
Undo<br/><br/></td><td>
Revert the previous action performed in the EditControl<br/><br/></td></tr>
<tr>
<td>
Redo<br/><br/></td><td>
Performs the action again that was reverted using Undo command<br/><br/></td></tr>
<tr>
<td>
Cut<br/><br/></td><td>
Cut the selected text<br/><br/></td></tr>
<tr>
<td>
Copy<br/><br/></td><td>
Copy the selected text<br/><br/></td></tr>
<tr>
<td>
Paste<br/><br/></td><td>
Paste the text in the clipboard in the current cursor location.<br/><br/></td></tr>
<tr>
<td>
Select All<br/><br/></td><td>
Selects all the text in the EditControl<br/><br/></td></tr>
<tr>
<td>
Outlining -> Expand All <br/><br/></td><td>
Expands all the collapsed blocks in the text. This functionality is supported only when the EnableOutlining is set to `true` and the language supports outlining.<br/><br/></td></tr>
<tr>
<td>
Outlining -> Collapse All<br/><br/></td><td>
Hides all the blocks in the EditControl’s text. This functionality is supported only when the EnableOutlining is set to `true` and the language supports outlining.<br/><br/></td></tr>
<tr>
<td>
Increase Indent<br/><br/></td><td>
Appends a series of empty characters (tab) in front of the first valid character in the line. This command can be performed on an individual line or selected lines.<br/><br/></td></tr>
<tr>
<td>
Decrease Indent<br/><br/></td><td>
Removes a series of empty characters (tab) if any, in front of the first valid character in the line. This command can be performed on an individual line or selected lines<br/><br/></td></tr>
<tr>
<td>
Comment Lines<br/><br/></td><td>
It detects the supported comment Lexem from the Language configuration of EditControl’s current language and appends it to individual or multiple selected lines.<br/><br/></td></tr>
<tr>
<td>
Uncomment Line<br/><br/></td><td>
Removes the comment from the individual or selected lines.<br/><br/></td></tr>
</table>
