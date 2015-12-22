---
layout: post
title: Custom Formula | SfSpreadsheet | WPF | Syncfusion
description: custom formula
platform: wpf
control: SfSpreadsheet
documentation: ug
---

# Custom Formula

SfSpreadsheet allows you to add custom formulas into its function library. You can add the custom formula into the SfSpreadsheet by using the [AddFunction](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic457.html) method of [FomulaEngine](http://help.syncfusion.com/cr/cref_files/wpf/sfspreadsheet/topic450.html),

{% tabs %}
{% highlight c# %}

    spreadsheet.WorkbookLoaded += spreadsheet_WorkbookLoaded;

    void spreadsheet_WorkbookLoaded(object sender, WorkbookLoadedEventArgs args)
    {
        foreach (var grid in args.GridCollection)
          AddCustomFormula(grid); 
          
        //Computing the formula at runtime
          var range = spreadsheetControl.ActiveSheet.Range["B2"];
          spreadsheetControl.ActiveGrid.SetCellValue(range,"=Find(aaa)");
    }

    private void AddCustomFormula(SpreadsheetGrid grid)
    {
       // Add a formula named Find to the Library.
       grid.FormulaEngine.AddFunction("Find", new LibraryFunction(ComputeLength));      
    }

    //Implementation of formula
    
    public string ComputeLength(string range)
    {
      //Used to find the length of the string
       return range.Length.ToString();
    }

{% endhighlight %}
{% endtabs %}