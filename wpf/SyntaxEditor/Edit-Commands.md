---
layout: post
title: Edit Commands of the Edit Control for WPF
description: Explains about Edit Commands of the Edit Control for WPF
platform: wpf
control: Syntax Editor
documentation: ug
---

# Edit Commands

Essential edit for WPF contains built-in RoutedUICommands for all editing and file operations such as select all, cut, copy, paste, new, open, save, and so on. The built-in RoutedUICommands can be bound to the edit control by using the Command property of the external controls such as button, menu item, and so on. 

<table>
<tr>
<th>
RoutedUICommands<br/><br/></th><th>
Description<br/><br/></th>
</tr>
<td>
New<br/><br/></td><td>
This command helps to create the new editor.<br/><br/></td></tr>
<tr>
<td>
Open<br/><br/></td><td>
This command helps to open the required document in EditControl<br/><br/></td></tr>
<tr>
<td>
Save<br/><br/></td><td>
This Command helps to save the EditControl content.<br/><br/></td></tr>
<tr>
<td>
Copy<br/><br/></td><td>
This Command helps to copy the selected Editcontrol control.<br/><br/></td></tr>
<tr>
<td>
Cut<br/><br/></td><td>
This Command helps to cut the selected Editcontrol control.<br/><br/></td></tr>
<tr>
<td>
Paste<br/><br/></td><td>
This Command helps to paste the content in EditControl.<br/><br/></td></tr>
<tr>
<td>
SelectAll<br/><br/></td><td>
This Command helps to select the all contents in EditControl.<br/><br/></td></tr>
<tr>
<td>
Outlining<br/><br/></td><td>
This command helps to outlining support<br/><br/></td></tr>
<tr>
<td>
Undo<br/><br/></td><td>
This command helps to perform the Undo action.<br/><br/></td></tr>
<tr>
<td>
Redo<br/><br/></td><td>
This command helps to perform the Redo action.<br/><br/></td></tr>
<tr>
<td>
Delete<br/><br/></td><td>
This command helps to delete the selected text in EditControl.<br/><br/></td></tr>
<tr>
<td>
Backspace<br/><br/></td><td>
This command also helps to clear the content in EditControl.<br/><br/></td></tr>
<tr>
<td>
ExpandAll<br/><br/></td><td>
This Command helps to expand the text<br/><br/></td></tr>
<tr>
<td>
CollapseAll<br/><br/></td><td>
This command helps to collapse the text<br/><br/></td></tr>
<tr>
<td>
Find<br/><br/></td><td>
This command helps to open the find operation window.<br/><br/></td></tr>
<tr>
<td>
Replace<br/><br/></td><td>
This command helps to open the replace window.<br/><br/></td></tr>
<tr>
<td>
Search<br/><br/></td><td>
This command helps for search operation.<br/><br/></td></tr>
<tr>
<td>
SearchInSelected<br/><br/></td><td>
This command helps for Search Text in selected text operation.<br/><br/></td></tr>
<tr>
<td>
FindAllReferences<br/><br/></td><td>
This command helps for find all reference operation.<br/><br/></td></tr>
<tr>
<td>
ShowIntellisense<br/><br/></td><td>
This command helps to display intellisense pop-up in the EditControl.<br/><br/></td></tr>
<tr>
<td>
IncreaseIndent<br/><br/></td><td>
This command helps to increases the indent of individual or selected lines.<br/><br/></td></tr>
<tr>
<td>
DecreaseIndent<br/><br/></td><td>
This command helps to decrease the indent of individual or selected lines.<br/><br/></td></tr>
<tr>
<td>
CommentSelection<br/><br/></td><td>
This command helps to comment the selected line.<br/><br/></td></tr>
<tr>
<td>
UncommentSelection<br/><br/></td><td>
This command helps to uncomment the selected line.<br/><br/></td></tr>
<tr>
<td>
InsertNewLine<br/><br/></td><td>
This command helps to insert the new line.<br/><br/></td></tr>
<tr>
<td>
AutoIndent<br/><br/></td><td>
This command helps for Auto indention.<br/><br/></td></tr>
<tr>
<td>
Print<br/><br/></td><td>
This command helps to perform print action.<br/><br/></td></tr>
<tr>
<td>
PrintPreview<br/><br/></td><td>
This command helps to show the print preview window.<br/><br/></td></tr>
</table>


The following lines of code can be used to bind the RoutedUICommands with external controls.


{% tabs %}

{% highlight XAML %}

<MenuItem Header="New" Command="{x:Static syncfusion:EditCommands.New}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="Open"  Command="{x:Static syncfusion:EditCommands.Open}" CommandTarget="{Binding ElementName=editcontrol}"/>

