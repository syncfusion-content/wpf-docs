---
layout: post
title: Interactive Features | SfSpreadsheet | WPF | Syncfusion
description: interactive features
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Interactive Features

## Clipboard Operations

SfSpreadsheet provides support for all the clipboard operations to with all the format settings when copied within a workbook. When the content is copied from external source, SfSpreadsheet does not support the format settings (paste options). 

The following are a list of paste options used while performing paste operation,

<table>
<tr>
<td>
**OPTIONS**</td><td>
**Description**</td></tr>
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

For Cut Operation,

{% highlight c# %}
			
    //To perform cut operation for selected ranges

    var range = spreadsheet.ActiveGrid.SelectedRanges.ActiveRange;

    spreadsheet.ActiveGrid.CopyPaste.Copy(range, true);

    //To perform cut operation

    spreadsheet.ActiveGrid.CopyPaste.Cut();

{% endhighlight %}

For Copy Operation,

{% highlight c# %}

    //To perform copy operation for selected ranges

    var range = spreadsheet.ActiveGrid.SelectedRanges.ActiveRange;

    spreadsheet.ActiveGrid.CopyPaste.Copy(range, false);

    //To perform Copy operation

    spreadsheet.ActiveGrid.CopyPaste.Copy();

{% endhighlight %}

For Paste Operation,

{% highlight c# %}

    //To perform paste operation

    spreadsheet.ActiveGrid.CopyPaste.Paste();

    //To perform paste operation with range and Paste Options

    var copyPaste = spreadsheet.ActiveGrid.CopyPaste as SpreadsheetCopyPaste;

    copyPaste.Paste(range);

    copyPaste.Paste(range, PasteOptions.Paste);

{% endhighlight %}

## Undo/Redo

SfSpreadsheet provides support for Undo/Redo functionality like MS Excel. 

SfSpreadsheet has HistoryManager class that supports the implementation of undo/ redo operations

To invoke Undo/Redo operations, the **Enabled** property of **HistoryManager** needs to be true.  

{% highlight c# %}

    spreadsheet.HistoryManager.Enabled = true;

    spreadsheet.HistoryManager.Undo();

    spreadsheet.HistoryManager.Redo();

{% endhighlight %}

## Context menu

Context menu in SfSpreadsheet is customizable menu which can be used for various functionalities

_**TabItem**_ _**context**_ _**menu**_

By default, “AllowTabItemContextMenu” property is set to true to enable the TabItemContext Menu in SfSpreadsheet. Default TabItem context menu has options like Insert, Delete, Hide/Unhide and Protect sheet. You can also customize the TabItem Context menu by setting “IsCustomTabItemContextMenuEnabled” property to be true and you can add your customized menu items in Context_Menu opening Event.

{% highlight c# %}

    spreadsheet.IsCustomTabItemContextMenuEnabled = true;

{% endhighlight %}

_**Cell**_ _**Context**_ _**menu**_

By default, “AllowCellContextMenu” property is set as true to enable the CellContext Menu in Sfspreadsheet. The Event associated with Cell Context menu is “CellContextMenuOpening” Event of SpreadsheetGrid.

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

## Cell Comments

SfSpreadsheet provides support for cell comments like in excel to give the reader additional context for the data it contains. You can set the comment height and color for the particular comments at runtime by invoking “CellCommentOpening” Event of SpreadsheetGrid

To enable the comment in SfSpreadsheet,

{% highlight c# %}

    spreadsheet.ActiveGrid.ShowComment = true;

{% endhighlight %}

To set the comments for particular cell at run time,

{% highlight c# %}

    spreadsheet.ActiveSheet.Range["E5"].AddComment().Text = "Sample Comment";
	spreadsheet.ActiveGrid.InvalidateCell(5, 5);
	
{% endhighlight %}
