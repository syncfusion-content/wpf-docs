---
layout: post
title: Interactive Features in WPF Spreadsheet control | Syncfusion
description: Learn here all about Interactive Features support in Syncfusion WPF Spreadsheet (SfSpreadsheet) control and more.
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Interactive Features in WPF Spreadsheet (SfSpreadsheet)

 This section explains about the interactive operations with SfSpreadsheet

## Clipboard Operations

SfSpreadsheet provides support for all the clipboard operations to with all the format settings when copied within a workbook.  

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

N> When the content is copied from external source, SfSpreadsheet does not support the format settings (paste options).

For [Cut](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetCopyPaste.html#Syncfusion_UI_Xaml_Spreadsheet_SpreadsheetCopyPaste_Cut) Operation,

{% tabs %}
{% highlight c# %}
//To perform cut operation for selected ranges
var range = spreadsheet.ActiveGrid.SelectedRanges.ActiveRange;
spreadsheet.ActiveGrid.CopyPaste.Copy(range, true);

//To perform cut operation
spreadsheet.ActiveGrid.CopyPaste.Cut();
{% endhighlight %}
{% endtabs %}

For [Copy](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetCopyPaste.html#Syncfusion_UI_Xaml_Spreadsheet_SpreadsheetCopyPaste_Copy) Operation,

{% tabs %}
{% highlight c# %}
//To perform copy operation for selected ranges
var range = spreadsheet.ActiveGrid.SelectedRanges.ActiveRange;
spreadsheet.ActiveGrid.CopyPaste.Copy(range, false);

//To perform Copy operation
spreadsheet.ActiveGrid.CopyPaste.Copy();
{% endhighlight %}
{% endtabs %}

For [Paste](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetCopyPaste.html#Syncfusion_UI_Xaml_Spreadsheet_SpreadsheetCopyPaste_Paste) Operation,

{% tabs %}
{% highlight c# %}
//To perform paste operation
spreadsheet.ActiveGrid.CopyPaste.Paste();

//To perform paste operation with range and Paste Options
var copyPaste = spreadsheet.ActiveGrid.CopyPaste as SpreadsheetCopyPaste;
copyPaste.Paste(range);
copyPaste.Paste(range, PasteOptions.Paste);
{% endhighlight %}
{% endtabs %}

T> Users can also set their default [PasteOptions](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.PasteOptions.html) while pasting in SfSpreadsheet, by using [DefaultPasteOption](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SpreadsheetCopyPaste.html#Syncfusion_UI_Xaml_Spreadsheet_SpreadsheetCopyPaste_DefaultPasteOption) property.

## Undo/Redo

SfSpreadsheet provides support for Undo/Redo functionality like Microsoft Excel.

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

SfSpreadsheet has [History Manager](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.History.HistoryManager.html) class that supports the implementation of undo/ redo operations

By default, Undo/Redo operations in SfSpreadsheet is enabled. To disable the Undo/Redo operations, set the [Enabled](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.History.HistoryManager.html#Syncfusion_UI_Xaml_Spreadsheet_History_HistoryManager_Enabled) property of [History Manager](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.History.HistoryManager.html) to be false.  

{% tabs %}
{% highlight c# %}
spreadsheet.HistoryManager.Enabled = false;
{% endhighlight %}
{% endtabs %}

To programmatically, invoke the Undo/Redo operations,

{% tabs %}
{% highlight c# %}
spreadsheet.HistoryManager.Enabled = true;
spreadsheet.HistoryManager.Undo();
spreadsheet.HistoryManager.Redo();
{% endhighlight %}
{% endtabs %}

## Context menu

Context menu in SfSpreadsheet is customizable menu which can be used for various functionalities

### TabItem Context menu

TabItem Context menu opens when the user right-click on the sheet tab and contains the menus related to worksheet operations.

By default, TabItem Context menu is enabled in SfSpreadsheet. To disable the TabItem context menu, set the [AllowTabItemContextMenu](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_AllowTabItemContextMenu) property to false. 

{% tabs %}
{% highlight c# %}
spreadsheet.AllowTabItemContextMenu = false;
{% endhighlight %}
{% endtabs %}

Default TabItem context menu has options like Insert, Delete, Hide/Unhide and Protect sheet. You can also customize the TabItem Context menu by setting [IsCustomTabItemContextMenuEnabled](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_IsCustomTabItemContextMenuEnabled)  property to be true and you can add your customized menu items.

{% tabs %}
{% highlight c# %}
spreadsheet.IsCustomTabItemContextMenuEnabled = true;
spreadsheet.TabItemContextMenu = CustomTabItemContextMenu();

//Custom TabItem ContextMenus

public ContextMenu CustomTabItemContextMenu()
{
    var contextMenu = new ContextMenu();
    var insertRowIcon = new Image() { Source = new BitmapImage(new Uri(@"..\..\Icon\insertRow.png", UriKind.Relative)) };
    var insertRow = new MenuItem() { Header = "InsertRow" };           
    insertRow.Icon = insertRowIcon;
    insertRow.Click += insertRow_Click;

    var deleteRowIcon = new Image() { Source = new BitmapImage(new Uri(@"..\..\Icon\deleteRow.png", UriKind.Relative)) };
    var deleteRow = new MenuItem() { Header = "DeleteRow"};
    deleteRow.Icon = deleteRowIcon;
    deleteRow.Click += deleteRow_Click;
    
    contextMenu.Items.Add(insertRow);
    contextMenu.Items.Add(deleteRow);
    return contextMenu;
 }
{% endhighlight %}
{% endtabs %}

### Cell Context menu

Cell Context menu opens when the user right-click on a worksheet cell or selection of cells in SfSpreadsheet.

By default, Cell Context menu is enabled in SfSpreadsheet. To disable the Cell Context menu, set the [AllowCellContextMenu](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Spreadsheet.SfSpreadsheet.html#Syncfusion_UI_Xaml_Spreadsheet_SfSpreadsheet_AllowCellContextMenu)  property as false.

{% tabs %}
{% highlight c# %}
spreadsheet.AllowCellContextMenu = false;
{% endhighlight %}
{% endtabs %}

Users can also customize the Cell Context menu of SfSpreadsheet by using [CellContextMenuOpening](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SfCellGrid.html) Event of `SpreadsheetGrid`.

Adding the customized menu items in the CellContextMenuOpening Event,

{% tabs %}
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
{% endtabs %}

T> Custom Cell Context menu can also by added by assigning the customized menu items to the [CellContextMenu](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SfCellGrid.html#Syncfusion_UI_Xaml_CellGrid_SfCellGrid_CellContextMenu) property of `SpreadsheetGrid`. For your reference, [CustomContextMenu](https://www.syncfusion.com/kb/6499/how-to-create-a-customized-cell-context-menu-of-sfspreadsheet)

## Cell Comments

SfSpreadsheet provides support for cell comments like in excel to give the reader additional context for the data it contains. You can set the comment height and color for the particular comments at runtime by invoking [CellCommentOpening](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SfCellGrid.html) Event of SpreadsheetGrid

To enable the comment in SfSpreadsheet, set the [ShowComment](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.SfCellGrid.html#Syncfusion_UI_Xaml_CellGrid_SfCellGrid_ShowComment) property of SpreadsheetGrid to true.

{% tabs %}
{% highlight c# %}
spreadsheet.ActiveGrid.ShowComment = true;
{% endhighlight %}
{% endtabs %}

To set the comments for particular cell at run time,

{% tabs %}
{% highlight c# %}
spreadsheet.ActiveSheet.Range["E5"].AddComment().Text = "Sample Comment";
spreadsheet.ActiveGrid.InvalidateCell(5, 5);
{% endhighlight %}
{% endtabs %}


N> You can refer to our [WPF Spreadsheet](https://www.syncfusion.com/wpf-controls/spreadsheet) feature tour page for its groundbreaking feature representations. You can also explore our [WPF Spreadsheet example](https://github.com/syncfusion/wpf-demos) to know how to render and configure the spreadsheet.