<MenuItem Header="Save"  Command="{x:Static syncfusion:EditCommands.Save}" CommandTarget="{Binding ElementName=editcontrol}"/>

<MenuItem Header="Cut"  Command="{x:Static syncfusion:EditCommands.Cut}" CommandTarget="{Binding ElementName=editcontrol}"  />

<MenuItem Header="Copy" Command="{x:Static syncfusion:EditCommands.Copy}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="Paste" Command="{x:Static syncfusion:EditCommands.Paste}" CommandTarget="{Binding ElementName=editcontrol}"  />

<MenuItem Header="SelectAll" Command="{x:Static syncfusion:EditCommands.SelectAll}" CommandTarget="{Binding ElementName=editcontrol}"  />

<MenuItem Header="Delete" Command="{x:Static syncfusion:EditCommands.Delete}" CommandTarget="{Binding ElementName=editcontrol}"  />

<MenuItem Header="BackSpace" Command="{x:Static syncfusion:EditCommands.Backspace}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="Undo" Command="{x:Static syncfusion:EditCommands.Undo}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="Redo" Command="{x:Static syncfusion:EditCommands.Redo}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="ExpandAll"   Command="{x:Static syncfusion:EditCommands.ExpandAll}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="CollapseAll" Command="{x:Static syncfusion:EditCommands.CollapseAll}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="IncreaseIndent" Command="{x:Static syncfusion:EditCommands.IncreaseIndent}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="DecreaseIndent" Command="{x:Static syncfusion:EditCommands.DecreaseIndent}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="CommentSelection" Command="{x:Static syncfusion:EditCommands.CommentSelection}" CommandTarget="{Binding ElementName=editcontrol}"  />

<MenuItem Header="UnCommentSelection" Command="{x:Static syncfusion:EditCommands.UnCommentSelection}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="InsertNewLine" Command="{x:Static syncfusion:EditCommands.InsertNewLine}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="AutoIndent" Command="{x:Static syncfusion:EditCommands.AutoIndent}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="ShowIntellisense" Command="{x:Static syncfusion:EditCommands.ShowIntellisense}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="Outlining" Command="{x:Static syncfusion:EditCommands.Outlining}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="Find" Command="{x:Static syncfusion:EditCommands.Find}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="Search" Command="{x:Static syncfusion:EditCommands.Search}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="Replace" Command="{x:Static syncfusion:EditCommands.Replace}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="FindAllReferences" Command="{x:Static syncfusion:EditCommands.FindAllReferences}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="SearchInSelected" Command="{x:Static syncfusion:EditCommands.SearchInSelected}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="Print" Command="{x:Static syncfusion:EditCommands.Print}" CommandTarget="{Binding ElementName=editcontrol}" />

<MenuItem Header="PrintPreview" Command="{x:Static syncfusion:EditCommands.PrintPreview}" CommandTarget="{Binding ElementName=editcontrol}" />

<!--EditControl-->

<syncfusion:EditControl x:Name="editcontrol" Grid.Row="1" Focusable="True"/>

{% endhighlight %}

