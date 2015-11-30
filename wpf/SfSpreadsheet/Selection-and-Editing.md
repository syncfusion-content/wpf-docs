---
layout: post
title: Selection and Editing | SfSpreadsheet| WPF | Syncfusion
description: selection and editing
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Selection and Editing

## Selection

The SfSpreadsheet control provides support for selection in grid by using mouse, keyboard and touch interactions.

By default, Selection behavior will be enabled in SfSpreadsheet, but if you want to disable the selection in SfSpreadsheet, then set the “AllowSelection” Property to be false.

{% highlight c# %}
                  
    void spreadsheet_WorkbookLoaded(object sender, WorkbookLoadedEventArgs args)
    {
      spreadsheet.ActiveGrid.AllowSelection = false;
    }

{% endhighlight %}

The Events associated with the Selection behavior are

* SelectionChanging     – Occurs when the selection is going to be changed. This event allows to cancel the selection change.
* SelectionChanged      - Occurs after the selection is changed
* CurrentCellActivating - Occurs when the current cell is going to be activated. This event allow to cancel the current cell activation.
* CurrentCellActivated  - Occurs after the current cell is activated
* CellClick             - Occurs when you click on the cell

## Editing

The SfSpreadsheet control provides support for Editing, you can modify and commit the cell values in the workbook. The Events associated with the Editing are CurrentCellBeginEdit and CurrentCellEndEdit of SpreadsheetGrid.

{% highlight c# %}
             
    void spreadsheet_WorkbookLoaded(object sender, WorkbookLoadedEventArgs args)
    {
       foreach (var grid in args.GridCollection)
        {
          grid.CurrentCellBeginEdit += grid_CurrentCellBeginEdit;

          grid.CurrentCellEndEdit += grid_CurrentCellEndEdit;
        }
    }

    void grid_CurrentCellEndEdit(object sender, CurrentCellEndEditEventArgs args)
    {
      //Code          
    }
	
    void grid_CurrentCellBeginEdit(object sender, CurrentCellBeginEditEventArgs args)
    {
      //Code         
    }

{% endhighlight %}

The order of events when editing and committing a cell value in SfSpreadsheet,

<table>
<tr>
<td>
**Events**</td><td>
**Description**</td></tr>
<tr>
<td>
BeginEdit</td><td>
Occurs when the current cell enters into edit mode</td></tr>
<tr>
<td>
CurrentCellValueChanged</td><td>
Occurs when the current cell value is changed in edit mode</td></tr>
<tr>
<td>
CurrentCellValidating</td><td>
Occurs when the current cell value is going to be validated</td></tr>
<tr>
<td>
CurrentCellValidated</td><td>
Occurs after the current cell is validated</td></tr>
<tr>
<td>
CurrentCellEndEdit</td><td>
Occurs when the current cell leaves from edit mode</td></tr>
</table>
