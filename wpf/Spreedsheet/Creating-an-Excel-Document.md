---
layout: post
title: Creating-an-Excel-Document
description: creating an excel document 
platform: wpf
control: Spreadsheet
documentation: ug
---

# Creating an Excel Document 

When you add the Spreadsheet control to the application, it will be loaded with a blank workbook. You can save this as an Excel document. You can also create new workbooks if required.

To create a new workbook, call the New method. New workbook will be created with three worksheets by default. The following code illustrates this:



<table>
<tr>
<td>
[C#]spreadControl.New();</td></tr>
<tr>
<td>
 [VB]spreadControl.New()</td></tr>
</table>


You can also specify the number of worksheet you want to add in workbook by passing the sheet count to the New method. The following code illustrates this:



<table>
<tr>
<td>
[C#]spreadControl.New(3);</td></tr>
<tr>
<td>
 [VB]spreadControl.New(3)</td></tr>
</table>


Using Command

You can also use the NewCommand to create the Excel document. By default when you execute the NewCommand it will create the workbook with three worksheets and you can also specify the number of worksheet you want to add in workbook by passing the sheet count as Command parameter. 

The following code illustrates how to bind the NewCommand__to a button: 



[XAML]

&lt;Button Command="{Binding Path=NewCommand}"/&gt;