{% highlight C# %}

//This command helps to create the new editor 

EditCommands.New.Execute(null, this.editcontrol);

//This command helps to open the required document in EditControl 

EditCommands.Open.Execute(null, this.editcontrol);

//This Command helps to save the EditControl content

EditCommands.Save.Execute(null, this.editcontrol);

//This Command helps to cut the selected Editcontrol control. 

EditCommands.Cut.Execute(null, this.editcontrol);

//This command helps to copy the selected EditControl content. 

EditCommands.Copy.Execute(null, this.editcontrol);

//This Command helps to paste the content in EditControl. 

EditCommands.Paste.Execute(null, this.editcontrol);

//This command helps to delete the selected text in EditControl 

EditCommands.Delete.Execute(null, this.editcontrol);

//This command also helps to clear the content in EditControl. 

EditCommands.Backspace.Execute(null, this.editcontrol);

//This command helps to perform the Undo action.

EditCommands.Undo.Execute(null, this.editcontrol);

//This command helps to perform the Redo action. 

EditCommands.Redo.Execute(null, this.editcontrol);

//This Command helps to expand the text 

EditCommands.ExpandAll.Execute(null, this.editcontrol);

//This command helps to collapse the text 

EditCommands.CollapseAll.Execute(null, this.editcontrol);

//This command helps to increases the indent of individual or selected lines.

EditCommands.IncreaseIndent.Execute(null, this.editcontrol);

//This command helps to decrease the indent of individual or selected lines.

EditCommands.DecreaseIndent.Execute(null, this.editcontrol);

//This command helps to comment the selected line.

EditCommands.CommentSelection.Execute(null, this.editcontrol);

//This command helps to uncomment the selected line.

EditCommands.UncommentSelection.Execute(null, this.editcontrol);

//This command helps to insert the new line.

EditCommands.InsertNewLine.Execute(null, this.editcontrol);

//This command helps for Auto indention.

EditCommands.AutoIndent.Execute(null, editcontrol);

//This command helps to perform print action.

EditCommands.Print.Execute(null, this.editcontrol);

This command helps to show the print preview window.

EditCommands.PrintPreview.Execute(null, this.editcontrol);

//This command helps to display intellisense pop-up in the EditControl.

EditCommands.ShowIntellisense.Execute(null, this.editcontrol);

//This command helps to outlining support.

EditCommands.Outlining.Execute(null, this.editcontrol);

//This command helps to open the find operation window.

EditCommands.Find.Execute(null, this.editcontrol);

//This command helps for search operation.

EditCommands.Search.Execute(null, this.editcontrol);

//This command helps to open the replace window.

EditCommands.Replace.Execute(null, this.editcontrol);

//This command helps for find all reference operation.

EditCommands.FindAllReferences.Execute(null, this.editcontrol);

//This command helps for Search Text in selected text operation

EditCommands.SearchInSelected.Execute("null", this.editcontrol);

//This Command helps to select the all contents in EditControl

EditCommands.SelectAll.Execute(null, this.editcontrol);

{% endhighlight %}

{% highlight VB %}

'This command helps to create the new editor.

EditCommands.[New].Execute(Nothing, Me.editcontrol)

'This command helps to open the required document in EditControl

EditCommands.Open.Execute(Nothing, Me.editcontrol)

'This Command helps to save the EditControl content

EditCommands.Save.Execute(Nothing, Me.editcontrol)

'This Command helps to cut the selected Editcontrol control.

EditCommands.Cut.Execute(Nothing, Me.editcontrol)

'This command helps to copy the selected EditControl content.

EditCommands.Copy.Execute(Nothing, Me.editcontrol)

'This Command helps to paste the content in EditControl.

EditCommands.Paste.Execute(Nothing, Me.editcontrol)

'This command helps to delete the selected text in EditControl

EditCommands.Delete.Execute(Nothing, Me.editcontrol)

'This command also helps to clear the content in EditControl.

EditCommands.Backspace.Execute(Nothing, Me.editcontrol)

'This command helps to perform the Undo action.

EditCommands.Undo.Execute(Nothing, Me.editcontrol)

'This command helps to perform the Redo action.

EditCommands.Redo.Execute(Nothing, Me.editcontrol)

'This Command helps to expand the text

EditCommands.ExpandAll.Execute(Nothing, Me.editcontrol)

'This command helps to collapse the text

EditCommands.CollapseAll.Execute(Nothing, Me.editcontrol)

'This command helps to increases the indent of individual or selected lines.

EditCommands.IncreaseIndent.Execute(Nothing, Me.editcontrol)

'This command helps to decrease the indent of individual or selected lines.

EditCommands.DecreaseIndent.Execute(Nothing, Me.editcontrol)

'This command helps to comment the selected line.

EditCommands.CommentSelection.Execute(Nothing, Me.editcontrol)

'This command helps to uncomment the selected line.

EditCommands.UncommentSelection.Execute(Nothing, Me.editcontrol)

'This command helps to insert the new line.

EditCommands.InsertNewLine.Execute(Nothing, Me.editcontrol)

'This command helps for Auto indention.

EditCommands.AutoIndent.Execute(Nothing, editcontrol)

'This command helps to perform print action.

EditCommands.Print.Execute(Nothing, Me.editcontrol)

'This command helps to show the print preview window.

EditCommands.PrintPreview.Execute(Nothing, Me.editcontrol)

'This command helps to display intellisense pop-up in the EditControl.

EditCommands.ShowIntellisense.Execute(Nothing, Me.editcontrol)

'This command helps to outlining support.

EditCommands.Outlining.Execute(Nothing, Me.editcontrol)

'This command helps to open the find operation window.

EditCommands.Find.Execute(Nothing, Me.editcontrol)

'This command helps for search operation.

EditCommands.Search.Execute(Nothing, Me.editcontrol)

'This command helps to open the replace window.

EditCommands.Replace.Execute(Nothing, Me.editcontrol)

'This command helps for find all reference operation.

EditCommands.FindAllReferences.Execute(Nothing, Me.editcontrol)

'This command helps for Search Text in selected text operation

EditCommands.SearchInSelected.Execute(“null”, Me.editcontrol)

'This Command helps to select the all contents in EditControl

EditCommands.SelectAll.Execute(Nothing, Me.editcontrol)

{% endhighlight %}

{% endtabs %}

N> Please find the [EditControlRoutedUICommand Sample](http://www.syncfusion.com/downloads/support/directtrac/214194/ze/EditControl_Command1758422738.zip) which uses all RoutedUICommands.
