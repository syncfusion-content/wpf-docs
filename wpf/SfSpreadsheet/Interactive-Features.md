---
layout: post
title: Interactive Features | SfSpreadsheet | WPF | Syncfusion
description: interactive features
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Interactive Features

 This section explains about the interactive operations with SfSpreadsheet
  
## Clipboard Operations

SfSpreadsheet provides support for all the clipboard operations to with all the format settings when copied within a workbook. When the content is copied from external source, SfSpreadsheet does not support the format settings (paste options). 

You can use the following shortcut keys for Clipboard operations like Excel
<table>
<tr>
<th>
Operations</th><th>
Shortcut Keys</th></tr>
<tr>
<td>
Cut</td><td>
Ctrl + X</td></tr>
<tr>
<td>
Copy</td><td>
Ctrl + C </td></tr>
<tr>
<td>
Paste</td><td>
Ctrl + V</td></tr>
</table>

The following are a list of paste options used while performing paste operation,

<table>
<tr>
<th>
Options</th><th>
Description</th></tr>
<tr>
<td>
Paste</td><td>
To paste with all the format options in the source range</td></tr>
<tr>
<td>
Formula</td><td>
To paste the formulas alone </td></tr>
<tr>
<td>
Keep Source Formatting</td><td>
To maintain the source range’s formatting</td></tr>
<tr>
<td>
Value</td><td>
To paste the values alone</td></tr>
<tr>
<td>
Format</td><td>
To paste only the formats alone without pasting the values.</td></tr>
<tr>
<td>
Value & Source Formatting</td><td>
To maintain the source range original format and paste only values</td></tr>
</table>

For [Cut](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic6411.html) Operation,

{% highlight c# %}
			
    //To perform cut operation for selected ranges

    var range = spreadsheet.ActiveGrid.SelectedRanges.ActiveRange;

    spreadsheet.ActiveGrid.CopyPaste.Copy(range, true);

    //To perform cut operation

    spreadsheet.ActiveGrid.CopyPaste.Cut();

{% endhighlight %}

For [Copy](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic6405.html) Operation,

{% highlight c# %}

    //To perform copy operation for selected ranges

    var range = spreadsheet.ActiveGrid.SelectedRanges.ActiveRange;

    spreadsheet.ActiveGrid.CopyPaste.Copy(range, false);

    //To perform Copy operation

    spreadsheet.ActiveGrid.CopyPaste.Copy();

{% endhighlight %}

For [Paste](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic6416.html) Operation,

{% highlight c# %}

    //To perform paste operation

    spreadsheet.ActiveGrid.CopyPaste.Paste();

    //To perform paste operation with range and Paste Options

    var copyPaste = spreadsheet.ActiveGrid.CopyPaste as SpreadsheetCopyPaste;

    copyPaste.Paste(range);

    copyPaste.Paste(range, PasteOptions.Paste);

{% endhighlight %}
<br/>

## Undo/Redo

SfSpreadsheet provides support for Undo/Redo functionality like MS Excel.

The shortcut keys used for Undo/Redo Operations

<table>
<tr>
<th>
Operations</th><th>
Shortcut Keys</th></tr>
<tr>
<td>
Undo</td><td>
Ctrl + Z</td></tr>
<tr>
<td>
Redo</td><td>
Ctrl + Y</td></tr>
</table>

SfSpreadsheet has [History Manager](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic8527.html) class that supports the implementation of undo/ redo operations

To invoke Undo/Redo operations, the [Enabled](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic8543.html) property of [History Manager](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic8527.html) needs to be true.  

{% highlight c# %}

    spreadsheet.HistoryManager.Enabled = true;

    spreadsheet.HistoryManager.Undo();

    spreadsheet.HistoryManager.Redo();

{% endhighlight %}
<br/>

## Context menu

Context menu in SfSpreadsheet is customizable menu which can be used for various functionalities

### TabItem context menu

By default, [AllowTabItemContextMenu](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic6318.html) property is set to true to enable the TabItemContext Menu in SfSpreadsheet. Default TabItem context menu has options like Insert, Delete, Hide/Unhide and Protect sheet. You can also customize the TabItem Context menu by setting [IsCustomTabItemContextMenuEnabled](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic6331.html)  property to be true and you can add your customized menu items in Context_Menu opening Event.

{% highlight c# %}

    spreadsheet.IsCustomTabItemContextMenuEnabled = true;

{% endhighlight %}

### Cell Context menu

By default, [AllowCellContextMenu](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic6315.html) property is set as true to enable the CellContext Menu in Sfspreadsheet. The Event associated with Cell Context menu [CellContextMenuOpening](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic2597.html) Event of SpreadsheetGrid.

Adding the customized menu items in the CellContextMenuOpening Event,

{% highlight c# %}

    spreadsheet.ActiveGrid.CellContextMenuOpening += ActiveGrid_CellContextMenuOpening;

    void ActiveGrid_CellContextMenuOpening(object sender, CellContextMenuOpeningEventArgs e)

    {

        //Adding Customized Menu item

        MenuItem PasteSpecial = new MenuItem();

        PasteSpecial.Header = "Pastespecial";

        Image paste = new Image() { Source = new BitmapImage(new Uri(@"..\..\Icon\paste.png", UriKind.Relative)) };

        PasteSpecial.Icon = paste;

        spreadsheet.ActiveGrid.CellContextMenu.Items.Add(PasteSpecial);

        //Remove the existing Context menu

        spreadsheet.ActiveGrid.CellContextMenu.Items.RemoveAt(2);

    }

{% endhighlight %}
<br/>

## Cell Comments

SfSpreadsheet provides support for cell comments like in excel to give the reader additional context for the data it contains. You can set the comment height and color for the particular comments at runtime by invoking [CellCommentOpening](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic2596.html) Event of SpreadsheetGrid

To enable the comment in SfSpreadsheet, set the [ShowComment](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic2592.html) property of SpreadsheetGrid to true.

{% highlight c# %}

    spreadsheet.ActiveGrid.ShowComment = true;

{% endhighlight %}

To set the comments for particular cell at run time,

{% highlight c# %}

    spreadsheet.ActiveSheet.Range["E5"].AddComment().Text = "Sample Comment";
	spreadsheet.ActiveGrid.InvalidateCell(5, 5);
	
{% endhighlight %}
