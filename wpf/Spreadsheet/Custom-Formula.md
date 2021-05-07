---
layout: post
title: Custom Formula in WPF Spreadsheet control | Syncfusion
description: Learn here all about Custom Formula support in Syncfusion WPF Spreadsheet (SfSpreadsheet) control and more.
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Custom Formula in WPF Spreadsheet (SfSpreadsheet)

SfSpreadsheet allows you to add custom formulas into its function library. You can add the custom formula into the SfSpreadsheet by using the [AddFunction](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.FormulaEngine.html#Syncfusion_UI_Xaml_CellGrid_FormulaEngine_AddFunction_System_String_Syncfusion_UI_Xaml_CellGrid_FormulaEngine_LibraryFunction_) method of [FormulaEngine](http://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.CellGrid.FormulaEngine.html),

{% tabs %}
{% highlight c# %}
spreadsheet.WorkbookLoaded += spreadsheet_WorkbookLoaded;

void spreadsheet_WorkbookLoaded(object sender, WorkbookLoadedEventArgs args)
{

    foreach (var grid in args.GridCollection)
        AddCustomFormula(grid); 
  
  //Computing the formula at runtime

   var range = spreadsheet.ActiveSheet.Range["B2"];
   spreadsheet.ActiveGrid.SetCellValue(range,"=Find(sample)");
}  

private void AddCustomFormula(SpreadsheetGrid grid)
{

  // Add a formula named Find to the Library.
   grid.FormulaEngine.AddFunction("Find", new FormulaEngine.LibraryFunction(ComputeLength));      
}    

//Implementation of formula
    
public string ComputeLength(string range)
{
  //Used to calculate the length of the string
    return range.Length.ToString();
}   
{% endhighlight %}
{% endtabs %}
