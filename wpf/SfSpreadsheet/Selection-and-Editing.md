---
layout: post
title: Selection and Editing
description: Selection and Editing behavior in SfSpreadsheet
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Selection and Editing

This section explains about the Selection and Editing behavior in SfSpreadsheet
<br/>

## Selection

The SfSpreadsheet control provides support for selection in grid by using mouse, keyboard and touch interactions.

By default, Selection behavior will be enabled in SfSpreadsheet,but if you want to disable the selection in SfSpreadsheet, then set the [AllowSelection](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~AllowSelection.html) Property to be false.

{% tabs %}
{% highlight c# %}

void spreadsheet_WorkbookLoaded(object sender, WorkbookLoadedEventArgs args)
{
    spreadsheet.ActiveGrid.AllowSelection = false;
}

{% endhighlight %}
{% endtabs %}

The Events associated with the Selection behavior are

* [SelectionChanging](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~SelectionChanging_EV.html)     – Occurs when the selection is going to be changed. This event allows to cancel the selection change.
* [SelectionChanged](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~SelectionChanged_EV.html)      - Occurs after the selection is changed
* [CurrentCellActivating](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~CurrentCellActivating_EV.html) - Occurs when the current cell is going to be activated. This event allow to cancel the current cell activation.
* [CurrentCellActivated](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~CurrentCellActivated_EV.html)  - Occurs after the current cell is activated
* [CellClick](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~CellClick_EV.html)             - Occurs when you click on the cell
<br/><br/>

## Editing

The SfSpreadsheet control provides support for Editing, you can modify and commit the cell values in the workbook. The Events associated with the Editing are CurrentCellBeginEdit and CurrentCellEndEdit of SpreadsheetGrid.

{% tabs %}
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
{% endtabs %}

The order of events when editing and committing a cell value in SfSpreadsheet,

<table>
<tr>
<th>
Events</th><th>
Description</th></tr>
<tr>
<td>
{{ '[CurrentCellBeginEdit](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~CurrentCellBeginEdit_EV.html)' | markdownify }}</td><td>
Occurs when the current cell enters into edit mode. This event allows to cancel entering the edit mode.</td></tr>
<tr>
<td>
{{ '[CurrentCellValueChanged](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~CurrentCellValueChanged_EV.html)' | markdownify }}</td><td>
Occurs when the current cell value is changed in edit mode</td></tr>
<tr>
<td>
{{ '[CurrentCellValidating](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~CurrentCellValidating_EV.html)' | markdownify }}</td><td>
Occurs when the current cell value is going to be validated</td></tr>
<tr>
<td>
{{ '[CurrentCellValidated](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~CurrentCellValidated_EV.html)' | markdownify }}</td><td>
Occurs after the current cell is validated</td></tr>
<tr>
<td>
{{ '[CurrentCellEndEdit](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/Syncfusion.SfCellGrid.WPF~Syncfusion.UI.Xaml.CellGrid.SfCellGrid~CurrentCellEndEdit_EV.html)' | markdownify }}</td><td>
Occurs when the current cell leaves from edit mode</td></tr>
</table>
